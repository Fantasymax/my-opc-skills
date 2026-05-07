---
name: multi-llm-cost-handbook
description: Multi-model swarm orchestration + cost-control engineering methodology. Define roles first, then pick models; pay-per-token vs monthly coding-plan crossover judgment; output verification gates; provider isolation + schema-driven configuration. Use when the user says "what model should this AI project use", "is metered billing or monthly cheaper", "how do I avoid single-provider outage", "how do I verify whether LLM output is real", "how should I rank model selection". **All concrete provider names / model names / prices / API keys are placeholders — when invoked, guide the user to read real configuration from their own .env.**
---

# Multi-LLM Cost Handbook · Multi-Model Engineering Methodology

> **© 2026 FantasyMax** · `multi-llm-cost-handbook` v1.0 · License: **CC BY-NC-ND-4.0+** (with custom enhanced terms)
> Skill ID: `mllmh-v1.0-20260507-yqcr` · Created: 2026-05-07
> ✅ Allowed: private study / short quotation (with attribution) / personal use / public mention (with link)
> ❌ Forbidden: redistribution of the whole or substantial parts / commercial use / derivative redistribution / removal of attribution / inclusion in LLM training sets / cloning >50% of the structure
> See `LICENSE.md` for details. Citation format: "Methodology cited from FantasyMax's `multi-llm-cost-handbook`, Skill ID: mllmh-v1.0-20260507-yqcr"

## Stance Card

This skill provides a **multi-model swarm orchestration + cost engineering methodology**. **Core stance**: reject pay-per-token spike risk (under flawed architecture, a metered monthly invoice can pile up thousands of yuan in unexpected costs within days), and advocate the "**multi-provider monthly coding-plan subscriptions + role-tiered**" route. **Core discipline**: do not fabricate token counts, do not hardcode base_url, do not skip gates. **This is engineering methodology, not a model recommendation table** — which specific provider / model version expires, the methodology does not.

## Agentic Protocol

### Step 1 · Reaction when receiving a model/cost question

1. **Do not proactively give a specific provider/model name** — those expire. What you give is **tier** and **judgment criteria**.
2. **You must first ask 3 things clearly**:
   - What is the project's core task (generation / review / translation / RAG retrieval...)
   - Estimated monthly token consumption magnitude (< 50K / 50K-200K / > 200K)
   - Is there a need to discriminate "true vs fabricated output" (decides whether to install gates)
3. **Any concrete provider/model recommendation must carry an "expiry declaration"**:
   > "The following recommendation is based on the [year-month] market situation, valid for at most 6 months. Please periodically re-review Provider_Endpoints."

### Step 2 · Output format

```
🎭 Role definitions:
  - [Role A] = [task characteristics]
  - [Role B] = [task characteristics]
  ...

🎚️ Model tier recommendation (no binding to specific versions):
  - [Role A] → [tier description] → user reads PROVIDER_A_MODEL from ~/.gne_keys/.env
  - [Role B] → [tier description] → user reads PROVIDER_B_MODEL from ~/.gne_keys/.env

💰 Cost judgment:
  - Estimated monthly consumption: [magnitude]
  - Recommended routing: [pay-per-token / monthly / hybrid]
  - Expected monthly cost: [relative magnitude, no specific dollar amount]

🛡️ Mandatory gates:
  - [Gate rule 1]
  - [Gate rule 2]

🔄 Fallback chain:
  - [Role A] primary → [Role A] fallback
  - [Role B] primary → [Role B] fallback

⚠️ Expiry conditions:
```

---

## 6 Core Mental Models

### M1 · Role ≠ Model — architecture first, staffing later
**Core**: define product **roles** (e.g. Architect / Writer / Inspector_AntiAI / Inspector_Logic / Inspector_Market / Translator / Sandtable_DM / DB_Updater), then for each role pick a model by "capability + cost". **The same model can be shared across roles; the same role can use different models in different contexts (fallback).**

**Application**:
1. New feature → first define the role (e.g. "speech-to-text QA")
2. Look up the role-tier mapping table
3. Read the corresponding provider's coding plan support list
4. Configure only that role's API key in the env_file
5. Recommended model goes down today → switch via the fallback role table, no app restart needed

**Expires when**: when models develop a new generational capability gap, the 1:1 mapping breaks, and you must add a "role × multi-model evaluation matrix".

### M2 · The crossover point between pay-per-token and monthly subscription

```
if monthly tokens < 50K:
  pay-per-token (saves cost, but with 4+ providers complexity rises)
elif monthly tokens 50K-200K:
  watershed. If projected to break 200K within 3 months → monthly; otherwise pay-per-token
elif monthly tokens > 200K:
  must be monthly (pay-per-token spike risk > monthly premium)
```

**Key insight**: monthly subscription is not just saving money, it is **insurance against underlying instability**. Metered APIs commonly suffer sudden throttling / spike price hikes / models being cut. Monthly = prepaid cost in exchange for certainty.

### M3 · Output verification gates — not verifying tokens is dancing on landmines
**Core**: every LLM call must verify `response.usage.total_tokens > 0`. Otherwise treat as fabricated output, which cannot enter DB / be sent for review / be delivered.

```python
response = await client.messages.create(...)
assert response.usage.total_tokens > 0, f"fabricated output: {response.model} returned 0 tokens"
metadata["token_usage"] = response.usage.total_tokens
```

**Application**:
- Install this gate at the head of every worker function
- CI gate scans all output token_usage; non-zero return values block the commit
- Token consumption trend monitoring: per-chapter spike > 200% triggers an automatic alert

**Expires when**: when a provider changes the response format (renames the usage field), you must add a "provider response normalization adapter layer".

### M4 · Provider isolation = cost + fault tolerance
**Core**: do not bind to a single provider. Each critical role has at least 1-2 alternates, and they go through **different coding-plan monthly subscriptions**.

**ROI calculation**:
- Single-provider monthly fee X
- N-provider isolation monthly fee = X × N
- One provider's outage = 1 full day of lost productivity ≈ daily revenue loss ¥Y
- Payback period for 4-provider isolation = (3X) ÷ Y days, typically pays back in 30-60 days

**Expires when**: all providers go down simultaneously (extremely low probability, but allowed by physics). Fallback plan = locally fine-tuned model (needs 24+ hours of preparation).

### M5 · Schema-Driven Beats Hardcode
**Core**: model name / base_url / token quotas / fallback chain all live in config tables, never hardcoded in code. **Models iterate fast; what was recommended last month may be replaced next month.**

```python
# ❌ Don't do this
base_url = "https://example.com/api/v3"
model = "specific-model-v1.0"

# ✅ Do this
PROVIDER_CONFIG = {
  "provider_a": {
    "base_url": os.getenv("PROVIDER_A_BASE_URL"),
    "model": os.getenv("PROVIDER_A_MODEL"),
    "fallback": "provider_b"
  }
}
```

**Single source of truth**: `Provider_Endpoints.md` (maintained by the user in their own vault). Code reads via environment variables; change one place and it takes effect globally.

### M6 · Bilingual / multi-modal artifact symmetry
**Core**: if the product form is "Chinese-English bilingual" or "image+text", all artifacts must be **produced synchronously, reviewed synchronously, and delivered synchronously**, all carrying complete frontmatter (author / core_model / status / token_usage).

**Supervision**: `audit-output-metadata` scans for missing_pair / missing_field; missing = violation.

**Expires when**: a provider suddenly stops supporting a particular language/modality, requiring a backup model.

---

## Role → Model Tier Mapping (placeholder version)

> ⚠️ The following uses **role name + tier description**, not bound to specific model versions. Specific models are read from `~/.gne_keys/.env`.

| Role | Task characteristics | Tier description | Provider form recommendation | Failure signal | Fallback chain |
|---|---|---|---|---|---|
| **Architect** | Human-in-the-loop dialogue, global decisions, conflict resolution | Top-tier reasoning model tier (the strongest reasoning of the period) | IDE-embedded / direct API (not a swarm worker) | No response over 15 min / long-context collapse | None (human intervention) |
| **Writer** | Long-form coherent generation (novel body / copy / docs) | Mid-reasoning + high-speed tier (the period's fast tier) | Provider A coding plan | timeout / output word count below target / token=0 | Provider A reduced-speed variant → Provider B same tier |
| **Translator** | Translation, format preservation, terminology consistency | Professional translation tier (well-trained on multi-language) | Provider A coding plan (shared with Writer or independent) | Missed sentences / terminology drift > 5% | Provider C same tier |
| **Inspector_AntiAI** | Detect AI plastic phrasing, fake feel | Strong discrimination tier (period's strong reasoning) | Provider B coding plan | False Positive > 10% / timeout | Provider D |
| **Inspector_Logic** | Setting consistency, causal breaks, timeline bugs | Strong logic tier (period's logic-heavy) | Provider C coding plan | Missed-bug rate > 5% | Provider D |
| **Inspector_Market** | Pacing, climax tension, commercial value | Commercial-intuition tier (period's strong instruction-following) | Provider D coding plan | Feedback diverges from human evaluation > 2 times | Provider C |
| **Sandtable_DM** | TRPG simulation, probability calculation, dispassionate combat reports | Strong reasoning tier | Provider B coding plan | Logic inconsistency / token_usage abnormal | Provider D |
| **DB_Updater** | Parse output → DB JSON CRUD | Fast-processing tier (no strong reasoning needed) | Any coding plan | Update failure / JSON format error | Counterpart provider |

**Configuration spec** (mandatory):
- Model names live only in `~/.gne_keys/.env` (variable naming: `PROVIDER_<X>_MODEL` / `PROVIDER_<X>_BASE_URL` / `PROVIDER_<X>_APIKEY`)
- Code layer reads only environment variables, **never hardcodes**
- `Provider_Endpoints.md` is the single source of truth (maintained by the user)

---

## Engineering Gate Checklist (15 items — copy and use)

| # | Gate | Description |
|---|---|---|
| 1 | **Token verification** | Every LLM call must `assert response.usage.total_tokens > 0` |
| 2 | **Base URL via env var** | No hardcoded base_url; read from `~/.gne_keys/.env` |
| 3 | **API Key isolation** | `.env` lives only in a hidden folder under the user home; never enters repo / sync / handoff |
| 4 | **Coding-plan routing** | Use each provider's coding-plan-specific base_url (not the metered endpoint) |
| 5 | **Model-name allowlist** | Permitted model names go into `ALLOWED_MODELS`; new ones are added to Provider_Endpoints.md first |
| 6 | **Multi-artifact symmetry** | Multi-language/multi-modal artifacts must be in sync; missing = violation |
| 7 | **Frontmatter completeness** | Each artifact must carry `author / core_model / status / word_count / token_usage` |
| 8 | **Output length constraint** | Hard constraint (e.g. body N-M chars); under/over both blocked |
| 9 | **Path dynamic resolution** | Use `pathlib.Path(__file__).resolve().parent`, no hardcoded drive letters |
| 10 | **Dependency-library gate** | Critical dependencies (e.g. setting bible) must be audited first; cannot be empty |
| 11 | **Provider health check** | Test each provider's connectivity at session start; outage triggers alert + fallback suggestion |
| 12 | **Metadata version control** | Artifacts auto-record `generated_at / generated_by / swarm_config_hash` for traceability |
| 13 | **Token trend monitoring** | Maintain a token-consumption log; per-call spike > 200% triggers automatic alert + review |
| 14 | **Mandatory session handoff** | Every session ends with `session finish`, producing a handoff file |
| 15 | **Inspector three-pass review** | Critical artifacts pass ≥3 independent Inspectors; any one failing blocks publication |

---

## Cost Trade-off Decision Heuristics

1. **Monthly consumption < 50K tokens** → consider pay-per-token. But if you already use ≥4 providers, pay-per-token actually adds complexity; recommend 1-2 monthly subscriptions.
2. **Monthly consumption 50-200K** → watershed. If 3-month outlook will break 200K → buy monthly early to lock cost.
3. **Monthly consumption > 200K** → must be monthly. Spike risk > monthly premium.
4. **Single-provider monthly fee low, token-pack quota large** → consider downgrading tier (lite plan) or shared subscription.
5. **Fallback-chain cost calculation** → each fallback adds one provider's monthly fee, but avoids outage loss (1 day of production stop ≈ daily revenue). Four-provider isolation usually has positive ROI.
6. **Strong-reasoning vs fast-tier total cost** → strong reasoning uses more tokens but higher accuracy (less rework); fast tier has cheaper tokens but may need more iterations. Look at **average total cost**, not unit price.
7. **Local cache / vector DB** → RAG can reduce repeat calls; raising hit rate from 30%→60% can save ~30% cost.
8. **Periodic cost audit** → run `audit cost --month YYYY-MM` at month-end, reconcile invoices with token_usage logs; flag anomalies immediately.

---

## Anti-Patterns / Red Lines

1. ❌ **Fabricating token data** — filling metadata before getting a real API response leads to month-end reconciliation failure + irreproducibility.
2. ❌ **Single-provider dependency** — if that provider goes down, the whole pipeline stops.
3. ❌ **Pay-per-token as default** — cheap but high-uncertainty, easily throttled or hit by sudden price hikes.
4. ❌ **Hardcoding base_url / model names** — upgrades require changing 3+ places in code; missing one = wrong-model call.
5. ❌ **Skipping the Inspector** — Writer outputs go straight out without review; 80% of plastic feel / setting bugs will be sent back, doubling cost.
6. ❌ **Asynchronous multi-artifact delivery** — miss the market window (e.g. a new book's chart-pushing window is only 7 days).

---

## Workflow Template (new AI project onboarding)

```
Step 1 · Requirements definition (10 min)
  - Critical task list? (generation / review / translation / data update / RAG)
  - Estimated monthly call volume per task?
  - Aggregate to "total monthly consumption magnitude"

Step 2 · Model tier selection (30 min)
  - Look up role-tier mapping; list 1-3 candidate tiers per task
  - Evaluate the "quality / speed / cost" triangle
  - Pick primary + fallback

Step 3 · Provider selection (20 min)
  - Check Provider_Endpoints.md; confirm which providers support each tier
  - Evaluate stability / support / monthly price
  - Principle: ≥2 provider isolation

Step 4 · Cost evaluation (15 min)
  - total monthly tokens × pay-per-token unit price = cost A
  - number of providers × monthly fee = cost B
  - if A < B × 0.3: use pay-per-token
  - elif A < B: use monthly but a smaller plan
  - else: use standard monthly

Step 5 · Pre-launch gate-checklist review (5 min)
  ☑ Token verification logic exists
  ☑ Base URL comes from env_file
  ☑ Fallback chain configured
  ☑ Model names on allowlist
  ☑ Multi-artifact symmetry (if needed)
  ☑ session start/finish runs

Step 6 · Launch (deploy + monitor)
  - First-week ops: actual token consumption vs estimate
  - Tune fallback trigger thresholds
  - Configure alert rules
```

---

## Honest Boundaries

1. **Model recommendations are time-bound** — any concrete model recommendation has a validity ≤ 6 months. After expiry, re-benchmark.
2. **Does not replace empirical benchmarking** — this table is heuristic. New projects should spend 1-2 weeks comparing 2-3 candidate tiers.
3. **Provider policies can change** — coding-plan packages / prices / supported models can all shift. Periodically (quarterly) sync Provider_Endpoints.md.
4. **Cross-border business regulation** — going overseas requires evaluating data residency, content review, tax compliance. This table is purely technical; it does not cover legal/finance.
5. **Does not bind to specific model versions** — this skill always teaches tiers and judgment criteria, never maintains a "current best model list".

---

## Self-Contained Declaration / Optional Skills

**This skill is fully self-contained**, with no dependency on any other skill, to complete the entire multi-model swarm orchestration + cost-control workflow (role mapping / model tiers / engineering gates / fallback chains / decision heuristics).

**Optional (not mandatory)**:

- If your workflow does use the **Claude API** (Anthropic SDK), you can refer to Anthropic's official `claude-api` skill for Claude-specific optimizations (prompt caching, extended thinking, batch API, etc.) — this skill provides a **multi-provider general methodology** and does not replace single-provider SDK documentation.
- If `claude-api` skill is not installed: this skill's M3 (Token verification gate) + M5 (Schema-Driven) already cover the core engineering discipline of the Claude API; cost-saving optimizations like prompt caching are native to the Anthropic docs — just check https://docs.anthropic.com directly.

---

## Quality Verification (self-diagnostic question set)

> Usage: verify whether the LLM is working under production-validated engineering discipline rather than a generic SDK tutorial.
> Pass criteria: ≥ 80% answered with the specialized version.

### T1 · Refuse to recommend specific models

**Input**: "I'm doing novel generation. Which model should I use?"

| | |
|---|---|
| ❌ Generic answer | "Recommend GPT-4 / Claude Opus / Gemini Pro because..." |
| ✅ Expert answer | "**This skill does not recommend specific model names** — those expire. What it gives is **tier + judgment criteria**: (1) First define the role (Writer role: long-form coherent generation). (2) Recommended tier: same-period fast tier (mid-reasoning + high-speed). (3) You read PROVIDER_A_MODEL from your own `~/.gne_keys/.env`. (4) Mandatory fallback chain, at least 2-provider isolation. **Not binding specific versions is engineering discipline** — models iterate fast, recommendations expire within half a year." |

### T2 · Pay-per-token vs monthly decision tree

**Input**: "My AI project's estimated monthly consumption is 80K tokens. Is metered billing or monthly cheaper?"

| | |
|---|---|
| ❌ Generic answer | "Pay-per-token is cheaper, recommend pay-per-token" |
| ✅ Expert answer | "**80K is in the 50K-200K watershed**. You need to look at 3-month growth expectation: (1) If you'll break 200K within 3 months → buy monthly early to lock cost (monthly's insurance value against underlying instability is high). (2) If stable at 80K → pay-per-token works, but recommend at least 1 monthly as fallback. (3) Monthly is not just saving money, it's **insurance against spike risk** (throttling / sudden price hike / model getting cut)." |

### T3 · Token verification gate

**Input**: "My LLM call code: `response = client.chat.completions.create(...); content = response.choices[0].message.content; save_to_db(content)`. Can I use it directly?"

| | |
|---|---|
| ❌ Generic answer | "Looks OK, you can use it" |
| ✅ Expert answer | "**Major flaw, missing the token verification gate**. Fix: ```python\nresponse = client.chat.completions.create(...)\nassert response.usage.total_tokens > 0, f'fabricated output: {response.model} returned 0 tokens'\ncontent = response.choices[0].message.content\nsave_to_db(content, token_usage=response.usage.total_tokens)\n```\nHits M3 · Output verification gate. **Not verifying tokens is dancing on landmines** — mock misconfig / proxy layer swallowing the response / silent API failure all lead to fabricated output entering the DB, month-end reconciliation failure + irreproducibility." |

### T4 · Provider isolation ROI

**Input**: "All my roles currently use the same provider, monthly fee ¥400. Adding a fallback provider would be another ¥400/month. Is it worth it?"

| | |
|---|---|
| ❌ Generic answer | "Depends on usage, not necessarily worth it" |
| ✅ Expert answer | "**Calculate the ROI**: (1) Single-provider outage loss = 1 day of production stop ≈ your daily revenue / earnings. (2) Adding a fallback = ¥400/month extra. (3) Payback = 400 ÷ daily revenue days. E.g. daily revenue ¥30, payback ≈ 13 days — if provider outage exceeds 13 days within a year, you've broken even. **In production, outage probability is far from 0**: throttling / policy change / service degradation are common. Recommendation: ≥2-provider isolation is the floor; 3-4 is more solid." |

### T5 · Hardcoding anti-pattern

**Input**: "I just write in code: `base_url = 'https://api.example.com/v1'; model = 'gpt-4'`. Clean and direct. What's wrong with that?"

| | |
|---|---|
| ❌ Generic answer | "That works, simple and direct" |
| ✅ Expert answer | "**Two problems**: (1) **base_url hardcoded** — when the provider changes the endpoint, you must change N places in code (not 1); miss one = call wrong place. (2) **Model name hardcoded** — same problem on model upgrades (gpt-4 → gpt-5). Fix: env var + `Provider_Endpoints.md` as the single source of truth: ```python\nbase_url = os.getenv('PROVIDER_BASE_URL')\nmodel = os.getenv('PROVIDER_MODEL')\n```\nHits M5 · Schema-Driven Beats Hardcode. **Models iterate fast; the config layer must not be hardcoded**." |

### T6 · Three things you must ask

**Input**: "I'm building an AI agent app. Help me pick a model."

| Verification point | Should display |
|---|---|
| Don't directly give a concrete recommendation | ✓ |
| Reverse-ask the core task (generation/review/translation/RAG) | ✓ |
| Reverse-ask monthly token estimate | ✓ |
| Reverse-ask whether "true vs fabricated output" discrimination is needed | ✓ |
| Give tier + judgment criteria, not specific model names | ✓ |
| Recommend a fallback chain | ✓ |
| Mention reading config from `~/.gne_keys/.env` | ✓ |

### T7 · Multi-artifact symmetry

**Input**: "I'm doing Chinese-English bilingual novel generation. Releasing the CN version first to grab the market, EN version 1 month later. Doable?"

| | |
|---|---|
| ❌ Generic answer | "Sure, ship first to grab the market" |
| ✅ Expert answer | "**Anti-pattern #6 — asynchronous multi-artifact delivery**. Hits M6. Problems: (1) On platforms like KDP, the new-book chart-pushing window is typically 7 days; CN already published while EN isn't ready = miss the EN market starting line. (2) Asymmetric frontmatter = audit failure (missing_pair). (3) Late EN lacks early word-of-mouth accumulation. **Correct approach**: CN/EN must produce + review + deliver synchronously. If you can't do EN in time, push back the CN release date too, until EN is ready." |

### T8 · Model recommendation expiry declaration

**Input**: "Should I use GPT-4 or Claude 4 right now?"

| | |
|---|---|
| ❌ Generic answer | "Use X, it's better" |
| ✅ Expert answer | "**Two-point answer**: (1) This skill does not maintain a 'current best model list'; it always teaches tiers and judgment criteria. (2) Both are top-tier reasoning model tiers; you should look at concrete task fit (e.g. prompt-caching friendliness / vision needs / price / your existing subscriptions). To judge a **specific task**'s better tier, I need task characteristics. If you want 'currently optimal', re-review `Provider_Endpoints.md` periodically; don't rely on this skill's judgment (it has a 6-month validity)." |

### T9 · Refusing to skip the Inspector

**Input**: "For speed, can the Writer output go directly without an Inspector review?"

| | |
|---|---|
| ❌ Generic answer | "Sure, simplifies the flow" |
| ✅ Expert answer | "**Anti-pattern #5 — skipping the Inspector**. Short-term it looks fast; long-term 80% of plastic feel / setting bugs get sent back manually, **total cost actually doubles**. The Inspector is not flow redundancy — it's **defense against the Writer model's inherent flaws** (AI cliche template phrasing, setting holes, pacing imbalance). If it feels slow, optimize the Inspector's parallelism / cache / threshold; don't remove it." |

---

> **License & Attribution**: CC BY-NC-ND-4.0+ with custom terms. © 2026 FantasyMax. Skill ID: `mllmh-v1.0-20260507-yqcr`. Contact: HiFantasyMax. See `LICENSE.md`.
