# Grassroot Hopper — Cofounder Tool Plan

*Date: 2026-03-08*  
*Purpose: lock the cofounder tool's design, product spec, and architecture before any implementation work.*

---

## What this round is for

This planning round is **not** about building the funnel yet.

It is about answering, in a way that survives contact with real execution:

1. **What is this tool, exactly?**
2. **What problem is it solving?**
3. **Who is it for?**
4. **What does success look like?**
5. **What architecture is justified by that definition, and what is premature?**

If we do this right, the repo should stop feeling like "good ideas plus placeholders" and start feeling like one coherent product.

Additional context from the earlier Perplexity conversation sharpens this further:

- this tool exists because the real bottleneck is **team formation**, not funding
- it should help Julien move from **convincing friends** to attracting **high-agency strangers**
- transparency about what Julien brings and what he lacks is not a side note; it is part of the product
- the tool itself should quietly prove that Julien can ship something serious with AI/no-code leverage

---

## End state for this plan

When this plan is complete, these statements should all be true:

- `docs/spec.md` clearly defines the tool in its opening sections
- `docs/spec.md` makes the goal, non-goals, and success criteria explicit
- `docs/architecture.md` only describes architecture that serves the frozen spec
- `README.md` points to the right source-of-truth docs in the right order
- there is no meaningful contradiction between the spec, architecture, and repo entrypoint
- the remaining open questions are few, visible, and deliberate

---

## Out of scope for this round

Do **not** drift into these yet:

- building the landing page
- choosing exact vendors in production
- wiring Make/Zapier
- building Airtable tables
- drafting final prompts and JSON schemas
- polishing UI copy beyond what is needed to define the product

Those are next-step tasks. This round is for **definition first**.

---

## Core principle for sequencing

The order here is intentional:

**product definition -> success definition -> design boundaries -> architecture alignment -> repo alignment**

Not:

**tool choices -> implementation details -> backfilled product reasoning**

---

## Phase 1 — Lock what the tool is

### Task 1 — Rewrite the opening definition

- **Time box:** 3-5 minutes
- **File:** `docs/spec.md`
- **What to do:** Rewrite the top of the spec so the first screenful answers:
  - what the tool is
  - who uses it
  - why it exists
  - why Grassroot Hopper needs it now
- **Why:** Right now the spec is strong, but still broad enough that it can drift toward "smart recruiting system" instead of "serious founder-selection funnel."
- **Verification:** A reader can answer "what is this?" after reading only the title, one-paragraph summary, and problem statement.

### Task 2 — Tighten the problem statement

- **Time box:** 3 minutes
- **File:** `docs/spec.md`
- **What to do:** Rewrite the problem section so it states the current bottleneck plainly:
  - awkward outbound cofounder search
  - no serious inbound channel
  - no structured comparison beyond vibes
  - too much gravitational pull toward recruiting friends as a safety mechanism
- **Why:** If the problem statement is fuzzy, every later feature becomes easier to justify badly.
- **Verification:** The problem statement names current pain, not future ambition.

### Task 3 — Freeze the primary goal

- **Time box:** 2-4 minutes
- **File:** `docs/spec.md`
- **What to do:** Rewrite the goals section so one goal is clearly primary:
  - create a credible inbound cofounder-selection funnel
  - specifically one that attracts strong strangers without requiring Julien to "sell" the idea person by person
- **Why:** The current spec has good goals, but this round should force a ranked hierarchy.
- **Verification:** There is one clearly dominant success goal and the rest read as support, not peers.

### Task 3.5 — Define the founder value proposition explicitly

- **Time box:** 3-4 minutes
- **File:** `docs/spec.md`
- **What to do:** Add or tighten a section that clearly states what Julien brings to the table:
  - proven operator history
  - existing profitable business
  - real financial skin in the game / runway
  - willingness to be CEO
  - openness to pivot

  And what he does not bring:
  - deep coding skill
  - a full founding team yet
- **Why:** The external conversation makes clear this transparency is part of the actual product design, not just persuasive copy.
- **Verification:** A strong candidate can quickly understand why Julien is worth taking seriously and where partnership is genuinely needed.

### Task 4 — Define success and failure explicitly

- **Time box:** 4-5 minutes
- **File:** `docs/spec.md`
- **What to do:** Rewrite success criteria so they are concrete and observable. Add a short failure-signals subsection, for example:
  - applications are high in volume but weak in seriousness
  - Julien still has to read everything from scratch
  - scoring feels decorative rather than useful
  - the tool attracts general job-seekers instead of founder-fit people
- **Why:** "Success" is currently present, but "failure" is mostly implied.
- **Verification:** Someone reading the spec can say both "how we will know this is working" and "how we will know it is drifting."

### Task 5 — Lock non-goals harder

- **Time box:** 3 minutes
- **File:** `docs/spec.md`
- **What to do:** Strengthen the non-goals section so it explicitly rules out:
  - ATS creep
  - pseudo-psychology
  - automating acceptance/rejection
  - optimizing for volume
- **Why:** This protects the product from becoming a generic hiring machine.
- **Verification:** At least one likely-but-wrong future direction is explicitly named and rejected.

---

## Phase 2 — Lock the product design

### Task 6 — Tighten the user model

- **Time box:** 3-5 minutes
- **Files:** `docs/spec.md`, `product/questions/role_tracks.md`
- **What to do:** Decide whether the v1 tool is truly serving two tracks from day one:
  - CTO / Pragmatic Builder
  - Community / Ops Architect

  If yes, make the distinction sharper. If no, narrow the scope now instead of pretending both are equally ready.
- **Why:** Dual-track systems add complexity fast. This is a high-leverage scope decision.
- **Verification:** The repo makes a clear statement about whether both tracks are in-scope for v1.

  The external conversation suggests a likely default:
  - **primary v1 focus:** pragmatic builder / technical cofounder
  - **secondary or later:** community architect / ops

### Task 7 — Tighten the applicant journey

- **Time box:** 4 minutes
- **File:** `docs/spec.md`
- **What to do:** Rewrite the applicant journey to emphasize:
  - seriousness
  - selective friction
  - transparency about uncertainty
  - what happens after submission
- **Why:** This is the heart of the product design, not just UX fluff.
- **Verification:** The applicant journey reads like a deliberate filtering mechanism, not a generic application form.

### Task 8 — Tighten the founder journey

- **Time box:** 3-4 minutes
- **File:** `docs/spec.md`
- **What to do:** Rewrite the founder journey so it makes clear what Julien should get from the tool:
  - a faster first-pass review
  - explainable reasoning
  - better interview prompts
  - structured status movement
- **Why:** The product only works if it creates founder leverage, not just candidate polish.
- **Verification:** The founder journey makes the operational win obvious.

### Task 9 — Clarify the intentional-friction philosophy

- **Time box:** 3 minutes
- **File:** `docs/spec.md`
- **What to do:** Keep the "selective by design" idea, but tighten it so the friction serves one purpose:
  - repel low-fit, low-agency applicants
  - not punish strong people with ritual
- **Why:** This is a subtle product-design balance and easy to overdo.
- **Verification:** The spec distinguishes between useful friction and pointless friction.

### Task 10 — Add a concise product promise

- **Time box:** 2-3 minutes
- **Files:** `docs/spec.md`, `README.md`
- **What to do:** Add one sentence that can act as the canonical product promise across the repo.
- **Why:** The project needs a stable sentence that other docs can inherit.
- **Verification:** The same core sentence appears consistently in the spec and README without contradiction.

  It should probably encode all three:
  - serious founder-selection
  - attraction of strong strangers
  - explainable evaluation, not black-box hiring

---

## Phase 3 — Align architecture to the frozen product

### Task 11 — Rewrite architecture goals to mirror the spec

- **Time box:** 3-4 minutes
- **File:** `docs/architecture.md`
- **What to do:** Rewrite the opening architecture goals so they clearly serve the frozen product definition rather than a generic no-code workflow.
- **Why:** Architecture should inherit from product intent, not vice versa.
- **Verification:** Every architecture goal maps back to a specific goal in `docs/spec.md`.

### Task 12 — Separate justified MVP architecture from future convenience

- **Time box:** 4-5 minutes
- **File:** `docs/architecture.md`
- **What to do:** Mark which components are:
  - required for v1
  - optional later
  - deliberately postponed

  This includes landing page, form, automation, dashboard, scoring, and email.
- **Why:** The current architecture is solid, but a sharper boundary will prevent overbuilding.
- **Verification:** A reader can tell what must exist for launch versus what can wait.

### Task 13 — Tighten data and decision boundaries

- **Time box:** 4 minutes
- **File:** `docs/architecture.md`
- **What to do:** Make the architecture explicitly state:
  - where PII lives
  - what the LLM sees
  - what remains human judgment
  - what happens when scoring fails
- **Why:** This is where product philosophy becomes actual system boundaries.
- **Verification:** There is no ambiguity about advisory scoring versus human decision-making.

### Task 14 — Tighten the upgrade path trigger

- **Time box:** 3 minutes
- **File:** `docs/architecture.md`
- **What to do:** Rewrite the "upgrade path to coded v2" so the trigger is based on real pressure, not optimism.
- **Why:** Otherwise the repo will always feel one step away from an unnecessary rewrite.
- **Verification:** The architecture names concrete thresholds for when no-code stops being enough.

### Task 15 — Add an architecture sanity check

- **Time box:** 2-3 minutes
- **File:** `docs/architecture.md`
- **What to do:** Add a short checklist section:
  - does this component reduce founder review time?
  - does it improve signal quality?
  - does it preserve explainability?
  - does it justify its complexity?
- **Why:** This becomes a discipline gate for later changes.
- **Verification:** Future architecture ideas can be tested against a short explicit checklist.

---

## Phase 4 — Align the repo entrypoints

### Task 16 — Update the README to match the frozen product

- **Time box:** 3 minutes
- **File:** `README.md`
- **What to do:** Update the README so it describes the cofounder tool with the same language as the spec and points readers to the right order:
  1. `SPEC.md`
  2. `docs/spec.md`
  3. `docs/architecture.md`
- **Why:** The README is the repo's front door. If it drifts, everything feels less real.
- **Verification:** A new reader lands in the repo and reaches the right source-of-truth docs without confusion.

### Task 17 — Align role-track framing

- **Time box:** 3-4 minutes
- **File:** `product/questions/role_tracks.md`
- **What to do:** Rewrite this file so it reflects the exact v1 decision from the spec:
  - both tracks, clearly differentiated
  - or one track first, with the other deferred
- **Why:** This file should stop being a stub and become a downstream expression of the spec.
- **Verification:** The role-track file no longer contains unresolved ambiguity about v1 scope.

### Task 18 — Align the question-bank intent

- **Time box:** 4 minutes
- **File:** `product/questions/question_bank.md`
- **What to do:** Convert the question bank from a TODO note into a canonical list of:
  - scored questions
  - informational questions
  - deferred questions
- **Why:** The question set is part of product design, not just later content work.
- **Verification:** The question bank clearly shows what is core to founder-fit evaluation in v1.

---

## Phase 5 — Review and force one iteration

### Task 19 — Diff review for coherence

- **Time box:** 5 minutes
- **Files:** `docs/spec.md`, `docs/architecture.md`, `README.md`, `product/questions/role_tracks.md`, `product/questions/question_bank.md`
- **What to do:** Review all changed docs together and check for contradictions in:
  - product definition
  - target user
  - success criteria
  - role-track scope
  - architecture boundaries
- **Why:** The biggest risk here is not bad writing. It is quiet inconsistency.
- **Verification:** No two docs describe a materially different product.

### Task 20 — Force a review round before implementation

- **Time box:** 2 minutes
- **File:** `docs/plans/2026-03-08-cofounder-tool-plan.md`
- **What to do:** Pause after the spec/architecture rewrite and review the result before planning implementation.
- **Why:** The first version of a spec nearly always hides at least one wrong assumption.
- **Verification:** We do not move into automation planning until the rewritten docs have been annotated and corrected.

---

## Review questions for annotation

When you annotate this plan, focus on these:

1. **Is this actually a cofounder-selection tool, or is it still drifting toward recruiting software?**
2. **Is the deeper job of the product clear enough: moving from friend-convincing to stranger-attraction?**
3. **Are two role tracks really justified in v1, or is that too much too early?**
4. **What is the one success signal you care about most: quality of applicants, review speed, or one real high-fit collaborator?**
5. **What would make this feel serious to the right person and repellent to the wrong person?**
6. **What part of the current architecture feels too heavy for the actual job the tool must do?**

---

## Summary

The order I recommend is:

1. define the tool more sharply
2. define success and failure more sharply
3. tighten the user journeys and role scope
4. align architecture to that frozen product
5. align repo entrypoints
6. review the whole thing once before any build planning

That is the smallest path that gives us a real product definition instead of a promising scaffold.

---

## Next step

Open this in your editor and annotate it directly.

Push on anything that feels:

- too broad
- too implementation-first
- too much like HR software
- too ambitious for v1
- too vague to verify
