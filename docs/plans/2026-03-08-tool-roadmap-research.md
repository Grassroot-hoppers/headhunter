# Grassroot Hopper — Tool Roadmap Research

*Date: 2026-03-08*  
*Purpose: research what already exists, what "the tool" most likely means in this repo, and what order the work naturally wants to happen in before writing a real implementation plan.*

---

## First: what I think "the tool" means

There are **two different product layers** in this repository:

1. **The public Grassroot Hopper platform / movement** described in `SPEC.md`, `ROADMAP.md`, and `STATUS.md`
2. **The internal cofounder headhunter tool** described in `docs/spec.md` and `docs/architecture.md`

Right now, the phrase **"the tool"** most likely refers to the **cofounder headhunter tool**, because:

- it is the only thing in the repo already framed explicitly as a tool
- it already has a concrete product spec and architecture
- the repository README is written around that tool, not around the public community platform
- many supporting folders (`product/`, `automation/`, `docs/prompts/`, `docs/rubrics/`) are clearly scaffolded for it

If that reading is wrong, correct it before planning. The public community platform is a separate roadmap problem with different assumptions, risks, and sequencing.

---

## What already exists

### 1. Repo-level source of truth for the broader project

These files define the larger Grassroot Hopper vision:

- `SPEC.md`
- `ROADMAP.md`
- `STATUS.md`

Key things they establish:

- Grassroot Hopper is bigger than one product
- the broader public vision is community-first, cooperative, local, anti-corporate
- "aggregate, don't build" is a non-negotiable principle
- the larger product story is still exploratory and not fully locked

Important tension:

- `SPEC.md` is relatively concrete about the public product: **blogs behind a gate + event calendar + QR code + spoken password**
- `STATUS.md` still says the project is **brainstorming** and **not committing to a specific product yet**
- `ROADMAP.md` frames the early public MVP as **newsletter-first**

That means the repo contains a **resolved story at the idea level** but an **unresolved path at the execution level**.

### 2. Concrete tool spec already written

The cofounder tool is defined in:

- `docs/spec.md`
- `docs/architecture.md`
- `README.md`

This is the most mature product definition in the repo.

It is a:

- no-code-first inbound application funnel
- for selecting a technical cofounder or early founding teammate
- with AI-assisted scoring
- with human override
- built to feel selective and serious

The core promise is:

- candidates get a serious, structured application experience
- Julien gets explainable scoring, evidence snippets, and interview prompts instead of pure vibes

### 2.5. External conversation context that sharpens the tool

The shared Perplexity conversation adds useful background to how this tool was conceived.

Most important additions:

- the true bottleneck was framed as **team formation, not funding**
- Julien explicitly wanted to move away from **trying to convince friends** and toward attracting **smart strangers**
- the tool was imagined not as recruiting software, but as a way to create a **serious inbound cofounder-selection process**
- transparency about Julien's strengths and weaknesses was part of the design from the start:
  - he brings operator credibility, runway, willingness to be CEO, and real business execution
  - he does **not** bring deep coding skill and needs a pragmatic builder counterpart
- the tool itself was also meant to function as a **proof-of-concept** that AI + no-code can ship something real quickly

The conversation also reinforces the early persona split:

- **Primary:** technical cofounder / pragmatic builder
- **Secondary:** community architect / ops person

That distinction matters because it suggests the v1 tool may not want to treat both tracks as equally important from day one.

Another useful thread from that conversation is psychological, not technical:

- one founder risk is using friends as a safety mechanism
- another is avoiding strangers because rejection feels embarrassing

That means the product is doing more than collecting applications.
It is also changing the founder's behavior from:

- persuasive outreach to friends

into:

- selective attraction of strong strangers

This is a real design constraint and should influence success criteria.

### 3. Supporting scaffolding exists, but most of it is placeholder-only

Supporting files already exist in the right folders, but most are still TODO stubs:

- `product/copy/landing_page.md`
- `product/copy/application_form_copy.md`
- `product/questions/question_bank.md`
- `product/questions/role_tracks.md`
- `docs/prompts/scorer_system_prompt.md`
- `docs/prompts/scorer_user_template.md`
- `docs/prompts/json_schemas.md`
- `docs/rubrics/high_agency_rubric.md`
- `docs/rubrics/big_five_rubric.md`
- `automation/airtable_schema.md`
- `automation/data_dictionary.md`
- `automation/zapier_make_blueprint.md`

This matters because the repo is **architecturally shaped**, but not yet **operationally defined**.

In plain language: the skeleton exists, but the exact moving parts are not filled in yet.

---

## How the tool is supposed to work

From `docs/spec.md` and `docs/architecture.md`, the intended MVP flow is:

1. Candidate lands on a serious landing page
2. Candidate chooses a role track
3. Candidate fills a structured application form
4. Form sends payload into automation
5. Automation normalizes fields and creates records
6. LLM scorer evaluates the submission using a rubric
7. JSON output is validated
8. Score record is stored
9. Confirmation email is sent
10. Julien reviews applicants in a dashboard and changes status manually

Recommended MVP stack in the architecture:

- **Landing:** Framer
- **Form:** Fillout
- **Automation:** Make
- **Database/dashboard:** Airtable + Airtable Interface
- **Scoring:** LLM API with strict JSON output

Upgrade path later:

- custom landing/app frontend
- backend/API
- Postgres
- queue worker
- stronger audit/logging

So the intended approach is explicitly:

**ship the funnel with no-code tools first, then replace boundaries one by one if it proves useful**

---

## Product principles already decided

The existing docs already make several decisions. These are not open unless deliberately changed.

### For the tool

From `docs/spec.md` and `docs/architecture.md`:

- **No-code first**
- **Advisory scoring, not automated decision-making**
- **Human override always**
- **Role-track-aware scoring**
- **Explainability matters**
- **PII minimization matters**
- **Version prompts, rubrics, schemas, and scoring runs**
- **Speed to launch matters more than elegant infrastructure**

### For the broader Grassroot Hopper brand

From `SPEC.md`:

- warm, direct, slightly rebellious tone
- anti-corporate but not angry
- open-source / aggregation-first thinking
- local, human, real-world grounded

That brand tone should still show up in the cofounder tool copy. It should not read like an HR SaaS.

---

## What is already detailed versus what is still missing

### Already detailed

These are in relatively strong shape:

- the product purpose
- target users
- role tracks
- question set
- scoring dimensions
- confidence model
- red flags
- MVP flow
- upgrade path
- privacy principles

### Still missing

These are still unresolved or empty in the working docs:

#### Copy layer

- real landing page copy
- real form helper text
- completion page copy
- confirmation email copy in final location

#### Data contract layer

- exact field names
- which system owns each field
- which fields are PII
- canonical payload shape from form to automation to LLM

#### Scoring layer

- final system prompt
- final user prompt template
- actual JSON schema
- repair flow for invalid JSON
- concrete examples for rubrics

#### Automation layer

- exact Make vs Zapier choice
- field mapping details
- retries and failure states
- notification rules
- validation implementation details

#### Ops layer

- review cadence
- who handles follow-up and declines
- how synthetic tests will be written and stored
- how prompt/rubric changes are versioned in practice

---

## Key dependencies

The tool depends on decisions in this order:

1. **Product definition**
   - what the landing page promises
   - what the form asks
   - what "good applicant" means

2. **Data contract**
   - field names
   - schema
   - status enums
   - scoring output structure

3. **Automation contract**
   - what the form sends
   - what the scorer receives
   - what Airtable stores

4. **Tool-specific implementation**
   - Fillout/Tally setup
   - Make scenario
   - Airtable base
   - email and notifications

This dependency order is critical.

If the team skips straight to Make/Airtable setup before freezing the data contract, the no-code stack will become fragile fast.

---

## The main gotchas I found

### 1. The repo has context drift

There is a real risk of mixing up:

- the public cooperative creative platform
- the internal cofounder funnel tool

They are related, but they are not the same product. Planning them together would blur priorities and produce a messy roadmap.

### 2. The implementation docs are mostly placeholders

The spec and architecture are strong. The working files that someone would actually build from are mostly not written yet.

That means the next roadmap should **not** start with "build the automation."  
It should start with **turn the placeholders into executable definitions.**

### 3. The architecture depends on structured outputs

The whole no-code scoring setup assumes:

- strict JSON output
- reliable validation
- clean field naming
- minimal ambiguity in question formatting

If the prompt/schema work is sloppy, the automation layer will be painful.

### 4. The founder-facing dashboard depends on upstream discipline

Airtable can feel fast at first, but only if:

- statuses are clearly defined
- linked records are consistent
- fields are named once and reused everywhere

Without that, the dashboard becomes a junk drawer.

### 5. GDPR is easy to gesture at and easy to get sloppy about

The docs already say the right things:

- minimize PII
- keep emails out of scorer payloads
- log consent and deletion requests

But the actual implementation docs do not yet pin down:

- exact retention behavior
- deletion workflow ownership
- vendor-by-vendor storage decisions

### 6. The tool should not accidentally look like generic recruiting software

The spec is strongest when it feels:

- selective
- candid
- serious
- founder-led

If the copy becomes polished-but-generic, it will lose the project's edge.

### 7. The tool has a founder-psychology job, not just a candidate-evaluation job

The external conversation makes this clearer than the current repo docs do.

The tool is partly a system for evaluating candidates, yes.
But it is also a system for helping Julien:

- stop relying on friend-convincing
- become legible to strong strangers
- present himself as a serious operator with a real offer
- make "joining this" feel like entering a serious process rather than doing him a favor

If this layer is ignored, the tool risks becoming technically coherent but strategically weak.

### 8. The funnel is downstream of a team-design decision

The latest planning note adds another important correction:

before the cofounder tool can be designed well, the project needs a clearer answer to:

- what Julien can realistically contribute himself
- what the **minimum viable team** actually is
- which roles are true founding roles
- which roles are advisory
- which roles are support / operations / later

This matters because the tool should not be asked to solve every staffing need.

For example, the current "CFO" discussion appears to mix at least three different needs:

1. **strategic finance judgment**  
   Example: startup/co-op/social-project experience, board-level advice, capital strategy, subsidy logic

2. **finance/admin operations**  
   Example: invoices, tax coordination, accountant interface, routine administration

3. **grants/incubator/funding process work**  
   Example: subsidy applications, grant writing support, incubator relationships

Those are not automatically the same role.

This implies a better planning order:

1. founder reality map
2. minimum viable team
3. role classification
4. cofounder tool scope

It also adds a cross-role requirement that was not explicit enough before:

every serious role should probably be screened for:

- high agency
- judgment
- AI fluency
- ability to ship at 80%
- ability to avoid perfectionism and AI-loop time waste

### 9. Unbundle judgment from execution

The newly added Perplexity research contributes a very strong team-design principle:

> **unbundle judgment from execution**

This maps well to the AI-native startup thesis already present in the repo.

The practical interpretation is:

- let AI + fast operators produce first drafts, reports, models, and routine outputs
- pay experienced professionals for:
  - strategic framing
  - edge-case detection
  - red-teaming
  - stakeholder confidence
  - compliance-sensitive review

Not for:

- spending 10 days creating something the team can generate in 10 minutes and then refine

This suggests a default posture for expensive senior profiles:

- **do not buy the whole bundle by default**
- buy only the part that is still scarce

For team design, this likely means:

1. **core builders/operators** create
2. **senior experts** audit, redirect, sign off, or lend credibility when needed

This is especially relevant to the current finance discussion.

The note strengthens the idea that a veteran finance person may be better framed as:

- fractional advisor
- board/advisory member
- paid reviewer
- occasional strategic red team

rather than immediate full-time founding operator.

### 10. Gravitas is real, but full-time gravitas may be too expensive

The new research also sharpens another distinction:

- **gravitas is useful**
- **full-time gravitas may create drag**

Why gravitas matters:

- investors, banks, and institutions still respond to credible senior profiles
- an experienced finance person can create trust and open conversations

Why full-time embedding may be wrong:

- it can slow an AI-native team to the pace of traditional executive workflows
- it can create cultural friction if the veteran role is mostly benchmarking or second-guessing fast operators
- it may force the startup to overpay for bundled execution it does not need

This suggests a better default:

- **rent gravitas**
- do not necessarily employ it

The Kaptain Finance search result reinforces that this is a real market pattern in Belgium:

- externalized CFO services already exist
- they are explicitly sold as part-time/fractional financial leadership rather than full-time internal hires

More specifically, **Kaptain Finance should now be treated as a named decision branch in the planning**, not just as generic market evidence.

Why:

- Julien already has a real relationship/history here
- the profile seems to combine:
  - strategic finance experience
  - startup/SME guidance
  - externalized CFO framing
- the likely value is not basic spreadsheet labor
- the likely value is:
  - judgment
  - credibility
  - financial structuring
  - selective oversight

So the planning question is no longer just:

- "should we use a fractional finance model?"

It is also:

- "should **Kaptain Finance / Laureen** be the concrete embodiment of that model for this project?"

That still does **not** mean "locked in as the final answer."
But it **does** mean she should appear explicitly in the finance-role comparison as:

1. a serious candidate for the **strategic finance advisor / board / fractional** branch
2. not merely an abstract example
3. probably **not** the default answer for routine finance-admin execution unless evidence says otherwise

### 11. Human-AI A/B testing should not become a speed tax

Another useful idea from the research:

running a senior human and AI in parallel on the same output may be intellectually interesting, but it can become a major velocity tax if the team waits for the slower control group.

The better pattern is probably:

1. AI/team produce baseline quickly
2. senior human audits and stress-tests it
3. lessons are captured about AI blind spots

This preserves speed while still generating organizational learning about where human judgment adds value.

For planning purposes, this means the startup may want:

- **AI-first execution**
- **human red-team review**

not:

- **two full production lanes running in parallel**

### 12. The technical cofounder profile has sharpened

The latest founder note materially improves the target profile for the technical cofounder.

Important correction:

- high repo count and nonstop AI experimentation are **not enough**
- Julien explicitly identified his own blind spot as:
  - shipping many things
  - finishing too few of them

That means the real counterpart is not just:

- AI-native
- obsessed
- high-agency

It is also:

- **close-the-loop oriented**
- has **finished products**, not just prototypes
- understands the boring final 20% that turns a demo into a usable thing
- knows how to stabilize, polish, simplify, and ship

This changes the technical profile from:

- "maniac builder with lots to prove"

to:

- **product-closing builder with strong finish discipline**

The latest note also adds a useful life-stage filter.

The ideal technical cofounder may be:

- someone with a real career behind them
- someone who has built enough to know what "finished" means
- someone who now recognizes this is their moment to cofound
- someone who lacks founder runway, CEO energy, or business-driving force

This is highly complementary to Julien.

Julien brings:

- CEO energy
- conviction
- operator drive
- willingness to push externally

The technical cofounder should bring:

- closure
- technical product maturity
- build-to-finish discipline
- less need to invent the company story alone

This suggests the cofounder tool should test for:

- evidence of shipping beyond MVP theater
- examples of maintenance, iteration, polishing, or launch completion
- ability to finish boring work
- ability to turn many possibilities into one completed outcome

not just:

- velocity
- excitement
- experimentation

---

## The natural roadmap order emerging from the docs

This is **not** the final implementation plan yet. It is the sequencing logic I see after reading the repo.

### Phase A — Lock scope

Goal: decide exactly which tool is being planned and what counts as MVP success.

Order:

1. Confirm the target is the **cofounder headhunter tool**
2. Freeze the MVP promise
3. Freeze role tracks and success criteria

Why first:

- otherwise every later doc will drift

### Phase B — Lock the content and scoring contract

Goal: define the words and the data before building anything.

Order:

1. finalize landing page copy
2. finalize application form copy
3. copy the question set into canonical product files
4. finalize role-track framing
5. define JSON output schema
6. draft scorer system prompt
7. draft scorer user template
8. expand rubrics enough to score consistently

Why before Airtable/Make:

- the form fields and scorer schema define the whole plumbing

### Phase C — Lock the operational data model

Goal: define how records move through the system.

Order:

1. finalize data dictionary
2. finalize Airtable tables and field types
3. finalize status enums
4. define prompt version storage
5. define score record shape

Why here:

- this is the translation layer between product definition and automation

### Phase D — Design the automation

Goal: map the flow in detail before building it.

Order:

1. choose Make or Zapier
2. define webhook payload mapping
3. define validation and repair flow
4. define retry behavior
5. define notification behavior

Why not earlier:

- automation details should reflect already-frozen fields and schemas

### Phase E — Build the MVP

Goal: create the actual working funnel.

Order:

1. publish landing page
2. build form
3. create Airtable base
4. build Make scenario
5. connect LLM scoring
6. create Airtable Interface
7. wire confirmation email and founder notification

### Phase F — Test before using it for real people

Goal: confirm the system is serious, not merely assembled.

Order:

1. run synthetic applicants through the flow
2. test invalid JSON and retry paths
3. test missing data cases
4. test low-confidence cases
5. run 1-3 friendly real testers
6. tighten prompt/rubric/calibration

### Phase G — Operate and learn

Goal: treat this as a live recruiting system, not a static artifact.

Order:

1. review first applicants manually
2. compare scoring against Julien's judgment
3. track false positives / false negatives
4. adjust prompts and weights carefully
5. decide what deserves a coded v2 later

---

## What I would not do first

These would be the wrong first moves given the current state of the repo:

- building a custom web app
- jumping into Postgres
- designing advanced analytics
- adding applicant login/status tracking
- experimenting with many scoring models at once
- drafting public-platform roadmap and tool roadmap in the same document

The smallest credible path is already in the docs. The missing piece is not architecture creativity. It is **discipline and sequencing**.

---

## My current read of the highest-leverage next step

Before writing a full plan, the highest-leverage clarification is:

> Are we planning the **cofounder headhunter tool** first, or the broader **public Grassroot Hopper platform** first?

If the answer is the cofounder tool, the roadmap should start with:

1. canonical copy
2. canonical questions
3. canonical schema
4. canonical Airtable/automation mapping

And before even that, the spec should clearly encode four things from the external conversation:

1. the tool exists to solve **team formation**
2. the core move is **friends -> strangers**
3. the first likely priority persona is the **pragmatic builder**
4. the tool itself is meant to signal **execution credibility**

If the answer is the public platform instead, we should stop and write a different research file, because the current repo has conflicting product assumptions there.

---

## Summary

The repository already contains a believable MVP architecture for one concrete tool: the **cofounder headhunter funnel**.

What exists:

- strong spec
- strong architecture
- clear no-code-first philosophy
- sensible upgrade path

What does not yet exist:

- executable implementation docs
- finalized schema and prompts
- finalized copy
- finalized automation mapping

So the correct roadmap logic is:

**clarify target tool -> lock content/scoring contract -> lock data contract -> design automation -> build -> test -> calibrate**

Not:

**start wiring tools immediately and hope the definitions settle later**

---

## What I need from you before planning

Read this. Correct anything I got wrong before we plan.
