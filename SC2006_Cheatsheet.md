# SC2006 Software Engineering — Cheatsheet

One page per chapter. Each page answers the chapter's learning objectives. Lines marked **[Insert diagram: …]** are empty slots for your own pictures.

| Ch | Topic | Ch | Topic |
|---|---|---|---|
| 1 | Introduction | 9 | Agile & XP |
| 2 | Elicitation I: FR / NFR | 10 | Scrum |
| 3 | Elicitation II: Use Case Diagram | 11 | System Design & Architecture |
| 4 | Elicitation III: Use Case Description | 12 | Object Design & Design Patterns |
| 5 | Analysis: Class Diagram | 13 | MVC |
| 6 | Analysis: State Machine & Activity | 14 | Testing I: EC & BV (black-box) |
| 7 | Writing the SRS | 15 | Testing II: Control Flow (white-box) |
| 8 | Software Processes | 16 | Software Maintenance |
| | | **T** | **Terminology (last page)** |

<div style="page-break-after: always;"></div>

## Ch 1 — Introduction to Software Engineering

**LO1. Define SE.** *"The production of maintainable, fault-free software that meets the user's requirements and is delivered on time and within budget."* That's four constraints at once: quality, maintainability, requirements fit, and schedule plus budget.

**LO2. Engineering activities (the building analogy).**

| Construction | Software |
|---|---|
| Purpose of the building | Requirements elicitation |
| Rooms, size, look | Requirements specification |
| Design, materials, plumbing | System & object design |
| Planning, scheduling | Project management |
| Simulation & testing | Verification & validation |
| Construction | Implementation |
| Operation & maintenance | Deployment, evolution |

**LO3. SDLC phases → work products → milestone.**

| Phase | Work products | Milestone |
|---|---|---|
| Requirements | SRS, prototype | Requirements Review |
| Design | Design doc, interface doc, test cases, models | Preliminary & Final Design Reviews |
| Implementation | Source code, build | — |
| Testing | Tech docs, user manual, test report | User Acceptance Test |
| Maintenance | Change requests, bug reports, patches | General Availability Release |

**LO4. SDLC vs PLC.** The **SDLC** is the pipeline that produces the product. The **PLC** (Project Life Cycle) wraps around it and produces control: Plan → Organise → WBS & Schedule → Supervise → Report → Quality Control → Close. Both run at the same time.

**LO5. Course map.** Requirements Elicitation & Analysis → Process Models → Agile → System & Object Design → Testing & Maintenance.

> **[Insert diagram: SDLC phases with work products and milestones]**

<div style="page-break-after: always;"></div>

## Ch 2 — Requirements Elicitation I: Functional & Non-Functional Requirements

**LO1. Where requirements sit.** Elicit → Validate → Review. Elicitation produces the **Project Mission Statement (PMS)**; review produces the **SRS**.

**LO2. Project Mission Statement.** Two or three sentences covering (1) the **problem/scope**, (2) the **stakeholders**, and (3) the **outcomes and benefits**.

**LO3. Elicitation techniques.** Interview · Observation · Workshop · Legacy product study · Competitive product study · Prototype. You use them to learn the problem domain and study user tasks.

**LO4. FR vs NFR.**
- **FR** = what the system **must do**, i.e. inputs mapped to outputs. Three kinds: system functionality, information to be processed, interfaces with other systems.
- **NFR** = **properties** the system must have. Lecture categories: **U**sability, **R**eliability, **P**erformance, **S**upportability (plus security, availability, portability…).
- *"Display the user's office"* is an FR. *"…within 2 seconds"* is an NFR. One sentence can hold both, which is why you atomise first.

**LO5. Three documentation qualities.**
- **Atomic:** one statement, one requirement. Use hierarchical numbering (1.1, 1.1.1). Watch for "or", "and" and comma lists, which hide several requirements.
- **Verifiable:** you can write a pass/fail test for it. ✗ "user-friendly" → ✓ "80% of first-time users enter a query within 2 min".
- **Traceable:** you can follow it from the SRS through design, code and tests, and see its dependencies on other requirements.

**LO6. Writing style.** Complete, simple, precise sentences in **active voice**, with terms defined and used consistently.

**LO7. Validation.** **Review** (walkthrough, inspection) against completeness, consistency, unambiguity and correctness, plus **prototype**. Stakeholders confirm their needs are met; developers confirm they understood.

**LO8. UI prototypes.** Storyboard · still images · interactive prototype.

**LO9. Data Dictionary.** A glossary of **problem-domain** terms that all stakeholders agree on. `Silo` belongs in it; `silo_table` does not.

**Trap:** never guess a missing detail. Raise it as a **TBD** with the client.

> **[Insert diagram: Elicit → Validate → Review, with PMS and SRS]**

<div style="page-break-after: always;"></div>

## Ch 3 — Requirements Elicitation II: Use Case Diagrams

**LO1. UML.** A graphical notation, with text annotations, for specifying, documenting and communicating structure and behaviour. It's **not** a programming language. Its value is **standardisation**. Current version is 2.5 (2015).

**LO2. Diagram types.** *Structure:* Class, Component, Object, Composite, Deployment, Package. *Behaviour:* Activity, Use Case, State Machine, Interaction (Sequence, Communication, Timing, Overview). This course uses Use Case, Class, State Machine, Activity and Sequence. Use only the ones you need.

**LO3. Lifecycle chain.** Use case model → expressed in application domain objects → structured by subsystems → implemented by solution objects → realised by source code → verified by test cases.

**LO4. FR vs use case.** An FR says **what**. A use case says **how** actors interact. FRs are the starting point for use case modelling.

**LO5. Use Case Model = Diagram (static) + Description (dynamic).**

**LO6. Elements.** **Actor** (stick figure, outside the system) · **Use case** (ellipse, a result of value to an actor) · **Association** (solid line) · **System boundary** (rectangle).

**LO7. Relationships between use cases.**

| | Meaning | When |
|---|---|---|
| `<<include>>` | Functional decomposition, or reuse. The base use case **always** runs the included one | e.g. Loan Material includes Verify Member |
| `<<extend>>` | **Optional** addition, only in exceptional cases. The arrow points to the **base** | e.g. Help extends Report Emergency |
| Generalisation | "Kind of". Works for actors (Manager ▷ Operator) or use cases | Removes duplicate lines |

**LO8. Three-pass method (from FRs).** (1) **Actors**: who or what external thing takes part. (2) **Use cases**: verb + object. (3) **Associations**: the words *before, when, using, if*. "before" points to include; "when there are network issues" points to extend. There is **no single correct diagram**, but you must justify yours.

**Traps (from my mistake log):**
- An actor is **outside** the boundary and talks to the system directly. "System", "Silo" and "Transaction log" are data, not actors.
- Don't draw a flowchart. Steps belong in the description.
- Keep one level of abstraction. "Click Submit" is not a use case.

> **[Insert diagram: Library system use case diagram with include/extend]**

> **[Insert diagram: Actor generalisation example]**

<div style="page-break-after: always;"></div>

## Ch 4 — Requirements Elicitation III: Use Case Descriptions

**LO1. Required content.**
- **Participating actors.** The **initiating** actor triggers the use case. If a system event or another use case triggers it, the initiating actor is **NULL**.
- **Entry (pre-) conditions** and **exit (post-) conditions.**
- **Flow of events:** the main success path.
- **Alternative flows:** variations or errors that **return to the main flow**.
- **Exceptions:** situations that **end the use case in failure**.

> Alternative flow = rejoins the main flow. Exception = terminates unsuccessfully.

**LO2. Write flows as alternating actor and system steps (ATM).**
1. Customer inserts card. 2. ATM asks for PIN. 3. Customer enters PIN. 4. ATM verifies with the Bank. 5. If valid, ATM asks for an amount. 6. Customer enters amount. 7. ATM checks funds. 8. If sufficient, ATM outputs cash, card and receipt. 9. Customer takes them.
- *Entry:* has a bank account **and** has a card and PIN. *Exit:* gets cash **or** gets an explanation.

**LO3. Label branches by step.**
- `AF-S5`: invalid PIN → show message → **return to step 2**.
- `AF-S8`: insufficient funds → **return to step 6**.
- `EX1`: wrong PIN 3 times → card suspended. `EX2`: ATM out of cash → card not accepted.

**LO4. Include inside the text.** *"The system uses the included use case Login to verify the Registrar."*

**LO5. Template fields.** ID · Name · Created/Updated by & dates · Actor · Description · Pre/Postconditions · Priority · Frequency · Flow · Alt flows · Exceptions · Includes · Special requirements · Assumptions · Notes.

**LO6. Elicitation deliverables.** FRs · Use case model (diagram + descriptions) · NFRs · Data dictionary · UI prototype.

**LO7. Two-step iterative process.**
- **Step 1, team only:** atomise requirements → identify actors → identify main use cases → identify NFRs → start the data dictionary → list **TBDs** (don't guess).
- **Step 2, meet the client:** set and agree the agenda first. Walk through the requirements and dictionary, clear the TBDs, and take new requirements.
- Repeat until everything is agreed. Keep meetings few and productive.

> **[Insert diagram: Use case description template filled in for ATM Withdraw]**

<div style="page-break-after: always;"></div>

## Ch 5 — Requirements Analysis: Conceptual Model & Class Diagrams

**LO1. Elicitation vs analysis.** Elicitation finds out what the customer wants and outputs **actors and use cases**. Analysis produces a correct, complete, consistent, unambiguous model: a **conceptual** (structure) model and a **dynamic** (behaviour) model.

**LO2. Why model.** It clarifies structure and dynamics, **validates** the requirements, and underpins the solution model.

**LO3. Two goals.** Conceptual model: find the **objects** and their **roles**. Dynamic model: work out **how** use cases are fulfilled and **which objects** do the work (Ch 6).

**LO4. Constituents.** **Object** (has state and behaviour) · **Operation** (how objects communicate) · **Attribute** (holds state).

**LO5. A UML class.** Three compartments: **name (the only mandatory one)**, attributes (each with a type), operations (each with a signature).

**LO6. Multiplicity.** How many objects one instance can reference: `1`, `1..6`, `*`. Every association end needs one.

**LO7. Relationships (heavily examined).**

| Relationship | Meaning | Notation |
|---|---|---|
| Generalisation, class parent | is-a | solid line, **black** arrowhead |
| Generalisation, abstract parent | is-a | solid line, **white** arrowhead |
| Realisation, interface parent | implements | **dashed** line, white arrowhead |
| Aggregation | **is part of** (part can exist alone) | **white** diamond at the whole (Book ◇ Page) |
| Composition | **entirely made of**, parts die with the whole | **black** diamond (Car ◆ Engine) |
| Dependency | **uses temporarily** | **dotted** arrow, client → supplier |

**LO8. Four activities.** Identify classes → attributes → operations → associations. The class diagram is **derived from** the use case model.

**LO9. Finding classes (noun extraction).** Look for recurring nouns in the use cases, real-world entities the system tracks, and data-dictionary terms. Then prune:
- No state to remember? Not an entity class.
- No state and no behaviour? It's an **attribute** (Weight, ArrivalDate).
- Outside the boundary? It's an actor. (It may still have a matching entity record.)

**LO10. Stereotypes.** `<<entity>>` = information **tracked** · `<<boundary>>` = actor–system **interaction** · `<<control>>` = **logic** for one use case (usually one controller per use case).

**LO11–12. Dependencies can carry stereotypes:** `<<read>>`, `<<call>>`, `<<signal>>`.

**Trap:** keep it a problem-domain model. No DB tables, no Manager/Helper classes, no getters and setters. Don't inherit just to express a value; use an attribute.

> **[Insert diagram: Relationship notation (generalisation / aggregation / composition / dependency)]**

> **[Insert diagram: Boundary–control–entity class diagram example]**

<div style="page-break-after: always;"></div>

## Ch 6 — Requirements Analysis: Dynamic Models

### State Machine Diagrams
**LO1. What it models.** A system or object by the **states** it can be in. A state is a *stable condition* that lasts until some action moves the system to another state.

**LO2. A state.** A rounded rectangle with internal actions:
- `entry /` runs once on entering
- `exit /` runs once on leaving
- `do /` runs **continuously** while in the state

**LO3. Transitions.** `event(args) [guard] / action`. A transition is **instantaneous**. The diagram has a start node, and an end node unless it loops forever.

**LO4. Dialog map.** A state machine for a UI: **state = screen**, **transition = UI control**. It finds missing or wrong navigation paths early, while they're cheap to fix, and shows reuse and redundancy. Prototyping reduces the risk of building the wrong product, or building the right product badly.

**LO5. Examples.** Vending machine (Idle → Accumulate → Vend → ReturnChange, with guards) · Student Management screens · Stopwatch.

### Activity Diagrams
**LO6. Elements.** Activity (rounded rectangle) · control-flow arrows · **fork** (1 in, many concurrent out) · **join** (many in, 1 out) · **decision** (branch on a condition) · **merge**.

**LO7. Examples.** Laundry: fork into wash whites ∥ wash darks, then join. Dryer: a decision loop on `[still wet]`.

**LO8. Activity vs state machine (standard exam question).** An **activity diagram** is a flowchart of the **workflow**: what happens next. A **state machine** shows **what condition the thing is in** and what moves it.

**LO9. 10-step elicitation + analysis process.** Study spec → draft use cases, dictionary and uncertainty list → review with client → refine (loop until initial agreement) → identify classes → add associations and dynamic diagrams → review → update use cases → refine diagrams (loop until agreed) → **sign off the SRS**.

**LO10. SRS outline.** Product description · FRs · NFRs · Interface requirements · Data dictionary (details in Ch 7).

**Projector tutorial traps:** "press LAPTOP" is an **event**, not a state. Blinking red is `do /`. The beep is `entry /`. Warm-up → Ready needs no user event (`[warm-up complete]`). Still model OFF even though Jane doesn't press it.

> **[Insert diagram: Vending machine state machine]**

> **[Insert diagram: Projector controller state machine]**

> **[Insert diagram: Activity diagram with fork/join and decision]**

<div style="page-break-after: always;"></div>

## Ch 7 — Writing the SRS

**LO1. Place.** Elicit (gives the PMS) → Analyse (gives the analysis model) → Validate (gives the **SRS**).

**LO2. What an SRS is.**
1. The output of elicitation and analysis.
2. A written understanding of the client's requirements at a point in time, before design.
3. A **two-way insurance policy** for client and developer.
4. A precise statement of the functions, capabilities and constraints.
5. A **blueprint** that keeps cost growth low.
6. FRs and NFRs only, with **no design suggestions**. It says *what*, never *how*. ("Store in MySQL" is design and doesn't belong.)

**LO3. Four purposes.** Assure the customer you understand · decompose the problem · input to design · **master document for testing and validation**.

**LO4. Who writes it.** Natural language, unambiguous, with diagrams as needed. Developers are seldom good writers, so **involve a technical writer**. IEEE 830-1998 is the reference.

**LO5. Structure.**

| § | Section | Content |
|---|---|---|
| 1a | Purpose | Mission statement plus a high-level view (100–200 words) |
| 1b | Scope | The system and software this document covers |
| 1c | Users & stakeholders | **Everyone** with an interest |
| 1d | Assumptions & constraints | External interfaces, regulations… |
| 2 | Functional reqs | Numbered statements, plus UML and UI prototype |
| 3 | Non-functional reqs | Performance, standards, reliability, availability, security, maintainability, portability |
| 4 | Interface reqs | (a) User (b) Hardware (c) Software |
| 5 | Data dictionary | All terms and abbreviations |

**LO6. Nine quality characteristics.**
**Correct** (only user reps can judge) · **Feasible** · **Necessary** (no known origin, maybe not needed) · **Unambiguous** · **Verifiable** · **Complete** (hard to spot, so organise hierarchically) · **Consistent** · **Modifiable** (uniquely labelled) · **Traceable**.

**LO7. Words.**
- **Use:** *shall* (functional capability) · *must / must not* (performance or constraint) · *is required to* · *are applicable* (standards by reference) · *responsible for* (pre-defined architecture) · *will* (what the **environment** provides, not the system).
- **Avoid:** adequate · as a minimum · be capable of · as applicable · as appropriate · effective · if possible · if practical · timely · normal.

> **[Insert diagram: SRS document structure]**

<div style="page-break-after: always;"></div>

## Ch 8 — Software Processes

**LO1. Software process.** A structured set of activities to develop a system. Every process has four: **Specification · Design & implementation · Validation · Evolution**. A *process model* is an abstract representation of a process.

**LO2. A process description also includes:** products (outputs) · roles · pre- and post-conditions.

**LO3. Plan-driven vs agile.** Plan-driven plans everything in advance and measures progress against the plan. Agile plans incrementally and finds change easy. Most real processes mix both, and **there is no right or wrong process**.

**LO4. Three general models.**

| Model | Key idea | + | − |
|---|---|---|---|
| **Waterfall** | Separate, sequential phases: requirements → design → implement & unit test → integrate & system test → operate & maintain | Coordinates large multi-site projects | Hard to accommodate change. Only fits **well-understood, stable** requirements |
| **Incremental** | Specification, development and validation **interleaved** | Cheaper change · early feedback · faster delivery of value | Process **not visible** · **structure degrades** without refactoring |
| **Integration & configuration (reuse/COTS)** | Build from reusable parts: COTS apps, component collections (.NET, J2EE), web services | Lower cost and risk · faster delivery | **Requirements compromises** · **loss of control** over how parts evolve |

Reuse stages: requirements spec → discovery & evaluation → requirements refinement → configuration → adaptation & integration.

**LO5. Activities organised differently.** Waterfall runs them **in sequence**. Incremental **interleaves** them.

**LO6. Key points.** Requirements engineering produces the spec · design & implementation turn it into an executable · validation checks it against the spec **and** real needs · **software must evolve to remain useful**.

**Tutorial 4 essentials:**
- **Why costs are high:** designed not manufactured · inherent complexity · changing requirements and rework · communication overhead n(n−1)/2 · costly V&V · maintenance.
- **Why maintenance is big (60–80% of lifetime cost):** mostly *new functionality*, not bug fixes · structure degrades · time spent understanding code · ripple effects.
- **Software vs hardware, the two differences:** (1) software is **developed, not manufactured**, so quality comes only from the process; (2) software **doesn't wear out**, but it deteriorates through change. No bathtub curve, and no spare parts.

> **[Insert diagram: Waterfall model]**

> **[Insert diagram: Incremental development]**

> **[Insert diagram: Reuse-oriented process]**

<div style="page-break-after: always;"></div>

## Ch 9 — Agile Software Development & XP

**LO1. Why agile.** Rapid delivery is often the top requirement, business changes fast, and stable requirements are nearly impossible. Agile appeared in the late 1990s to cut delivery time.

**LO2. Characteristics.** Spec, design and implementation interleaved · a series of increments · frequent delivery · heavy tool support (automated tests) · **minimal documentation, focus on working code**.

**LO3. Plan-driven vs agile.** Plan-driven has separate stages with outputs planned in advance (it can still be incremental, with iteration *within* activities). Agile interleaves everything and **negotiates** outputs during development.

**LO4. Agile Manifesto.** **Individuals & interactions** over processes & tools · **Working software** over comprehensive docs · **Customer collaboration** over contract negotiation · **Responding to change** over following a plan.

**LO5. Five principles.** Customer involvement · Incremental delivery · People not process · Embrace change · Maintain simplicity.

**LO6. Where it applies.** Small or medium products for sale, and in-house custom systems with a **committed customer** and **few regulations**. Problems: managers new to agile, bureaucratic quality procedures, mixed skill levels, cultural resistance.

**LO7. XP.** Builds several times a day · delivers every **2 weeks** · **all tests run on every build**.

**LO8. XP practices.** Incremental planning (story cards → tasks) · Small releases · Simple design (just enough) · Test-first · Refactoring · Pair programming · Collective ownership · Continuous integration · Sustainable pace · On-site customer.

**LO9. What stuck.** As originally defined, XP isn't widely used. Four practices are: **user stories, refactoring, test-first, pair programming**.

**LO10. User stories.** The customer is on the team and writes stories on cards. The team splits them into tasks, which drive estimates. The customer picks stories for the next release.

**LO11. Refactoring.** Conventional wisdom says design for change. XP says change can't be reliably anticipated, so **improve the code continuously** instead. That improves understandability and reduces documentation. Limit: **architecture refactoring is expensive**. It needs a regression test safety net.

**LO12. Test-first / TDD.** Write a failing test → write the minimum code → refactor. It **clarifies requirements**. Tests are programs (e.g. JUnit) with a built-in check. All old and new tests run on every change.

**LO13. Pair programming.** Two people at one computer, with pairs rotated. Shares knowledge (less risk when people leave), acts as **informal review**, builds common ownership, encourages refactoring. **Not necessarily inefficient.**

**When NOT to use XP:** safety-critical or regulated systems · large or distributed teams · fixed-price contracts · no available customer · long-lived docs needed by a separate maintenance team.

> **[Insert diagram: XP release cycle]**

<div style="page-break-after: always;"></div>

## Ch 10 — Scrum

**LO1–2. What Scrum is.** An agile method for **managing** iterative development. Three phases: **outline planning** (objectives, architecture) → **sprint cycles** → **project closure** (docs, lessons learned).

**LO3–5. Roles.**

| Role | Key duties |
|---|---|
| **Product Owner** | Vision; represents stakeholders; **maximises value**; **owns the Product Backlog** (content, ordering) |
| **Scrum Master** | **Servant-leader**; coaches Scrum; facilitates events; **removes impediments**; shields the team. **Not** a project manager |
| **Dev Team** | **5–9** people (Sommerville says ≤ 7); self-organising; flat; owns the Sprint Backlog; delivers a "Done" increment |

**LO4. Sprint cycle.** Fixed **2–4 weeks** → select from the backlog with the customer → team self-organises, isolated (all contact goes through the SM) → review with stakeholders → next sprint.

**LO6. Artifacts.**
- **Product Backlog:** an ordered list and the **single source of requirements**. Features are written as user stories.
- **Sprint Backlog:** the chosen PBIs plus a plan. **Unchanged during the sprint.** Tasks take **1–16 h** (break up anything longer). Unfinished items go back to the Product Backlog.
- **Product Increment:** "Done" items integrated with all earlier sprints, so it is **potentially shippable**.

**LO7. Events.**

| Event | Time-box | Notes |
|---|---|---|
| Sprint | 2–4 wk | Fixed Sprint Goal; **never extended** |
| Sprint Planning | — | *What* can be done (only the Dev Team judges) + *how* |
| Daily Scrum | **15 min** | Yesterday? Today? Impediments? |
| Sprint Review | **1 h × weeks** | **Product** + stakeholders → revised backlog |
| Retrospective | **45 min × weeks** | **Process, tools, people**; team only → action plan |

**LO8. Burndown chart.** Work remaining vs time. Tracks scope creep and schedule, and compares planned with actual.

**LO9. Velocity.** Average points delivered per sprint, **as an average only** (one sprint means nothing). **Points can't be converted to hours.** To estimate it: (1) historical average, (2) run a sprint and observe, (3) capacity forecast (members × days × hours × focus factor), used only at the start.

**LO10. DEEP backlog.** **D**etailed appropriately (top items small and detailed) · **E**stimated · **E**mergent (never frozen) · **P**rioritised.

**LO11. Grooming.** Create and refine, estimate, prioritise. Takes **up to 10%** of the Dev Team's time.

**LO12–14. User stories.** *As a \<role\>, I want \<action\>, so that \<benefit\>.* An **epic** is a story too big to fit, so split it. **3 Cs:** Card · Conversation · Confirmation (acceptance criteria). A good acceptance criterion states **intent, not a solution**, is implementation-independent, and is fairly high-level. **INVEST:** Independent · Negotiable · Valuable · Estimable · Small · Testable.

**LO15. Benefits.** Manageable chunks · unstable requirements don't block progress · full visibility · on-time increments · trust.

**Calc trap (Tut 5 Q6):** 64 pts ÷ 8 sprints = **8 pts/sprint**. Cost = (PO + SM + 6 devs = **8**) × $2,000 × 8 sprints = **$128,000**, not $96,000.

> **[Insert diagram: Scrum sprint cycle]**

> **[Insert diagram: Sprint burndown chart]**

<div style="page-break-after: always;"></div>

## Ch 11 — System Design & Software Architecture

**LO1. Problem vs solution.** Elicitation, specification and analysis cover the **problem**. System design, object design, implementation and testing cover the **solution**. Their outputs: architecture → design model → code → tests.

**LO2. Two translations before design.** Mission statement (vague) → **SRS** (formal), then SRS (customer view) → **analysis model** (engineer view: boundary/control/entity, sequence, state).

**LO3. Why design is hard.** Systems keep growing (size, users, developers, lifespan) · projects are constrained (cost, schedule, maintenance) · NFRs must be met (performance, availability, security, scalability, extensibility).

**LO4–5. Definition.** *High-level structure in terms of architectural elements and their interactions.* **Architecture = {Components, Connectors}**.
- **Component:** a run-time unit (program, object, process, client, server, DB).
- **Connector:** an interaction (procedure call, RPC, protocol, data stream). Connectors are often spread across many components, so they're easy to miss.

**LO6. Three properties.** **Abstract** (details hidden) · about **structure and interactions** (topology) · **purposeful** (exists to analyse properties of interest).

**LO7. Inputs to design.** *Why:* FRs and NFRs. *What:* design principles and patterns. *How:* constraints (languages, libraries, communications).

**LO8. Design principles.** Modularity · Abstraction · **Open-Closed** · Reusability · Single Responsibility · Least Knowledge (Demeter) · DRY · **Low coupling, high cohesion**.

**LO9. Architectural style.** Defines a family of systems by a structural pattern: a vocabulary of component and connector types, combination constraints, and semantic models. It **doesn't** fix the number of components, the interaction mechanism, or what the system does.

**LO10. Taxonomy.**

| Family | Styles |
|---|---|
| Data flow | Batch sequential · Pipe-and-filter |
| Data-centred | Repository · Blackboard |
| Virtual machine | Interpreter · Rule-based |
| Call & return | Main/subroutine · OO · **Layered** |
| Independent components | **Client–server** · Event systems (implicit/explicit invocation) |

**LO11. Layered (3-tier).** **Presentation ↔ boundary**, **App Logic ↔ control**, **Persistent Data ↔ entity**. **Dependencies point downward only.** *Closed:* calls go only to the layer directly below. *Open:* calls can go to any lower layer.

**LO12. Event-based trade-offs.** + modifiability, concurrency, scalability, easy integration. − did the message arrive? Correctness is hard.

**LO13. Design process.** Generate and test: postulate several solutions → validate against the model → revise, seek new, or elaborate → compare → select.

**LO14. What it buys.** Maintainability, extensibility, new features, performance, scalability. These are the NFRs.

> **[Insert diagram: 3-layered architecture (Presentation / App Logic / Persistent Data)]**

> **[Insert diagram: Client–server (WWW) components & connectors]**

**Architecture vs design pattern (the difference is zoom level).**

| | Architecture (Ch 11) | Design pattern (Ch 12) |
|---|---|---|
| Scope | **Whole system** | **A few classes** in one subsystem |
| Parts | **Components + connectors** | **Classes / interfaces + roles** |
| Examples | Layered, Client–server, **Event-based**, Repository, Pipe-and-filter | Observer, Strategy, Factory, Façade |
| Driven by | **NFRs** | **What varies** + Open-Closed |
| Drawn as | Box-and-line diagram | UML class diagram |
| Change cost | Expensive | Local, cheap |

MVC (Ch 13) is the bridge: an architecture built from patterns.

**DWS (AY24/25 S2 Q3a/b):**
- **3(a) Architecture: Event-based (publish–subscribe).** Sensors push updates *at any time*, and the DWS reacts. The justification is LO12: easy to add or remove sensors and alerts (modifiability, integration) and many concurrent sensors (scalability). Optional: a layered manager side (UI / logic / persistent interaction log).
- **3(b)(i) Pattern: Observer.** The DWS is the Subject: `register()` / `deregister()` at **runtime**, `notify()`. Sensors push `update(value)`. The thing that varies is **who** gets told.
- Event-based architecture and Observer are the **same idea at two zoom levels**.

<div style="page-break-after: always;"></div>

## Ch 12 — Object Design & Design Patterns

**LO1. Place.** System design picks the subsystems. Object design fills them with classes, interfaces and collaborations.

**LO2. Four activities.** **Interface spec** (visibility, types, signatures, constraints, exceptions) · **Reuse** (components, patterns) · **Restructuring** (revisit inheritance, collapse classes) · **Optimisation** (access paths, caching, deferring work). Each round ends with a check against the use cases.

**LO3. Road to good design.** Goals (maintainable, extensible, scalable, testable, reusable) ← principles ← patterns. **Principles:** encapsulate what varies · program to an interface · favour composition over inheritance · loose coupling · Open-Closed · least knowledge.

**LO4–5. A pattern** is *a proven solution to a problem in a context*. Four elements: **Name · Problem · Solution · Consequences**.

**LO6. GoF 23 = 5 + 7 + 11.** *Creational:* Abstract Factory, Builder, Factory Method, Prototype, Singleton. *Structural:* Adapter, Bridge, Composite, Decorator, **Façade**, Flyweight, Proxy. *Behavioural:* Chain of Resp., Command, Interpreter, Iterator, Mediator, Memento, **Observer**, State, **Strategy**, Template Method, Visitor.

| Pattern | Problem | Roles | + / − |
|---|---|---|---|
| **Strategy** | Interchangeable algorithms | Context → «interface» Strategy ◁ ConcreteStrategies | + encapsulation, swap at run time · − complex if overused; client still has to `new` one |
| **Observer** | Many objects need updates when one changes | Subject (register / unregister / notify) → Observer.update() | + loose coupling, broadcast, independent reuse · − slower, extra complexity |
| **Factory** | Which class to create isn't known until run time | Context → StaticFactory.create() → AbstractProduct | + centralises creation, easy to add subclasses, enables Singleton or lazy init |
| **Façade** | Complex subsystem | Client → Façade → subsystem classes | + easier use, fewer dependencies · − rework if badly designed; many façades slow things down |

**Observer details.** *Pull:* `update()`, then the observer calls `getData()` (two-way). *Push:* `update(details)` (one-way). *Push+pull:* a few details pushed, the rest pulled if wanted. **Interest subscription** (`register(o, interest)`) plus **selective notification** (`notify(interest)`). Event handling (Swing listeners) *is* Observer.

**Strategy + Factory.** Strategy handles *use*, Factory handles *creation*. Together they satisfy Open-Closed end to end. Add **dynamic loading** (class name from config) and a new variant needs zero code changes (Eclipse, Swing L&F, JDBC).

**LO7. Choosing a pattern.** Find what **varies**:

| Varies | Pattern |
|---|---|
| Algorithm or policy | Strategy |
| Who gets told | Observer |
| Which class to create | Factory |
| Families of objects | Abstract Factory |
| Complex subsystem needs a simple entry point | Façade |
| Number of parts / combinations | Composite |

Then check Open-Closed and **name each class's role**.

**Tutorials:** T6Q2 network protocols = **Strategy** · T7Q1 plants = **Observer** (who) + **Strategy** (how) + Composite (email+SMS) · T7Q2 the missing piece = **Factory**.

> **[Insert diagram: Strategy pattern class diagram]**

> **[Insert diagram: Observer pattern class diagram]**

> **[Insert diagram: Static Factory + Strategy (EMS DataStore)]**

> **[Insert diagram: Façade (Computer startComputer)]**

<div style="page-break-after: always;"></div>

## Ch 13 — MVC: Composing Design Patterns

**LO1. Challenges of interactive systems.** UIs change often · the same data appears in several ways · changes must show up **immediately** · different look and feel · different reactions to input. So the **UI must not be tightly coupled** to the core.

**LO2. Excel case study.** EditWS, LineChart and BarChart (boundary) → SheetManager (control) → WorkSheet (entity). **Problem:** SheetManager has to call **up** into the presentation layer to refresh the charts. That's tight coupling, and every new chart means editing SheetManager.

**LO3. Fix with Observer.** SheetManager becomes `WSSubject` (attach, detach, notify, getData). The views become `WSObserver` (update). *They talk as WSSubject/WSObserver, not as specific classes.* **Observer allows up-calls without the lower layer depending on the higher one.** For look and feel and input handling, add **Strategy**.

**LO4. MVC goal.** Multiple synchronised views of shared data. Separating the Model from the View and Controller allows **many views of one model**. A change made through one view shows up in all of them.

**LO5. Components.**

| | Responsibility |
|---|---|
| **Model** | Data **and** processing |
| **View** | Displays output; **observes** the Model and redraws when notified |
| **Controller** | Handles user input → updates the Model. **One controller per view**; users interact only through controllers |

**LO6. Interaction (triangular, not layered).** (1) View subscribes to Model → (2) Controller updates Model → (3) Model notifies all Views → (4) each View calls `getData()` and redraws.

**LO7. Patterns inside MVC.**

| Pattern | Where |
|---|---|
| **Observer** | Model = Subject, Views = Observers |
| **Strategy** | View = Context, **Controller = Strategy** |
| **Abstract Factory** | Creates a view's controller or look and feel |
| Composite | Nested views |
| Decorator | Extra UI features (scrolling) |
| Command | Undo / redo |

The key three are **Observer, Strategy and Abstract Factory**.

**LO8. Excel as MVC.** EditWSView holds an EditWSCtrler. `handleEnter()` → `sheetMgr.updateCell()`. SheetManager is the Model. The charts are Views that call `getData()` inside `update()`.

**LO9. Pros and cons.** + parallel development · multiple views · high cohesion · low coupling. − steep learning curve and harder navigation · one feature is spread over three artifacts that must stay consistent.

**LO10. Summary.** Interactive systems are solved by **pattern composition**. Used in Django, Rails and ASP.NET MVC.

> **[Insert diagram: Excel case — layered with up-call problem]**

> **[Insert diagram: MVC triangle (Model / View / Controller) with Observer + Strategy]**

<div style="page-break-after: always;"></div>

## Ch 14 — Testing I: Fundamentals, Equivalence Classes, Boundary Values

**LO1–2. Context.** Black-box testing (ECs, BVs) checks against the **requirements**. White-box testing (CFG, basis paths) checks against the **code**. A bug is an error or fault that gives incorrect or unexpected results (the 1947 moth in the Mark II).

**LO3. Why not test everything.** A 16-bit int has 65,536 inputs. That's too costly, and random picks (1, 42, 32000) miss the `−1` vs `+1` bug. Testing at the **class boundaries** (e.g. 29999) catches it. Systematic beats random.

**LO4. Testing ≠ debugging.** Testing *finds* failures; debugging *fixes* faults. Testing is dynamic execution whose aim is to **find bugs, not prove there are none**.

**LO5. Black-box vs white-box.** Black-box works from the spec and misses hidden special cases in the code. White-box works from the code and misses **unimplemented** requirements. **Both are needed.**

**LO6. Levels.** Unit → Integration → System → Acceptance (UAT).

**LO7. Test case ingredients.** **Name · Location · Input · Oracle** (expected) **· Log** (actual). If the oracle and log differ, you've found a bug.

**LO8. Execution order.** *Cascading:* simpler, but one failure invalidates the rest. *Independent:* can run in parallel, but each test is bigger.

**LO9–10. Black-box process.** The tester finds ECs and BVs → picks valid and invalid inputs → sets the oracle → builds tests (steps 1–2 are hardest). The engine runs them and compares. + small, high-yield input set. − **no coverage measure**.

**LO11. Assumptions.** Requirements must be verifiable ("not too young" → ranges), and the code must be testable (no per-value special cases).

**LO12. Equivalence class.** Values that should give the **same output**. If one value catches a bug, the others probably would too. Test **one value per class**.

**LO13. EC rules.**

| | Range | Discrete set |
|---|---|---|
| ECs | **1 valid + 2 invalid** | **1 valid + 1 invalid** |
| BVs | on / just-below / just-above **each** boundary | **none** |

When one range has several outputs, each sub-range is its own valid EC (hiring: 0–15, 16–17, 18–54, 55–99).

**LO14. Designing tests.** Valid values: **combine** in one test case. Invalid values: **only one invalid input per test case**, so you know which check rejected it.

**LO15. Defensive testing** (valid and invalid inputs) is preferred over **testing by contract** (valid only).

**LO16–18. BV rules.** Three values per boundary. The step depends on the unit (±1, ±0.01). Drop any value that falls inside an EC already tested. Valid tests combine on-boundary values; invalid tests use one just-outside value each.

**LO20.** First turn vague requirements into verifiable ranges.

**Silo (Tut 8):** Humidity 0–100, normal 35–50 → **5 ECs**: <0 invalid · 0–34 reject · **35–50 accept** · 51–100 reject · >100 invalid. Valid BVs {0, 34, 35, 50, 51, 100}, invalid {−1, 101}. Same for temperature (−10–100, normal 40–60). **ACCEPT ⟺ humidity normal AND temperature normal.** Hold the other variable at a nominal normal value (42%, 50 °C).

**DWS link (AY24/25 S2 Q4b):** Only **ordered** inputs have boundaries. Names (`"smoke concentration"`, `"fire"`) are discrete, so there are **no BVs**; say so explicitly. 4 boundaries = 4 marks:

| Boundary | Below | On | Above |
|---|---|---|---|
| N lower −32768 | −32769 ✗ | −32768 ✓ | −32767 ✓ |
| N upper +32767 | +32766 ✓ | +32767 ✓ | +32768 ✗ |
| M lower 0 | **−0001** ✗ | 00000 ✓ | 00001 ✓ |
| M upper 32767 | 32766 ✓ | 32767 ✓ | 32768 ✗ |

M has no sign, so "just below 0" can't be written in a valid format. `−0001` is the answer, and it's invalid because of its **format**. Optional extra: digit count is ordered too (`+1234` ✗ / `+12345` ✓ / `+123456` ✗).

**DWS defensive test suite (AY24/25 S2 Q4c):** Cover **all 4 inputs** with **valid + invalid** values, **one invalid per case**, and give an **expected output** for each. Defaults: smoke concentration / fire / +00100 / 00100.

| TC | Changed input(s) | Expected |
|---|---|---|
| 1 | N=−32768, M=00000 | Link created |
| 2 | N=+32767, M=32767 | Link created |
| 3 | Sensor=`"rain"` | Rejected: unknown sensor |
| 4 | Alert=`"flood"` | Rejected: unknown alert |
| 5 | N=−32769 | Rejected: N below range |
| 6 | N=+32768 | Rejected: N above range |
| 7 | N=`12345` (no sign) | Rejected: N format |
| 8 | M=−0001 | Rejected: M negative / format |
| 9 | M=32768 | Rejected: M above range |
| 10 | M=`1234` (4 digits) | Rejected: M format |

Valid on-boundary values are combined (TC1–2). The just-inside values are dropped because they fall in a valid class already tested. TC2 is valid only because Q4(c) doesn't limit N+M; under Q4(d) it becomes invalid.

> **[Insert diagram: Number line showing ECs and boundary values (silo humidity)]**

<div style="page-break-after: always;"></div>

## Ch 15 — Testing II: Control Flow (White-box) Testing

**LO1. Process.** Draw the CFG → find paths → choose inputs for each path → set the oracle → build tests (steps 1–3 are hardest).

**LO2. Pros and cons.** + every path is identified. − all paths is usually infeasible · may miss data or arithmetic bugs (`a−1` vs `a+1`, divide by zero) · **never finds unimplemented paths**.

**LO3. CFG rules.** Node = process block (statements in sequence, one edge in, one out) or decision point. Edge = control flow.
- `if` / `if-else`: binary decision, branches merge after.
- `while`: decision plus a **back edge** from the end of the body to the condition.
- `for`: **rewrite as `while` first**.
- `switch`: N-ary decision, one edge per case including default.

**LO4. Path count.** 2^(number of decisions) for loop-free code. Loops multiply it by the iteration count.

**LO5. Coverage levels (each subsumes the one before).**

| Level | Criterion |
|---|---|
| 1 | **Statement:** every node at least once |
| 2 | **Branch:** every decision outcome T and F |
| 3 | **Basis path:** CC independent paths (guarantees 1 and 2) |
| 4 | **Path:** every path (often infeasible) |

**LO6. Basis path.** Each one adds **at least one new edge**. The basis set isn't unique, but its **size is always CC**.

**LO7. Cyclomatic complexity.**
```
CC = |E| − |N| + 2
CC = |decision points| + 1      (all binary)
CC = regions (incl. outer)      (textbook)
```
Check with two formulas. Count a compound `&&`/`||` as one decision (conventional) and **say so**. CC > ~10 suggests refactoring.

**LO8. Selecting a basis set.** (1) **Baseline** = a typical, important path. (2) Flip the first decision, keeping the others. (3) Flip the next. Repeat until you have CC paths, then give each one inputs **and** an expected output.

**LO9. Infeasible paths.** With **correlated** decisions, flip them **together** to keep infeasible paths to a minimum. Report any that remain as infeasible; never invent inputs for them.

**LO10. Loops.** Take each loop **0 and 1 times** when selecting basis paths, with the baseline **not entering** the loop. The real run may iterate many times, and that's fine.

**LO11. Summary.** Both testing styles matter.

**Tut 9 `sum(n, upperbound)`:** 9 nodes, 11 edges → **CC = 4** (3 decisions + 1).
- Statement and branch coverage: `(−3, 10)` → "sum is 6"; `(3, 2)` → "too large", returns 3.
- Basis paths: `(0, 10)` → 0 · `(−1, −1)` → "too large", 0 · `(1, 10)` → 1 · `(3, 2)` → "too large", 3.
- **Trap:** n<0 with the loop skipped *must* end in "too large".

> **[Insert diagram: CFG for computeP(a, b)]**

> **[Insert diagram: CFG for sum(n, upperbound)]**

> **[Insert diagram: CFG constructs — if / if-else / while / switch]**

<div style="page-break-after: always;"></div>

## Ch 16 — Software Maintenance

**LO1. Scale.** Over **100 billion LOC** are in production, and **up to 80%** of it is unstructured, patched and badly documented. Most software work is maintenance.

**LO2. Causes of maintenance problems.**

| Cause | Looks like | Remedy |
|---|---|---|
| **Unstructured code** | GOTO spaghetti, bad names, long procedures, tight coupling, weak cohesion, deep nesting | Structured programming, design principles |
| **Insufficient domain knowledge** | Has to be reverse-engineered from the code | Readable structure, domain models |
| **Insufficient documentation** | Missing or out of date | Keep the SRS and design docs alive |

**LO3. Definition (IEEE 610.12).** *Modifying a system after delivery to correct faults, improve performance or other attributes, or adapt to a changed environment.* It's done by changing existing components or adding new ones.

**LO4. Types and share of effort.**

| Type | Meaning | Effort | Textbook name |
|---|---|---|---|
| Fault repair | Fix bugs and vulnerabilities | **24%** | Corrective |
| Environmental adaptation | New OS or hardware | **19%** | Adaptive |
| Functionality addition/modification | **New requirements** | **58%** | Perfective |
| — | Head off future problems | — | Preventive (refactoring) |

**Exam point:** most maintenance is **not bug fixing**. That's why you design for change (Open-Closed, Strategy + Factory, Observer, MVC).

**LO5. Refactoring.** Improving a program to **slow degradation through change**, without adding functionality. It improves structure, reduces complexity and makes code easier to understand. **Behaviour doesn't change.** It's a **continuous** process, and the test suite proves behaviour is preserved.

**LO6. Bad smells (Fowler).**

| Smell | Fix |
|---|---|
| Duplicate code | Extract Method; pull up |
| Long method | Extract Method |
| Large class | Extract Class |
| Temporary field | Extract Class; Null Object |
| **Switch statements** | **Replace conditional with polymorphism (Strategy/State)** |
| Lazy class | Inline Class |
| Data clumping | Parameter Object |
| Tight coupling | Move Method; interface or **Façade** |

> **[Insert diagram: Maintenance effort pie chart (24 / 19 / 58)]**

<div style="page-break-after: always;"></div>

## Terminology — Definitions for Theory Questions

One line per term, grouped by topic. Focuses on terms the past papers ask about that the chapter pages don't define. **[S]** = only in Sommerville, not on the slides.

### People & requirements

| Term | Meaning |
|---|---|
| **Stakeholder** | Anyone with a direct or indirect interest in, or influence on, the system's requirements. Includes far more than users |
| ↳ *"Name 4 stakeholders + concerns"* | **End user**: usability, features, speed · **Client / sponsor**: cost, schedule, return on investment · **Developer**: clear, feasible, stable requirements · **Maintainer / operator**: maintainability, documentation · **Regulator**: compliance, safety, privacy · **Domain expert**: correctness of business rules. Give each one a concern tied to the scenario |
| **Customer vs user** | The customer pays and signs off. The user operates the system. They may be different people |
| **Requirement** | A statement of a service the system provides (FR) or a constraint on it (NFR) |
| **User vs system requirement** [S] | User = natural-language statement for the customer. System = detailed, precise spec for developers |
| **Domain requirement** [S] | Comes from the application domain (laws, industry rules), e.g. "PDPA compliance" |
| **Emergent property** [S] | A property of the whole system, not of any one part (reliability, security) |
| **Requirements engineering** | Elicitation → analysis → specification → validation, then management of change |
| **Requirements volatility** | How much requirements change during the project. High volatility points to agile |
| **TBD** | An open question recorded and asked of the client, never guessed |
| **Traceability** | Linking each requirement to its source, design, code and tests |
| **Baseline** | An agreed, signed-off version of a work product. Later changes go through change control |

### Process & project

| Term | Meaning |
|---|---|
| **Verification vs validation** | Verification: *"Are we building the product right?"* (meets the spec). Validation: *"Are we building the right product?"* (meets real needs) |
| **Generic vs customised product** [S] | Generic: sold on the open market; the **developer** owns the spec. Customised (bespoke): built for one customer, who owns the spec |
| **Software product vs software system** [S] | A product is the software itself (code, docs, config). A system is the wider whole the software runs in: hardware, people, processes. Reused COTS parts clash with **certification** because no source code or development evidence is available to certify |
| **COTS** | Commercial Off-The-Shelf: bought, configured, not built |
| **Coping with change** [S] | **Change anticipation**: prototype early to catch changes before they're costly. **Change tolerance**: incremental delivery so changes are cheap. Plan-driven projects also use a **change control board** and impact analysis |
| **Milestone vs deliverable** | Milestone = checkpoint for measuring progress (often a review). Deliverable = a work product handed to the customer |
| **WBS** | Work Breakdown Structure: the project broken down hierarchically into tasks small enough to estimate |
| **Activity network** | Tasks drawn with their durations and dependencies |
| **Critical path** | The longest path through the network, which gives the **shortest possible project time**. Any delay on it delays the project |
| **Forward / backward pass** | Forward gives the earliest start and finish (ES, EF). Backward gives the latest start and finish (LS, LF) |
| **Slack (float)** | LS − ES. How long a task can slip without delaying the project. Zero on the critical path |
| **PERT estimate** | (Optimistic + 4 × Most likely + Pessimistic) / 6 |
| **Estimation methods** [S] | **Experience-based** (expert judgement, analogy with past projects) · **Algorithmic** (COCOMO II: effort = A × Size^B × M) · bottom-up from the WBS · agile: story points + planning poker |
| **Story point** | A relative measure of size and complexity, **not** hours |
| **Definition of Done** | The shared checklist an item must pass to count as "Done" in the increment |
| **Impediment** | Anything blocking the team. The Scrum Master removes it |
| **Technical debt** | Future rework caused by choosing a quick fix now |

### Design & architecture

| Term | Meaning |
|---|---|
| **Coupling** | How strongly modules depend on each other. Aim **low** |
| **Cohesion** | How closely the responsibilities inside one module belong together. Aim **high** |
| **Separation of concerns** | Each part handles one concern (e.g. UI vs logic vs data) |
| **Encapsulation** | Hide internal data behind an interface |
| **Abstraction** | Show only essential features, hide the details |
| **Polymorphism** | One interface, many implementations chosen at run time. The basis of Strategy |
| **Interface** | A contract of operations with no implementation |
| **Open-Closed** | Open for extension, closed for modification |
| **Single Responsibility** | A class has one reason to change |
| **Law of Demeter** | Only talk to your immediate friends: no `a.getB().getC().do()` |
| **DRY** | Don't Repeat Yourself |
| **Dynamic loading** | Load a class by name, read from config, at run time. **Downsides:** errors move from compile time to run time, slower start-up, harder to debug, security risk if the config can be tampered with |
| **Subsystem** | A replaceable part of the system with a well-defined interface |
| **Tier vs layer** | A layer is a logical grouping. A tier is a physical machine or process |

### NFR vocabulary (for "identify the key NFR")

| NFR | Meaning | Architecture lever |
|---|---|---|
| **Performance** | Response time, throughput | Localise critical work, fewer large components, caching |
| **Scalability** | Handles more users or data by adding resources | Client–server, stateless servers, load balancing |
| **Availability** | Fraction of time the system is up | Redundant components, failover |
| **Reliability** | Runs without failure for a given time | Redundancy, input validation, fault tolerance |
| **Security** | Protects against unauthorised access | Layered, with critical assets in the inner layers; authentication component |
| **Safety** [S] | Doesn't cause harm | Isolate safety-critical parts in a few components |
| **Maintainability** | Easy to change | Fine-grained, self-contained, low-coupling components |
| **Extensibility** | Easy to add new features | Strategy + Factory, Observer, Open-Closed |
| **Portability** | Runs on other platforms | A layer that isolates the platform |
| **Usability** | Easy to learn and use | MVC, consistent UI |
| **Interoperability** | Works with other systems | Adapter, Façade, standard APIs |
| **Testability** | Easy to test | Low coupling, dependency injection, mocks |

### UML extras

| Term | Meaning |
|---|---|
| **Extension point** | A named place in a base use case where an `<<extend>>` use case may be inserted |
| **Sequence diagram** [S] | Objects as **lifelines** (dashed vertical lines), **messages** as horizontal arrows ordered top to bottom, **activation bars** while an object is busy. Fragments: `alt`, `opt`, `loop` |
| **Communication diagram** | Same information as a sequence diagram, but objects are linked freely and messages are **numbered** (1, 1.1, 2) to show order |
| **Swimlane** | A column of an activity diagram showing who or what performs each activity |
| **Guard** | A `[condition]` that must be true for a transition or flow to fire |
| **Stereotype** | `<<…>>` label extending UML's meaning, e.g. `<<entity>>`, `<<include>>` |
| **Component diagram** | Components with provided (lollipop) and required (socket) interfaces |

### Testing

| Term | Meaning |
|---|---|
| **Error → fault → failure** | Error = a human mistake. Fault (defect, bug) = its result in the code. Failure = the visible wrong behaviour when the fault runs |
| **Test case / suite / oracle** | Case = input + expected output. Suite = a set of cases. Oracle = the source of the expected result |
| **Unit testing** | Test one component **in isolation**, by the developer, usually white-box, with stubs and drivers |
| **Integration testing** | Test the **interfaces** between components. Big-bang, top-down (needs stubs) or bottom-up (needs drivers) |
| **System testing** | Test the whole integrated system against the **SRS**, FRs **and** NFRs, by a test team, black-box |
| **Acceptance testing (UAT)** | The **customer** tests in their own environment to decide whether to accept. Alpha = at the developer's site, beta = real users at their site |
| ↳ *Unit vs system, 2 differences* | Scope (one component vs the whole system) · basis (code or design vs requirements) · who (developer vs independent test team) · technique (mostly white-box vs black-box) |
| **Release testing** [S] | Testing a release before it ships, by a separate team, to show it meets the requirements |
| **Regression testing** | Re-run old tests after a change to check nothing that used to work is broken |
| **Stub** | A fake **callee**. It replaces a component the unit calls (missing, slow or external) and returns canned values |
| **Driver** | A fake **caller**. It invokes the unit under test and feeds it inputs |
| **Mock** | A stub that also **checks** it was called correctly |
| **Test harness** | Automated framework that runs tests and compares results (JUnit) |
| **Grey-box testing** | Testing with **partial** knowledge of the internals (design, schema, APIs). Better than black-box because it can target internal risks; cheaper than white-box because it doesn't need the full source |
| **Data-flow testing** | White-box testing that picks paths by where variables are **defined** and **used** (def-use pairs). Finds uninitialised or unused variables. Control-flow testing picks paths by **branches** instead |
| **Shift-left testing** | Test **earlier** in the lifecycle (TDD, requirements reviews). Defects are cheaper to fix the earlier they are found |
| **Static vs dynamic** | Static = reviews and inspections without running the code. Dynamic = execute it |
| **Test coverage** | How much of the code (statements, branches, paths) the tests exercise |
| **Parameterised test** | One test body run with many input sets, e.g. one suite for every deployment |
| **CC as a metric** | Besides basis paths: measures complexity, flags code to refactor (CC > 10), predicts maintenance effort and fault-proneness |

### Maintenance & evolution

| Term | Meaning |
|---|---|
| **Software evolution** | Ongoing change after delivery. Software must evolve to stay useful |
| **Legacy system** | An old system still vital to the business but costly to change (old tech, poor docs, original staff gone) |
| **Re-engineering** [S] | Restructure and redocument a legacy system **without changing its functionality**: source translation, reverse engineering, structure improvement, modularisation, data re-engineering |
| **Reverse engineering** | Analyse code to recover its design and specification |
| **Refactoring vs re-engineering** | Refactoring = small, **continuous**, during development. Re-engineering = big, one-off, after years of maintenance |
| **Maintenance prediction** [S] | Estimate effort from: the **number of change requests**, **complexity metrics** (CC, size), the number of components a change touches, and the mean time to make a change |
| **Ripple effect** | One change forces changes elsewhere. Caused by high coupling |
| **Lehman's laws** [S] | Continuing change: a system in use must change or it becomes less useful. Increasing complexity: structure degrades unless work is done to keep it |

### Professional & ethics [S 1.2]

| Term | Meaning |
|---|---|
| **Professional responsibility** | Confidentiality · competence (don't accept work beyond your skill) · intellectual property · no computer misuse. ACM/IEEE Code of Ethics |
| **Input validation** | Check all external input (users, third-party sensors, APIs) at the system boundary. A crash caused by bad input is a fault in **your** system too |
| **Accountability** | A human remains responsible for AI-generated code, designs and tests |

**DWS crash: string from a third-party sensor (AY24/25 S2 Q3c).** The concept tested is **professional responsibility + input validation / robustness**.
- **(i) Blame us?** *Yes:* the sensor is untrusted external input, and a safety-critical system must validate it and reject bad input instead of crashing (**robustness**). *No:* the SRS says updates are integers, we met the spec, and the sensor **broke the interface contract**. We never supplied or certified it.
- **(ii) Other parties:** **Sensor manufacturer** (broke the interface spec) · **Client / DWS manager** (connected an uncertified sensor with no integration or acceptance testing) · *alt:* whoever wrote the SRS without saying how invalid input is handled.
- **(iii) One way per stage:**

| Stage | Prevent it / reduce blame |
|---|---|
| Requirements | Robustness NFR: *"shall reject and log malformed updates without crashing"*. State the supported sensor interface in the SRS or contract |
| Design / impl | **Input validation**, exception handling, **fault isolation** (one bad sensor doesn't crash the whole DWS; alert the manager) |
| Testing | **Defensive / robustness testing** with wrong types (string, empty, overflow) + integration tests with third-party sensors |
| Deploy / maintain | Check compatibility at registration (test reading), and document the supported sensors |

Input validation is the one fix that actually **prevents** the crash. The others mostly **reduce blame**.
