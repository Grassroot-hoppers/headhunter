# Grassroot Hopper — Cofounder Tool + Team Design Plan

*Date: 2026-03-08*  
*Purpose: lock the founder reality, minimum viable team, and cofounder tool design before any implementation work.*

---

## What this round is for

This planning round is **not** about building the funnel yet.

It is about answering, in a way that survives contact with real execution:

1. **What can Julien realistically provide himself?**
2. **What does the minimum viable team actually need to contain?**
3. **Which roles are core, which are advisory, and which belong later?**
4. **What is the cofounder tool, exactly?**
5. **What problem is it solving?**
6. **What does success look like?**
7. **What architecture is justified by that definition, and what is premature?**

If we do this right, the repo should stop feeling like "good ideas plus placeholders" and start feeling like one coherent product.

Additional context from the earlier Perplexity conversation sharpens this further:

- this tool exists because the real bottleneck is **team formation**, not funding
- it should help Julien move from **convincing friends** to attracting **high-agency strangers**
- transparency about what Julien brings and what he lacks is not a side note; it is part of the product
- the tool itself should quietly prove that Julien can ship something serious with AI/no-code leverage

Additional context from the latest notes sharpens it again:

- the real planning problem is a **mix of multiple plans**, not just a funnel plan
- before designing the funnel, we need a **founder reality map** and a **minimum viable team model**
- "CFO" is likely being used to describe more than one job:
  - strategic finance judgment / board-level advisory
  - finance and admin operations
  - grants / subsidies / incubator navigation
- every serious role should be filtered through the same operating standard:
  - high agency
  - good judgment
  - AI fluency
  - knows when 80% is enough
  - does not get trapped in hallucination loops or perfectionist last-mile waste

The newest research adds one more strong operating principle:

- expensive senior people should often be used as **editors / red-teamers / advisors**
- not automatically as full-time creators of first-draft deliverables
- the startup should try to **unbundle judgment from execution**
- gravitas is useful, but may be best rented fractionally rather than bought full-time

The latest founder correction sharpens the technical-cofounder target even further:

- Julien's blind spot is **starting and shipping many things without reliably finishing them**
- so the core technical need is **not** just AI intensity or experimentation
- it is a **close-the-loop CTO / product-finisher**
- ideally someone with real product/career experience who feels this is their moment to cofound
- someone who may lack runway, CEO drive, or founder-front energy, but does know how to turn demos into finished products

---

## End state for this plan

When this plan is complete, these statements should all be true:

- there is a clear written map of Julien's realistic contribution, strengths, weaknesses, and constraints
- there is a clear written definition of the **minimum viable team**
- each needed role is classified as **core founding role**, **advisor/board role**, **contractor/part-time support**, or **later**
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
- making final compensation offers to specific people

Those are next-step tasks. This round is for **definition first**.

---

## Core principle for sequencing

The order here is intentional:

**founder reality -> minimum viable team -> role prioritization -> tool definition -> success definition -> design boundaries -> architecture alignment -> repo alignment**

Not:

**tool choices -> implementation details -> backfilled product reasoning**

---

## Phase 0 — Define founder reality and minimum viable team

### Task 0.1 — Write the founder contribution map

- **Time box:** 5-8 minutes
- **File:** `docs/spec.md`
- **What to do:** Add a short section that states, plainly:
  - what Julien can realistically provide now
  - what he is unusually good at
  - what he should not pretend to be
  - where he has leverage
  - where he is currently a bottleneck

  Include both capability and energy constraints.
- **Why:** The tool cannot be designed well if the founder offer is still blurry.
- **Verification:** A stranger could read the section and understand what partnership with Julien actually means in practice.

### Task 0.2 — Decompose the team need into actual jobs

- **Time box:** 5-7 minutes
- **Files:** `docs/spec.md`, `product/questions/role_tracks.md`
- **What to do:** Split vague role labels into concrete jobs. Especially separate:
  - strategic finance / judgment / board-level advisory
  - finance-admin operations
  - technical product building
  - grants / subsidies / incubator relationship work
  - community / events / operations

  Avoid using one title to hide multiple jobs.
- **Why:** "I need a CFO" may be true, but the current description mixes very different kinds of work and leverage.
- **Verification:** Each role has a job description defined by outcomes, not prestige titles.

### Task 0.3 — Define the minimum viable team

- **Time box:** 5-8 minutes
- **File:** `docs/spec.md`
- **What to do:** Add a section that answers:
  - what is the smallest team that can genuinely move Grassroot Hopper forward now
  - which role is absolutely essential first
  - which role is valuable but can be advisory
  - which role can be covered by consulting or part-time help
  - which role should wait until there is traction
- **Why:** This is the upstream decision that tells us what the tool should optimize for.
- **Verification:** The minimum viable team is small, believable, and clearly prioritized.

  The current working hypothesis should be tested explicitly:
  - **core founding pair:** Julien + close-the-loop technical cofounder
  - **fractional shell:** finance advisor + freelance ops/admin support

### Task 0.4 — Classify each role by relationship type

- **Time box:** 4-5 minutes
- **File:** `docs/spec.md`
- **What to do:** For each important role, classify it as one of:
  - cofounder / founding team
  - advisor / board member
  - contractor / specialist
  - part-time operator
  - later-stage hire

  Apply this to the finance function in particular.
- **Why:** Not every needed function belongs in the same funnel.
- **Verification:** It is obvious which profiles the cofounder tool should target directly and which should be sourced differently.

  Add one more question for each role:
  - is this person mainly needed to **create**, or mainly needed to **judge / audit / guide / signal credibility**?

### Task 0.5 — Define the universal team bar

- **Time box:** 4 minutes
- **Files:** `docs/spec.md`, `product/questions/role_tracks.md`
- **What to do:** Add a short set of non-negotiable operating traits for all meaningful roles:
  - high agency
  - judgment under ambiguity
  - AI leverage
  - fast good-enough shipping
  - ability to avoid hallucination loops and perfectionist waste
- **Why:** This is one of the clearest new requirements from your note and should shape both role design and screening.
- **Verification:** Every later role description inherits the same operating standard.

  Add one more filter for the technical cofounder role specifically:
  - evidence of **closure**
  - evidence of finishing
  - evidence of surviving the boring final 20%

### Task 0.6 — Explicitly resolve the finance question

- **Time box:** 5 minutes
- **File:** `docs/spec.md`
- **What to do:** Add a planning note that tests three distinct possibilities:
  1. strategic finance advisor with equity / board role
  2. Julien handles finance/admin directly at first, with on-demand consulting
  3. finance/admin ops is delegated later to a lighter-weight operator rather than a full CFO profile

  Add a fourth lens to compare them:
  - which parts require **judgment**
  - which parts are mostly **execution**
  - which parts require **certification / sign-off / credibility**

  The goal is not to decide compensation yet. The goal is to decide what kind of role this really is.
- **Why:** This is the clearest concrete role ambiguity in the current planning.
- **Verification:** The spec no longer uses "CFO" as shorthand for several unrelated needs.

  Make this concrete by naming the current strongest candidate path:
  - **Kaptain Finance / Laureen** as the real-world example of the strategic-finance-advisor branch

  Explicitly test whether that path should mean:
  1. hourly consulting only
  2. fractional advisory relationship
  3. symbolic board/advisory seat plus possible equity participation
  4. not used for routine execution-heavy finance work

### Task 0.6b — Add a named-candidate finance note

- **Time box:** 3-4 minutes
- **File:** `docs/spec.md`
- **What to do:** Add a short note that Kaptain Finance is not just evidence of a model, but a concrete candidate to evaluate against the finance-role framework.
- **Why:** This prevents the planning from staying too abstract when there is already a real person/company in view.
- **Verification:** The spec names Kaptain Finance explicitly as a candidate path while still separating:
  - model choice
  - person choice
  - compensation structure

### Task 0.7 — Add the "judgment vs execution" test

- **Time box:** 4-5 minutes
- **File:** `docs/spec.md`
- **What to do:** Add a short decision rule for role design:
  - if AI + a high-agency operator can execute the deliverable fast, do not default to buying a senior full-time creator
  - use senior people for audit, edge cases, sign-off, stakeholder confidence, and strategic correction
- **Why:** This principle may become one of the core design rules of the whole team.
- **Verification:** At least one current ambiguous role is clarified using this test.

### Task 0.8 — Add the "red team, don't parallelize" rule

- **Time box:** 3-4 minutes
- **File:** `docs/spec.md`
- **What to do:** Add a note that human-AI comparison should default to:
  - AI/team baseline first
  - senior human review second

  Not:
  - waiting for two full parallel production lanes unless there is a very specific reason
- **Why:** This preserves speed while still learning where expert judgment matters.
- **Verification:** The plan explicitly protects velocity from turning into a human-control-group bottleneck.

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

  The wording should now reflect that the main target is not just "technical cofounder" in the abstract, but:
  - a **technical closer**
  - a **product-finisher**
  - a partner who complements Julien's tendency to start faster than he closes

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

  This should now be written against the founder contribution map from Phase 0, not from intuition alone.

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

  The latest note adds a second filter:
  - some roles may belong **outside** the cofounder funnel entirely because they are advisory or support, not founding roles

  And it sharpens the technical persona itself:
  - not just "AI guy shipping constantly"
  - but "builder who has actually finished products and knows closure"

### Task 6.5 — Add a career-stage filter for the CTO path

- **Time box:** 3-4 minutes
- **Files:** `docs/spec.md`, `product/questions/role_tracks.md`, `product/questions/question_bank.md`
- **What to do:** Add a note that the ideal technical cofounder may be:
  - experienced enough to know what finished looks like
  - early enough in founder journey to still be hungry
  - lacking CEO energy, runway, or front-person drive
  - now ready to cofound because timing finally makes sense
- **Why:** This is a much sharper complementarity hypothesis than "young AI genius."
- **Verification:** The role description and questions screen for life-stage readiness, not just technical obsession.

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

  It should also make clear which kinds of people Julien should **not** be using the tool for.

  It should also make clear that Julien is specifically trying to find a counterpart for his own blind spot:
  - someone who closes
  - someone who finishes
  - someone who can help convert motion into completed product

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

1. **What is the true minimum viable team?**
2. **Which role is truly cofounder-critical first, and which roles are advisory or later?**
3. **Is "CFO" actually one role here, or three different jobs wearing one label?**
4. **Which roles require creation, and which mostly require judgment, audit, or gravitas?**
5. **Where should gravitas be rented fractionally instead of bought full-time?**
6. **Should Kaptain Finance be treated as the concrete strategic-finance candidate path right now?**
7. **If yes, is the right shape hourly advisor, fractional partner, or symbolic board/advisory seat with optional equity?**
8. **Is the technical target now defined sharply enough as a close-the-loop product finisher, not just a prolific AI builder?**
9. **Does the role description screen for real closure and finished products rather than repo count and hype?**
10. **Is this actually a cofounder-selection tool, or is it still drifting toward recruiting software?**
11. **Is the deeper job of the product clear enough: moving from friend-convincing to stranger-attraction?**
12. **Are two role tracks really justified in v1, or is that too much too early?**
13. **What is the one success signal you care about most: quality of applicants, review speed, or one real high-fit collaborator?**
14. **What would make this feel serious to the right person and repellent to the wrong person?**
15. **What part of the current architecture feels too heavy for the actual job the tool must do?**

---

## Summary

The order I recommend is:

1. define Julien's real contribution and constraints
2. define the minimum viable team
3. classify roles into founder / advisor / support / later
4. define the tool more sharply
5. define success and failure more sharply
6. tighten the user journeys and role scope
7. align architecture to that frozen product
8. align repo entrypoints
9. review the whole thing once before any build planning

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
