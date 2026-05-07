# Complete OPC Workflow · opc-venture-screener

> This is a supplementary reference for `../SKILL.md`. The main skill provides the venture-screening decision protocol (red lines → scoring → stop-loss); this file contains pre/post stages of the full OPC chain: opportunity discovery → screening → commercialization → governance.

This skill is the **decision-gate** node of the full OPC pipeline. Complete workflow: **opportunity discovery → venture screening (this skill's core) → commercialization path design → post-launch execution governance**. The three sections below give the minimal self-contained protocol for the stages before and after screening, allowing the user to go independently from idea to operations without bringing in other skills. **No stage exempts the 15 red lines**; each section below labels which red lines remain in force during that stage.

## 1. Opportunity Discovery and Initial Screening (Pre-stage — Input to Screening)

**Trigger scenarios**: User has no specific idea, only asks "what OPC direction should I do", "what opportunities are there now", or can't produce a scoreable idea. **This stage does not score** (scoring is reserved for this skill's 5-dimension scoring card), only produces **opportunity cards** as screening input.

**Steps**:
1. **Asset inventory**: List the founder's existing assets (industry experience / data pool / channels / taste / tools), don't rely on "wanting to learn new skills".
2. **Boundary-shift scan**: Identify recent 12-month change points in AI / platforms / regulation / distribution / cost / user behavior — OPC opportunities always come from the edge of change.
3. **Niche user slicing**: Find small but growing user segments that big companies don't want to serve; clarify "pain point + already-paid alternative".
4. **Match founder's advantage**: Each candidate must answer "why is the founder in the top 1%" — if no answer, downgrade.
5. **Produce 3-5 opportunity cards**, enter screening.

**Opportunity card format** (screening input, simplified):
```
- title:
- target_segment:
- painful_job:
- current_alternatives: (existing paid solutions)
- boundary_shift: (which recent change is opening the window)
- founder_advantage: (which killer skill is hit)
- AI_automation_angle:
- monetization_hypothesis:
- first_validation_step: (not the product, but the minimum validation action)
- red_flags: (self-check which red lines are touched)
```

**Red lines still in force at this stage**: #1 (non-compete), #2 (self-built platform), #5 (real-name exposure), #6 (direct AI image generation), #7 (game mechanics) — any opportunity card that hits one of these 5, **does not enter screening, discard directly**.

**Connecting to screening**: ≥3 clean opportunity cards → run each through the 5-dimension scoring card. **Not allowed** to skip the opportunity card and directly score an idea; ideas without paid-alternative evidence are forced back to redo this section.

---

## 2. Post-Pass Commercialization Path Design (Post-stage — Activated when screening ≥18)

**Trigger scenarios**: An idea passes all red lines, scores ≥18 on the 5 dimensions. **Strictly forbidden to develop the product directly**; first design the minimal payment/commitment validation loop.

**Design sequence (8 steps, non-skippable)**:
1. Lock target user segment + value proposition (one sentence).
2. Identify the **highest-risk assumption** (will users pay? can AI keep cost down? can the channel deliver?) — only one, not concurrent.
3. **MVP type selection** (only 7 allowed): landing page + waitlist / paid consulting pilot / AI-assisted manual report / content series with conversion hook / template pack pre-sale / single-workflow thin tool / form-then-concierge delivery.
4. Design the offer: result promise / price hypothesis / deliverable / refund or cap boundary.
5. Design the conversion loop: reach → trust → action → payment or commitment → delivery → feedback.
6. Split AI / human: HITL steps explicit, weekly hours estimated (must be ≤2h, otherwise back to screening to re-evaluate M2).
7. Write metrics: acquisition / activation / payment / delivery cost / satisfaction / repurchase.
8. Asset distillation: at the end of this loop, what templates / data / content / automation candidates will be deposited.

**MVP hard prohibitions**: full account system / multi-sided market / portal / complex community / large content library before launch — **touch one and veto**, back to screening to re-evaluate dimension 5 (operational risk).

**Red lines still in force at this stage**: #2 (self-built platform — even MVP not allowed), #3 (real-time customer service — concierge must be asynchronizable), #4 (LTV<CAC×1.5 cut offer immediately), #8 (HITL>2h/week = MVP failure).

**Connection logic**: ⬅ Input = screening output + stop-loss list. ➡ After MVP runs for 4 weeks, must return to screening and re-score the 5 dimensions with real data; score drops to <18 → back to Backlog; stop-loss triggered → immediate kill, no negotiation.

---

## 3. Post-Launch Execution Governance (Post-stage — After venture launches)

**Trigger scenarios**: Venture is commercialized, generating revenue, in daily operation. **Governance goal = make stop-loss rules actually bite + deposit reusable assets + recover across tools/devices.**

**SOP minimum skeleton** (every venture must have one, no more than one page):
```
Trigger: When to run this SOP (event / time)
Inputs:  Required source-of-truth files (don't rely on AI memory)
Steps:   1.. 2.. 3.. (numbered, executable, verifiable)
Gates:   Which checks must pass to continue
Outputs: Files / handoff fields
Stop:    Under what conditions to halt / when to call the founder
```

**Weekly dashboard review** (non-skippable): Check item by item against the stop-loss list set during screening:
- ROAS / gross margin / weekly HITL hours / user feedback count / founder self-use frequency — any metric entering red-line #9-#15 zone, **decide that week**: continue / pivot / kill. **Not allowed to "observe one more week"** (decision paralysis itself is an OPC failure mode).

**Asset distillation (required after each major task, otherwise the task is not done)**: templates / SOPs / data insights / script tools / content assets / cases / model prompt improvements / runtime backlog — at least 1 item must land; if none, must explain in writing why this task was still worth doing.

**AI execution red lines (don't exist at screening stage but bite at operations stage)**:
1. Letting the founder manually do an automatable action = failure output (must provide one-click script).
2. Skipping commercialization to chase only product polish = deviation from this protocol.
3. Writing into metadata without verifying LLM `usage.total_tokens > 0` = fabricated output, treat as error.
4. Replacing local source-of-truth files with AI chat memory = guaranteed cross-device crash.

**Red lines still in force at this stage**: #8-#15 all (this is the stop-loss zone). **Reaffirm**: #15 (founder doesn't use own product for a week → kill) is an honest signal, not noise.

**Connection logic**: ⬅ Input = offer / SOP / metrics / stop-loss output by the commercialization stage. ➡ Once a month, return to this skill and re-evaluate with the latest real data; stop-loss triggered → forced kill, do not enter the "iterate one more version" loop.

---

> **License & Attribution**: CC BY-NC-ND-4.0+ with custom terms. © 2026 FantasyMax. Skill ID: `opcvs-v1.0-20260507-yqcr`. Contact: HiFantasyMax. See `../LICENSE.md`.
