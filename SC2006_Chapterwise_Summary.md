# SC2006 / CE2006 / CZ2006 — Software Engineering
## Chapter-wise Learning Outcomes & Tutorial Learning Points

> **Scope.** Built from the lecture decks in this folder (`1 – Introduction` … `9 – Agile`, `Lecture 12 System Design`, `Writing SRS`) and `Tutorial Questions.pdf`, with gaps filled from the prescribed textbooks.
>
> **Textbook shorthand used throughout**
> - **[S]** — Ian Sommerville, *Software Engineering*, 10th ed., Pearson 2017
> - **[BD]** — Bruegge & Dutoit, *Object-Oriented Software Engineering: Using UML, Patterns and Java*, 3rd ed., Pearson 2010
> - **[F]** — Martin Fowler, *UML Distilled*, 3rd ed., Pearson 2004
>
> **Coverage note.** Lecture slides exist for Chapters 1–10 and 11 below. Tutorials 6(b)–9 examine **design patterns** and **software testing**, for which no slide deck is present in this folder. Chapters 12–14 are therefore reconstructed from [BD] Ch. 8 and [S] Ch. 8 so the tutorial answers are still self-contained. These are flagged as *(no slides in folder)*.
>
> **Case-study note.** Tutorials 2, 3, 6, 7 and 8 all build on the **Grain Elevator System (GES)** problem statement, which is distributed separately on NTULearn and is not in this folder. The learning points below give the *method* and the expected *shape* of the answer rather than inventing GES specifics.

---

## Table of Contents

| Ch. | Topic | Lecture file | Tutorial |
|---|---|---|---|
| 1 | Introduction to Software Engineering | `1 - Introduction.pdf` | — |
| 2 | Requirements Elicitation I — FR / NFR | `2 - Requirements Elicitation 1.pdf` | Tut 1 |
| 3 | Requirements Elicitation II — Use Case Diagram | `3 - Requirements Elicitation 2.pdf` | Tut 2 |
| 4 | Requirements Elicitation III — Use Case Description | `4 - Requirements Elicitation 3.pdf` | Tut 2 |
| 5 | Requirements Analysis — Conceptual (Class) Model | `5 - Requirements Analysis Conceptual Models.pdf` | Tut 3 Q1 |
| 6 | Requirements Analysis — Dynamic Models | `6 - Dynamic models.pdf` | Tut 3 Q2 |
| 7 | Writing the SRS | `Writing SRS.pdf` | — |
| 8 | Software Processes | `8 - Software Processes - Basics.pdf` | Tut 4 Q1–4 |
| 9 | Agile Development & XP | `9 - Agile ... .pdf` (p.1–28) | Tut 4 Q5 |
| 10 | Scrum | `9 - Agile ... .pdf` (p.29–65) | Tut 5 |
| 11 | System Design & Software Architecture | `Lecture 12 System Design.pdf` | Tut 6 Q1 |
| 12 | Design Patterns *(no slides)* | — | Tut 6 Q2, Tut 7 |
| 13 | Black-box Testing *(no slides)* | — | Tut 8 |
| 14 | White-box / Control-flow Testing *(no slides)* | — | Tut 9 |

---

# Chapter 1 — Introduction to Software Engineering

**Reading:** [S] Ch. 1 · [BD] Ch. 1

## Learning Outcomes

**1. Define software engineering.**
> *"The production of maintainable, fault-free software that meets the user's requirements and is delivered on time and within budget."*

Note what the definition bundles together: four simultaneous constraints — **quality** (fault-free), **maintainability**, **requirements fit**, and **schedule + budget**. [S §1.1] adds that SE is concerned with *all* aspects of software production, not just the technical process — project management, tool development, theory and method all count.

**2. Recognise the engineering activities in building software.** The lecture motivates this with a building-construction analogy:

| Construction activity | Software counterpart |
|---|---|
| Deciding the purpose of the building | Requirements elicitation |
| How many rooms, how big, what it looks like | Requirements specification |
| Designing the building; materials, power, plumbing | System & object design |
| Project planning, scheduling, teamwork | Project management |
| Simulations and testing | Verification & validation |
| Construction | Implementation |
| Operation and maintenance | Deployment, evolution |

**3. State the five core SDLC activities and their work products / milestones.**

| SDLC phase | Work products | Milestone |
|---|---|---|
| Requirements Specification | SRS document, Prototype | Requirements Review |
| Design | Software Design Document, Interface Design Document, Test Cases, Models | Preliminary & Final Design Reviews |
| Implementation | Source code, System build | — |
| Testing | Technical documentation, User manual, Test report | User Acceptance Test |
| Maintenance | Change requests, Bug reports, Patch releases, Upgrades | General Availability Release |

**4. Distinguish SDLC from PLC.** The **Software Development Life Cycle** is the technical product pipeline. The **Project Life Cycle** wraps around it: *Plan Project → Organize Project → WBS & Schedule → Supervise Performance → Report Performance → Quality Control → Close Project*. Both run concurrently; SDLC produces the product, PLC produces the control.

**5. Know the course map.** Requirements Elicitation and Analysis → Software Process Models → Agile Software Process → System and Object Design → Testing and Maintenance. Lectures are pitched at large/medium projects; the lab project is where the practices are exercised.

**6. Course logistics.** 20+ lectures · 9 tutorials (5%) · group project 45% (labs #1–#3 at 5% each, Lab #5 demo 15%, documentation 15%) · Exam 50%. Tutorials are problem-based around the **Grain Elevator System** case study; most questions have no single model answer.

## Tutorial
None mapped to Chapter 1.

---

# Chapter 2 — Requirements Elicitation I: Functional & Non-Functional Requirements

**Reading:** [BD] §4.1–4.3 · [S] Ch. 4

## Learning Outcomes

**1. Place requirements work inside the SDLC.** The Requirements Specification phase has three activities and two documents:

```
Elicit Requirements → Validate Requirements → Review Requirements
         ↓                                            ↓
 Project Mission Statement (PMS)      Software Requirement Specification (SRS)
```

**2. Write a Project Mission Statement.** Two or three sentences defining:
1. **The problem** — what will be done (scope and limits)
2. **The stakeholders** — developers and users
3. **The outcomes and benefits** of the project

> *Example:* "The GoFast team will develop a website that enables airline travellers to rate their travel experiences. This project will be considered complete when the website has been tested and approved for release by the FactFinding Organisation. This project supports the International Travel Watchdogs objective to ensure air passengers can openly compare airlines."

**3. Select an elicitation technique.** Interview · Observation · Workshop · Legacy Product Study · Competitive Product Study · Prototype. Two purposes drive the choice: **learn the problem domain** and **study user tasks**.

**4. Classify requirements.**

- **Functional requirements** describe *interactions between the system and its environment* — mapping program inputs to program outputs. The things the system **must do**. Three recurring kinds:
  - *System functionality* — "The library member must be able to search the library catalog."
  - *Information to be processed* — "The system must display the temperature in degrees centigrade in the range −10 °C to +130 °C to one decimal place of accuracy."
  - *Interfaces with other systems* — "The system must be able to use WiFi to communicate all transactions with a client's secure database."

- **Non-functional requirements** describe *properties the system must have* that are not directly related to functional behaviour. The lecture's four categories (the FURPS-style set used by [BD §4.3]):

  | Category | Example from lecture |
  |---|---|
  | **Usability** | Help messages must be displayed in the local language according to the user's locale. |
  | **Reliability** | After a system reboot, the full system functionality must be restored within 5 minutes. |
  | **Performance** | When a book is placed in the checkout pad, the system must detect it within 2 seconds. |
  | **Supportability** | The database must be replaceable with any commercial product supporting standard SQL queries. |

**5. Apply the three documentation qualities — atomicity, verifiability, traceability.**

- **Atomic** — one requirement states one thing, so it can be individually verified and traced. The lecture's worked example:

  > *Non-atomic:* "When a computer is added, the tracking system requires the user to specify its type and allow the user to provide a description. Both these fields must be text of length >0 and <512 characters."

  > *Atomised:*
  > 1.1 When a computer is added to the tracking system, the user must enter the computer type.
  > 1.1.1 The computer type data must be text of at least one character and less than 512 characters.
  > 1.2 When a computer is added to the tracking system, the user must enter a description of the computer.
  > 1.2.1 The description of the computer must be text of at least one character and less than 512 characters.

  Note the hierarchical numbering — it carries the parent/child relationship and makes the set navigable.

- **Verifiable** — specific enough to be tested.

  | ✗ Not verifiable | ✓ Verifiable |
  |---|---|
  | The user interface must be user-friendly. | 80% of first-time users must be able to enter a simple search query within 2 minutes of starting to use the system. |
  | The system must control more than one drill press. | The system must control up to seven drill presses concurrently. |

- **Traceable** — (a) the ability to track a requirement from the SRS through design, documentation, source code, and into reviews and tests; (b) the ability to track dependencies among requirements, system functions and system components.

**6. Use good technical writing style.** Complete, simple, precise, unambiguous sentences in **active voice**; terms defined clearly and used consistently; clear layout and hierarchical organisation.

**7. Validate requirements.** Two mechanisms:
- **Review** — walkthrough, inspection, critical review, against a checklist for *completeness, consistency, unambiguity, correctness*.
- **Prototype** — makes requirements concrete.

Validation serves two audiences: **stakeholders** confirm the specified system meets their needs and that requirements are prioritised; the **development team** confirms the requirements and underlying assumptions are properly understood.

**8. Use UI prototypes.** "A picture is worth a thousand words." Three forms: **story boarding** (a sequence of graphics showing views of the interface during a specific interaction), **still images**, and an **interactive prototype** illustrating simulated dialogue.

**9. Build a Data Dictionary** — the *problem-domain glossary*. It ensures consistent, unambiguous terminology that all stakeholders agree on, and defines specialised terms. The lecture's university example distinguishes *Programme of Study / Course / Degree Programme* and *Lecture / Tutorial / Class / Laboratory / Seminar*. **Focus on problem-domain terms, not implementation terms.**

## Tutorial #1 — Functional / Non-Functional Requirements

### Q1. Atomise the Inventory and Asset Tracking System description, and check verifiability

**The source text:**
> "The System may be queried. A query may contain a user number or a serial number. If the query contains a user number, all equipment assigned to that user is reported. If the query contains a serial number, the assignment for that computer is reported. All query results show the name, office and user number of a user, followed by the serial numbers and types of all computers assigned to that user, and the date of each assignment. If a user is not assigned a computer or a computer not assigned to a user, this is reported."

**Learning points**

1. **Each sentence usually hides several requirements.** The word "or" ("a user number **or** a serial number") signals two separate query paths; the comma-list in the results sentence ("name, office and user number … serial numbers and types … date") signals a separate data requirement per field.
2. **Separate the *trigger*, the *processing* and the *output*.** A clean atomisation gives a numbered hierarchy, e.g.:

   ```
   1.    The system must accept a query from the user.
   1.1   The system must accept a query containing a user number.
   1.2   The system must accept a query containing a serial number.
   1.3   The system must reject a query that contains neither a user
         number nor a serial number, and display an error message.

   2.    Query by user number
   2.1   On a query containing a user number, the system must report all
         equipment assigned to that user number.
   2.2   If the user number has no equipment assigned, the system must
         report "No equipment assigned to this user".

   3.    Query by serial number
   3.1   On a query containing a serial number, the system must report the
         user to whom that computer is assigned.
   3.2   If the serial number is not assigned to any user, the system must
         report "This computer is not assigned to a user".

   4.    Query result content
   4.1   Each query result must display the user's name.
   4.2   Each query result must display the user's office.
   4.3   Each query result must display the user's user number.
   4.4   Each query result must display, for every computer assigned to
         the user, the computer's serial number.
   4.5   Each query result must display, for every computer assigned to
         the user, the computer's type.
   4.6   Each query result must display, for every computer assigned to
         the user, the date of that assignment.
   4.7   The query result must list the user's name, office and user
         number before the list of assigned computers.
   ```

3. **Verifiability check — the point of the exercise.** Walk each atomised statement and ask *"can I write a test that passes or fails this?"* Statements like 2.1 pass. Items that *don't* pass the check reveal **TBDs** to take back to the client:
   - What is the **format and length** of a user number and a serial number? (Without this you cannot test 1.1/1.2.)
   - What **ordering** applies to the list of computers — by serial number, by assignment date?
   - What is the **date format**?
   - What are "equipment", "computer" and "assignment" exactly? → these belong in the **Data Dictionary**.
   - What should happen if a query contains **both** a user number and a serial number? (The description is silent — do **not** guess, raise it as a TBD.)
4. **Do not invent requirements to fill a gap.** The lecture's elicitation process is explicit: *"Identify uncertainties to clarify with client (TBD). Do not guess the user requirements."*
5. **Use the SRS verbs.** "must", "shall", "is required to" — never "adequate", "as appropriate", "if possible" (see Chapter 7).

### Q2. Identify several non-functional requirements for the same system

**Learning points**

1. **Work through the NFR categories systematically** rather than free-associating — Usability, Reliability, Performance, Supportability (plus Security, Availability, Portability, Maintainability from the SRS template in Ch. 7).
2. **Every NFR must still be verifiable** — that is the whole trap in this question. Each needs a *number* and a *measurement condition*.

| Category | Weak (unverifiable) | Strong (verifiable) |
|---|---|---|
| Performance | "Queries must be fast." | "The system must return a query result within 2 seconds for a database of up to 50,000 asset records." |
| Usability | "The UI must be easy to use." | "90% of new administrative staff must be able to complete an asset-assignment query within 3 minutes of their first use, without written instructions." |
| Reliability | "The system must be reliable." | "The system must have an availability of at least 99.5% during office hours (0900–1800, Mon–Fri)." |
| Supportability | "The system must be maintainable." | "The asset database must be replaceable by any commercial DBMS supporting ANSI SQL-92 without changes to application source code." |
| Security | "Data must be secure." | "The system must authenticate every user by username and password before accepting a query, and must lock an account after 3 consecutive failed attempts." |
| Capacity / Scalability | — | "The system must support at least 2,000 registered users and 10,000 tracked assets." |
| Portability | — | "The client application must run on Windows 10 and later, and on macOS 12 and later." |

3. **Watch the FR/NFR boundary.** "The system must display the user's office" is *functional* (information to be processed). "The system must display it within 2 seconds" is *non-functional* (performance). The same sentence often contains one of each — another reason atomisation comes first.

---

# Chapter 3 — Requirements Elicitation II: Use Case Modeling & Use Case Diagrams

**Reading:** [BD] §4.4 · [F] Ch. 9

## Learning Outcomes

**1. Know what UML is and is not.** Created by Booch, Jacobson & Rumbaugh (1996); v1.1 adopted by the OMG in 1997; current version 2.5 (August 2015). It is *a graphical notation with textual annotation for specifying, documenting and communicating the structure, functionality and dynamic behaviour of complex software systems*. It is **not** a programming language and **not** the answer to all modelling problems. Its value is **standardisation**. (Visual Paradigm is the lab tool.)

**2. Place the UML diagram types.** The taxonomy splits into **Structure Diagrams** (Class, Component, Object, Composite Structure, Deployment, Package) and **Behaviour Diagrams** (Activity, Use Case, State Machine, and the Interaction family: Sequence, Communication, Timing, Interaction Overview). This course covers **Use Case, Class, State Machine, Activity, Sequence**. *Not all diagrams are needed to specify a system — use only the ones that are useful and necessary.*

**3. Position use cases in the lifecycle.**

```
Requirements Elicitation → Use Case Model
        ↓ expressed in terms of
Analysis → Application Domain Objects
        ↓ structured by
System Design → Subsystems
        ↓ implemented by
Detailed Design → Solution Domain Objects
        ↓ realized by
Implementation → Source Code
        ↓ verified by
Testing → Test Cases
```

**4. Distinguish functional requirements from use cases.** Both are about system functionality, but:
- **Functional requirements** state **what** — user, external system, functionality, information.
- **Use cases** state **how** — how actors interact with system functionality.
- **Functional requirements are the starting point for use case modeling.**

**5. Know the two halves of a Use Case Model.**
> **Use Case Model = Use Case Diagram (static) + Use Case Description (dynamic)**

Together they give a coherent visual *and* textual description of system functionality. In use-case-driven iterative development, use cases are **prioritised** for implementation.

**6. Use the four diagram elements.**

| Element | Notation | Meaning |
|---|---|---|
| **Actor** | stick figure | An external entity that interacts with the system |
| **Use Case** | ellipse | A unit of functionality performed by the system, which yields a result/value for an Actor |
| **Association** | solid line | Connects an Actor to the Use Case(s) in which they participate |
| **System boundary** | rectangle | What is inside vs. outside the system |

The ATM example: `Customer` → *Withdraw money*, *Check Balance*; *Verify Customer* involves the `Bank` actor; the box is the `ATM Machine`.

**7. Apply use case associations.** Dependencies between use cases are represented by associations; **associations are used to reduce complexity**. Two types:

- **`<<include>>` — Functional Decomposition.**
  *Problem:* a function in the original problem statement is too complex.
  *Solution:* describe it as the aggregation of simpler functions; decompose the use case into shorter ones.
  *Example:* `Manage Incident` includes `Create Incident`, `Handle Incident`, `Close Incident`.

- **`<<include>>` — Reuse of Existing Functionality.**
  *Problem:* overlaps among use cases.
  *Solution:* an include association from A to B means an instance of A performs all the behaviour described in B ("A delegates to B").
  *Example:* `View Map` is included by both `Open Incident` and `Allocate Resources`.

- **`<<extend>>` — Adding Optional Functionality.**
  *Problem:* the functionality in the original problem statement needs extension.
  *Solution:* an extend association from A to B.
  *Example:* `Report Emergency` is complete by itself but can be extended by `Help` for a scenario where the user needs help.

> **The distinction to memorise:** *include* = reuse; the included use case is **always** used by the parent. *extend* = optional addition; used by the parent **only** in exceptional or unusual circumstances.

**8. Derive a use case diagram from functional requirements — the three-pass method.** The lecture works the Library Management System three times over the same list of requirements:

> 1. The library member must be able to search the system for library materials
> 2. The library member must be able to loan library materials
> 3. The library management system must verify the library membership with the University Account System before the library member can loan library materials
> 4. The library member must return library materials via library dropoff kiosk
> 5. The library management system must send overdue notice using the CITS Email Server to the library member
> 6. When there are network issues to connect to CITS Email Server, the library management system must log the event

- **Pass 1 — Identify potential actors:** scan for *who* or *what external thing* participates → `Member`, `University Account System`, `CITS Email System`, `Library Dropoff Kiosk`.
- **Pass 2 — Identify potential use cases:** scan for *verb + object* → `Search Material`, `Loan Material`, `Verify Member`, `Return Material`, `Send Overdue Notice`, `Log Network Issues`.
- **Pass 3 — Identify associations between use cases:** scan for *before / when / using* → `Loan Material` **includes** `Verify Member` (req. 3: "before"); `Send Overdue Notice` **extends to**/triggers `Log Network Issues` (req. 6: "when there are network issues" → exceptional ⇒ `<<extend>>`).

The lecture then shows **three alternative diagrams** for the same requirements (one adding a `Login` use case included by everything; one attaching the `Library Dropoff Kiosk` as a secondary actor on `Return Material`). **Take this seriously: there is no single correct use case diagram.** What you must be able to do is justify your decomposition.

## Tutorial #2 — Use Case Model (Grain Elevator System)

> The GES problem statement is distributed separately. The learning points are the method and the expected answer shape.

### Q1(a). Identify actors and main use cases; draw a complete Use Case diagram using generalization, include and extend where appropriate

**Learning points**

1. **Work the three-pass method on the GES text.** Highlight nouns-that-act for actors, verb phrases for use cases, and connective words (*before*, *after*, *when*, *using*, *if*) for associations — exactly as the Library example demonstrates.
2. **Typical GES actors.** Elevator Manager / Operator, Truck Driver or Shipment Carrier, Processing Plant, Farmer / Supplier, plus *non-human* actors such as the Silo Sensor system (temperature / humidity), a Weighbridge or Scale, and any external billing or notification system. A system or device that the system *talks to* is an actor just as much as a person is.
3. **Typical GES use cases.** *Record Shipment Arrival*, *Weigh Shipment*, *Grade / Inspect Grain*, *Allocate Grain to Silo*, *Monitor Silo Condition*, *Ship Grain Out*, *Notify Processing Plant*, *Generate Report*.
4. **Where `<<include>>` belongs.** Behaviour repeated across several use cases, or a sub-step that is *always* performed: e.g. *Allocate Grain to Silo* always includes *Check Silo Capacity* and *Check Silo Condition*; several use cases include *Login / Authenticate Operator*.
5. **Where `<<extend>>` belongs.** Exceptional or conditional behaviour: e.g. *Allocate Grain to Silo* is extended by *Reject Shipment* when no silo is suitable; *Monitor Silo Condition* extended by *Raise Alarm* when thresholds are breached.
6. **Where generalization belongs** — the element the tutorial explicitly asks for and students most often omit.
   - **Actor generalization**: if `Elevator Manager` can do everything an `Elevator Operator` can do plus more, draw `Elevator Manager ──▷ Elevator Operator`. This removes duplicated association lines.
   - **Use case generalization**: a general use case `Record Shipment` with specialisations `Record Road Shipment` / `Record Rail Shipment`, where the specialisations share a goal but differ in the steps.
   - Generalization is the right tool when the variants are **kinds of the same thing**; `include` when one is a **part of** another; `extend` when one is an **optional addition to** another.
7. **Keep the diagram at one level of abstraction.** The classic marking failure is mixing a system-level use case (*Process Shipment Arrival*) with a UI-level step (*Click Submit Button*). A use case must yield an observable **result of value to an actor**.
8. **Draw the system boundary box** and keep actors outside it.

### Q1(b). Write the Use Case description for the use case(s) covering grain shipment arrival and subsequent allocation

**Learning points**

1. This is a **forward reference to Chapter 4** — the template, flow of events, alternative flows and exceptions are all specified there. Use the full template, not just a paragraph of prose.
2. **Decide first whether this is one use case or two.** "Shipment arrival **and subsequent** allocation" invites either (a) one use case *Process Shipment* that `<<include>>`s *Record Arrival* and *Allocate to Silo*, or (b) two use cases where the post-condition of the first is the pre-condition of the second. Either is defensible; state your choice and be consistent with the diagram from part (a).
3. **The description is where the real requirements surface.** Writing the step-by-step flow forces you to ask: what if the grain fails the quality check? What if no silo has capacity? What if the silo's temperature or humidity is out of range? Each of those becomes an **alternative flow** or **exception** — and the silo condition thresholds come back in **Tutorial #8**.
4. **Write actor steps and system steps alternately**, numbered, exactly as the ATM example in Chapter 4.

### Q1(c). Determine and document important terms in the Data Dictionary

**Learning points**

1. **Harvest the terms from the use case descriptions you just wrote.** Every domain noun you used needs an agreed definition: *Shipment, Consignment, Lot, Grain Type / Grade, Silo, Bin, Allocation, Capacity, Moisture Content, Elevator, Processing Plant, Gross/Tare/Net Weight*.
2. **Define problem-domain terms, not implementation terms.** `Silo` belongs in the dictionary; `SiloRecord` or `silo_table` does not.
3. **Expose ambiguity deliberately.** If the GES text uses "shipment", "delivery" and "consignment" interchangeably, the dictionary is where you force a single term and record the decision — this is the dictionary's primary purpose: *consistent unambiguous terminology that all stakeholders can agree on*.
4. **Use the two-column format** from the lecture (Term | Definition), and make definitions full sentences that would survive a client review. The definitions directly feed **Tutorial #3**, where the dictionary terms become candidate classes.

---

# Chapter 4 — Requirements Elicitation III: Use Case Descriptions & Introduction to the SRS

**Reading:** [BD] §4.4 · [F] Ch. 9

## Learning Outcomes

**1. Know the mandatory content of a Use Case Description.**

- **Participating Actors (and the Initiating Actor)**
  - A use case can have more than one participating actor.
  - The **initiating actor triggers** the use case.
  - If the use case is triggered by a system event or by another use case, the **initiating actor is NULL**.
- **Entry conditions (pre-conditions)** — the system state that must hold for the use case to execute.
- **Exit conditions (post-conditions)** — the system state that must be reached after executing the use case.
- **Flow of Events** (a.k.a. Normal / Main Successful Flow) — Step 1: how the actor triggers the use case; Step 2: how the system responds; Step 3: …
- **Alternative Flows** — variations or errors in the interaction (e.g. wrong username/password) that **return back to the normal flow**.
- **Exceptions** — exceptional situations that cause the **failure** of the use case (e.g. network not available).

> **The distinction that gets examined:** an *alternative flow* rejoins the main flow; an *exception* terminates the use case unsuccessfully.

**2. Write flows as alternating actor/system steps.** The ATM worked example:

| # | Step |
|---|---|
| 1 | *(Actor)* The Bank Customer inputs the card into the ATM |
| 2 | *(System)* The ATM requests the input of a six-digit PIN |
| 3 | *(Actor)* The Bank Customer enters a PIN |
| 4 | *(System)* The ATM verifies the card and PIN with the account information in the Bank |
| 5 | *(System)* If the card and PIN is verified the ATM requests the amount to withdraw |
| 6 | *(Actor)* The Bank Customer enters an amount |
| 7 | *(System)* The ATM verifies the amount is available in the customer account |
| 8 | *(System)* If the customer account has sufficient funds, the ATM outputs the money and card and a receipt |
| 9 | *(Actor)* The Bank Customer removes card, receipt and money |

**Participating actors:** Bank Customer (initiating), Bank.
**Entry conditions:** (1) Bank Customer has a Bank Account with the Bank, **and** (2) Bank Customer has an ATM Card and PIN.
**Exit conditions:** (1) Bank Customer receives the requested cash, **or** (2) Bank Customer receives an explanation from the ATM why the cash could not be dispensed.

**3. Label alternative flows and exceptions against the step they branch from.**

```
AF-S5: If the card and PIN are invalid
  1. The ATM displays "Invalid card and PIN. Please try again!" for 2 seconds
  2. The ATM returns to step 2

AF-S8: If the customer account has insufficient funds
  1. The ATM displays "Insufficient funds in your account! Please enter a
     smaller amount!" for 2 seconds
  2. The ATM returns to step 6
```

```
EX1: If the Bank Customer enters invalid PIN three times
  1. The ATM displays "Card is suspended! Please call customer service
     (1633) to reactivate the card" for 2 seconds
  2. The ATM outputs the card

EX2: If the ATM has insufficient funds
  1. The ATM displays "This ATM is off-service due to insufficient funds!"
     at the start screen
  2. The ATM does not accept the card
```

Note the naming convention `AF-S<step>` — it makes the alternative flow **traceable** to the step it leaves from, and note that each alternative flow says explicitly **which step it returns to**.

**4. Work a second full example — the Course Registration System.** Requirements:
> Registrar manages the course curriculum for a semester · Students select 4 primary and 2 alternate courses · Students add and drop courses till the end of the second week · Once a Student registers, the system notifies the Billing System · Professors find their course schedule · All users must login with the assigned password before performing tasks.

Yielding actors `Student`, `Registrar`, `Professor`, `Billing System`, and use cases `Select Courses`, `Add Courses`, `Drop Courses`, `Manage Curriculum`, `Find Course Schedule`, `Send Notice`, `Login` — with `Login` **included** by the actor-facing use cases, and `Manage Curriculum` **including** `AddCourse`, `DeleteCourse`, `ReviewCourses` (functional decomposition).

Its flow of events shows how **`<<include>>` appears inside the text**:
```
1. The system uses the included use case Login to verify the Registrar.
2. On successful login, the system prompts the Registrar to select the
   current semester or a future semester.
3. The Registrar selects the desired semester.
4. The system prompts the Registrar to select the desired activity:
   ADD, DELETE, REVIEW, or QUIT.
5. If the Registrar selects ADD, he uses the included use case AddCourse.
6. If the Registrar selects DELETE, he uses the included use case DeleteCourse.
7. If the Registrar selects REVIEW, he uses the included use case ReviewCourses.
8. If the Registrar selects QUIT, the system returns to the semester selection screen.
```

**5. Use the standard Use Case Template.** Fields: *Use Case ID · Use Case Name · Created By · Last Updated By · Date Created · Date Last Updated · Actor · Description · Preconditions · Postconditions · Priority · Frequency of Use · Flow of Events · Alternative Flows · Exceptions · Includes · Special Requirements · Assumptions · Notes and Issues.*

**6. Recite the deliverables of requirements elicitation.** Functional requirements · Use case model (diagram + descriptions) · Non-functional requirements · Data dictionary (problem-domain glossary) · UI prototype.

**7. Follow the two-step iterative elicitation process.**

- **Step 1 — Project Team.** Review the client's specification and any legacy or competitive products, then:
  1. Atomise requirements
  2. Identify Actors
  3. Identify main Use Cases (functional requirements)
  4. Identify non-functional requirements
  5. Initiate the Data Dictionary
  6. **Identify uncertainties to clarify with the client (TBD). Do not guess the user requirements.**

- **Step 2 — Project Team meets Client** (interview, observation, workshop…). *The agenda and necessary outcomes must be set and agreed before the meeting. Do not waste the Project Team's or the Client's time in unstructured unproductive meetings.* Typical agenda:
  1. Present and walk through the initial requirements and Data Dictionary; get agreement
  2. Clarify the TBD issues
  3. Discuss any new requirements the client identifies

- **Repeat Steps 1 & 2** until all uncertainties and ambiguities, and all dictionary definitions, are agreed with the client. A **prototype** may be produced to show intended functionality. *Try to minimize the number of meetings by making meetings productive.*

## Tutorial #2 (continued)
See Tutorial #2 learning points under Chapter 3 — part (b) of that tutorial is assessed against this chapter's template.

---

# Chapter 5 — Requirements Analysis: Conceptual Models & Class Diagrams

**Reading:** [BD] §2.3 Modelling Concepts, §2.4.2 Class Diagrams · [F] Ch. 3 Class Diagrams, Ch. 6 Object Diagrams

## Learning Outcomes

**1. Separate elicitation from analysis.**

| | Requirements **Elicitation** | Requirements **Analysis** |
|---|---|---|
| **Purpose** | Finding out what customers want | Produce a system model that is correct, complete, consistent and unambiguous, based on the use cases |
| **Output** | A description of the system in terms of **actors and use cases** | **Conceptual model** (system structure) + **dynamic model** (system behaviour) |

**2. Know why we formalise requirements with analysis models.** They (a) clarify the structural and dynamic aspects of the system to be built, (b) **validate** the requirements, and (c) **underpin solution modelling**.

**3. State the two analysis goals.**
- **Conceptual model (structural aspect)** — analyse use cases to identify the **objects** and the **roles** of objects involved in the system.
- **Dynamic model (dynamic aspect)** — determine *how* to fulfil the processes defined in the use cases, and *which objects* perform those processes. (→ Chapter 6)

**4. Define the three constituents of a conceptual model.**

| Concept | Definition | Real-world examples | Software examples |
|---|---|---|---|
| **Objects** | Anything that has a **state** and exhibits **behavior** | Bus, Dog, Company | LoginForm, UserVerifier, UserList |
| **Operations** | Procedures through which objects communicate among themselves | Bus: Stop, Start; Dog: Bark, Growl; Company: Sell, Quote | LoginForm: submit; UserVerifier: authenticate; UserList: searchUser |
| **Attributes** | Variables that hold state information | Bus: Seats, Colour; Dog: Name, Breed; Company: Name, Employees | — |

**5. Read and draw a UML class.** A class **represents a concept** and **encapsulates state (attributes) and behaviour (operations)**. Three compartments: name (the **only mandatory** part), attributes, operations. **Each attribute has a type; each operation has a signature.**

```
┌─────────────────────────────┐
│      TarifSchedule          │  ← Name (mandatory)
├─────────────────────────────┤
│ zone2price : Table          │  ← Attributes (each has a type)
├─────────────────────────────┤
│ getZones() : Enumeration    │  ← Operations (each has a signature)
│ getPrice(Zone) : Price      │
└─────────────────────────────┘
```

**6. Use associations and multiplicity.** Associations denote relationships between classes. **The multiplicity of an association end denotes how many objects an instance of a class can legitimately reference.** Multiplicity is a number (3), a range (1..6), or an unspecified large number (`*`).

| Form | Example from lecture |
|---|---|
| Many-to-many | `TarifSchedule * ── * TripLeg` |
| 1-to-1 | `Person 1 ── 1 Head` |
| 1-to-many | `Polygon 1 ── * Point` |

**7. Distinguish the class relationships — the most heavily examined slide in this chapter.**

**Generalization (inheritance):** hierarchies drawn top-down with arrows pointing **upward to the parent**. Line/arrow style depends on the parent:

| Parent is a… | Notation |
|---|---|
| class | solid line, **black** (filled) arrowhead |
| abstract class | solid line, **white** (hollow) arrowhead |
| interface | **dashed** line, white arrowhead |

*We often don't draw trivial/obvious generalization relationships, such as drawing the `Object` class as a parent.*

**Association (usage relationships):**

| Relationship | Meaning | Notation | Example |
|---|---|---|---|
| **Aggregation** | "**is part of**" | clear **white** diamond | `Book ◇── Page` |
| **Composition** | "**is entirely made of**" — a stronger aggregation; **the parts live and die with the whole** | **black** diamond | `Car ◆── Engine` |
| **Dependency** | "**uses temporarily**" — often an implementation detail, not an intrinsic part of the object's state | **dotted** line | `Lottery ┄> Random` |

**8. Follow the four conceptual-modelling activities.**
1. Identify the Classes
2. Find the attributes for each Class
3. Find the methods/operations for each Class
4. Find the associations between Classes

```
┌──────────────────┐
│  BankCustomer    │  ← Class name
├──────────────────┤
│ AccountName      │  ← Class attributes
│ CreditLimit      │
│ AccountNumber    │
├──────────────────┤
│ UpdateAccount()  │  ← Class methods
│ WithdrawCash()   │
└──────────────────┘
        │            ← Associations with other classes
```

> **Use case model → Class diagram.** The class diagram is *derived from* the use case model, not invented beside it.

**9. Identify initial objects/classes — the noun-extraction heuristic.** Look for:
1. **Recurring nouns / concepts** in the use cases
2. **Real-world entities** the system must track
3. **Application (problem) domain terms** in the Data Dictionary

Then **review definitions and attributes with stakeholders.**

**10. Apply the three analysis class stereotypes** ([BD §5.3] — the boundary/control/entity split that drives the architecture in Chapter 11):

| Stereotype | Responsibility |
|---|---|
| `<<entity>>` | Information **tracked** by the system |
| `<<boundary>>` | **Interaction** between actor and system |
| `<<control>>` | **Logic** to realize a use case |

**11. Work the extraction on a real use case description.** The `EnterSecureFacility` flow of events:

> 1. **User** presses finger on **FingerprintReader**.
> 2. **FingerprintReader** scans **fingerprint** and sends image to the **FacilityAccessSystem**.
> 3. The **FacilityAccessSystem** validates fingerprint and unlocks **EntryGate**.
> 4. **EntryGate** sends a signal to the **FacilityAccessSystem** that it has opened.
> 5. The **FacilityAccessSystem** locks **EntryGate**, logs entry event and increments occupant count.

→ **Possible classes:** `FingerprintReader`, `Employee`, `FacilityAccessSystem`, `EntryGate`, and `Fingerprint`? — the question mark is deliberate: a noun that is pure data passing through may be an **attribute** rather than a class. Deciding that is the exercise.

**12. Stereotype the dependencies too.** The lecture annotates usage dependencies with their nature: `FacilityAccessSystem ┄<<read>>┄> FingerprintReader`, `FacilityAccessSystem ┄<<call>>┄> EntryGate`, `EntryGate ┄<<signal>>┄> FacilityAccessSystem`. On a dependency, the arrow points from **client** to **supplier**.

## Tutorial #3 Q1 — Conceptual Model & Class Diagram (GES)

### Q1(a). From the Use Case description and Data Dictionary, identify the classes to produce a conceptual model

**Learning points**

1. **The inputs are specified and they are the ones you produced in Tutorial #2.** This is the point of the exercise: a conceptual model is *derived*, and its traceability back to the use case description is what makes it defensible. If you cannot point at the sentence in the use case description that justifies a class, you probably invented it.
2. **Apply the three-source heuristic** — recurring nouns in the flow of events, real-world entities the system tracks, and the problem-domain terms you already recorded in the dictionary.
3. **Expected GES entity candidates:** `Shipment`, `Grain` (or `GrainType` / `GrainGrade`), `Silo`, `Allocation`, `Elevator`, `ProcessingPlant`, `Supplier`, `Truck`, `WeightRecord`, `QualityReading` (temperature/humidity).
4. **Prune aggressively using three tests:**
   - *Does it have state the system must remember?* If not, it is probably not an entity class.
   - *Does it have behaviour?* A noun with neither state nor behaviour is an **attribute**, not a class (e.g. `Weight`, `MoistureLevel`, `ArrivalDate` are attributes of `Shipment`, not classes).
   - *Is it outside the system boundary?* Actors are not classes in the conceptual model — though an actor often has a corresponding entity class (`Supplier` the actor vs. `Supplier` the stored record).
5. **Apply the stereotypes.** A full conceptual model for GES will have `<<boundary>>` classes (e.g. `ShipmentArrivalUI`, `AllocationUI`), `<<control>>` classes (e.g. `ShipmentProcessingController`, `AllocationController` — typically one controller per use case), and `<<entity>>` classes (the list above). **This split is what Tutorial #6 Q1 then maps onto a layered architecture**, so getting it right here pays off twice.
6. **Give each class attributes and operations**, with types and signatures — the four-step activity list is explicit about this and marks are lost for name-only boxes.

### Q1(b). Depict the classes and the associations/dependencies between them in a Class Diagram

**Learning points**

1. **Choose the relationship type deliberately, don't default to a plain line.**
   - `Elevator ◆── Silo` — **composition**: silos are entirely part of the elevator and do not exist independently of it (parts live and die with the whole).
   - `Shipment ◇── Lot` or `Silo ◇── GrainBatch` — **aggregation** if the part can exist on its own.
   - `Shipment ──── Silo` via an `Allocation` — a plain **association**, because this is a relationship between independent things, often best reified as an **association class** `Allocation` carrying `quantity` and `date`.
   - `AllocationController ┄┄> Silo` — **dependency** if the controller only *uses* a silo temporarily during a method call.
2. **Every association end needs multiplicity.** `Silo 1 ── * Allocation`, `Shipment 1 ── * Allocation`, `GrainType 1 ── * Shipment`. An unlabelled association end is an incomplete model.
3. **Name associations or association ends where the meaning isn't obvious** — `Silo "storedIn" Allocation`.
4. **Use generalization where GES has genuine kinds**: `Grain` generalising `Wheat`/`Corn`/`Barley` only if they differ in attributes or behaviour; otherwise a `grainType` attribute is simpler and better. **Don't inherit to express a value.**
5. **Keep it a problem-domain model.** No database tables, no `Manager`/`Helper`/`Util` classes, no getters and setters. Those belong to design, not analysis.

---

# Chapter 6 — Requirements Analysis: Dynamic Models (State Machine & Activity Diagrams)

**Reading:** [BD] §2.4.3–2.4.5 · [F] Ch. 4 (Sequence), Ch. 10 (State Machine), Ch. 11 (Activity), Ch. 12 (Communication)

## Learning Outcomes

### State Machine Diagrams

**1. Know what a state machine diagram models.** Also known as **Statecharts** or **Finite State Automata**. It models a system or object based on the **"States" it can be in**.

> A **State** is a *stable condition* of a system that can exist for a period of time, or for all time, **until some ACTION drives the system into another stable state**.

Most systems have a **finite** number of states, determined by the previous state and the actions that move it onward. *E.g. a 2-bit binary counter has 4 states and moves from one to the next on a clock signal:* `00 → 01 → 10 → 11`.

**2. Draw a state.** A rectangle with **rounded corners**, with the name at the top and optionally a description and/or the actions and activities performed while in that state:

```
┌─────────────────────┐
│   State name        │
├─────────────────────┤
│ Entry / action      │   ← performed on entering the state
│ Exit  / action      │   ← performed on leaving the state
│ Do    / activity    │   ← performed continuously while in the state
└─────────────────────┘
```

**3. Draw transitions.** A diagram begins with a **start node**, followed by states connected by transitions, and ends with an **end node** (*unless the system is in an infinite loop, in which case there is no end node*). **A transition is assumed to be instantaneous in response to an event.** A transition can optionally carry:

```
          event(arguments) [guard] / action
State 1 ─────────────────────────────────────> State 2
```
- **event** — the event that triggers the transition
- **guard** — the condition that must be true to take the transition
- **action** — the action to perform during the transition

**4. Use a state machine diagram as a Dialog Map in prototyping.**

> Prototyping is a technique to **reduce the risk of building the wrong product, or of building the right product badly.** Using a state machine diagram and a prototype, users can experiment with navigation options and preview the functionality available at each screen, to assess the look and feel of the system.

Many user interfaces can be thought of as finite state machines, with **one display screen or window active at a time (a state)** and **defined conditions for moving from one to another (a transition)**. Such diagrams are called **dialog maps**.
- The dialog map helps us **find missing or incorrect navigation pathways early, when they are cheap to fix**.
- We can also **spot opportunities for reuse and redundancies in the user interface**, without prematurely worrying about screen-design details.

**5. Read the worked examples.**

*Vending machine:*
```
          Power On/Reset
               ↓
      ┌──────────────────────┐
      │ Idle                 │ ←───────────────────┐  [amount = 0]
      │ entry / amount := 0  │                     │
      │ do / display(greeting)│                    │
      └──────────────────────┘                     │
               │ insert(c:Coin)                    │
               ↓                                   │
      ┌───────────────────────────────┐            │
      │ Accumulate                    │ ⟲ insert(c:Coin)
      │ entry / amount := amount+c.amount           │
      │ do / display(amount)          │            │
      └───────────────────────────────┘            │
               │ select(i:item) [amount is enough for i]
               ↓                                   │
      ┌──────────────────────────────────┐         │
      │ Vend                             │         │
      │ entry / amount := amount - i.cost│         │
      │ do / dispense(i); display(vending)│        │
      └──────────────────────────────────┘         │
               │ [amount > 0]                      │
               ↓                                   │
      ┌──────────────────────┐                     │
      │ ReturnChange         │ ────────────────────┘
      │ do / return(amount)  │
      └──────────────────────┘
```
Note the three uses of guards: `[amount is enough for i]` gates the vend, `[amount > 0]` routes to change return, `[amount = 0]` routes straight back to Idle.

*Student Management System dialog map:* `Students List` ──add new──> `Student Details`; `Student Details` ──cancel──> `Students List`; `Personal Info Form` ⇄`next`/`back`⇄ `Academic Info Form` ⇄`next`/`back`⇄ `Activity Info Form` ──save──> back. Here each **state is a screen** and each **transition is a UI control**.

*Stopwatch practice:* states `Ready` (entry / Reset time), `Time` (do / Display time elapsed, Continuous Update), `Paused`; transitions `Click Start`, `Click Stop`, `Click Start` (resume), `Click Reset`, and `Click Close Window` from every state.

### Activity Diagrams

**6. Know the activity diagram elements.**
- **Activities** are the execution of one or more basic operations — a **rounded rectangle**.
- **Control flow** between activities — **arrows**.
- **Forks** — control flow has one input and **two or more outputs** (go to concurrent activities).
- **Joins** — two or more control flows come together into a single control flow.
- **Decision boxes (branches)** — control flow can go in one of several directions depending on a condition.
- **Merge** — several branches merge into one branch.

**7. Read the examples.**
- *Do Laundry:* `Sort Clothes in Whites and Darks` → **fork** → `Wash Whites` ∥ `Wash Darks` → **join** → `Dry Clothes`. (Fork/join expressing concurrency.)
- *Dry Clothes:* `Run Dryer` → **decision** `[still wet]` loops back to `Run Dryer`, `[else]` → `Fold Clothes`. (Decision + loop.)

**8. State the difference between the two diagram types — a standard exam question.**

> **Activity diagrams** are used as a **flow chart of activities performed by the system**. They describe the **workflow behaviour** of a system in terms of activities.
>
> **State machine diagrams** model a system or an object based on the **"States" it can be in**.

In short: *activity diagram = what happens next (flow of work)*; *state machine = what condition the thing is in (and what moves it)*.

### Requirements Elicitation & Analysis — the Complete Process

**9. Recite the 10-step process** (the lecture presents it, fittingly, as an activity diagram):

1. Study the client's initial specification
2. Generate initial Use Case Diagram and Descriptions, Data Dictionary, and a list of uncertainties / ambiguities / functional & non-functional requirements
3. Review requirements with the client (Interview, Observation, Workshop, Legacy Product Study, Competitive Product Study, Prototype)
4. Refine the Use Case Diagram, Descriptions and Data Dictionary, and the uncertainty list → **loop to 3 until `[Initial Requirements elicitation Agreed]`**
5. Identify Classes and draw initial Class Diagrams
6. Add associations and multiplicities; add Sequence Diagrams, State Diagrams, Activity Diagrams and other diagrams; list any new uncertainties
7. Review requirements with the client
8. Update Use Cases → **`[Use Case affected]`** branch
9. Refine Class Diagrams and other affected diagrams → **loop to 7 until `[Requirements Agreed]`**
10. Agree and **Sign-Off** on the Software Requirements Specification

**10. Know the SRS contents at a glance** (expanded in Chapter 7):
1. Product Description — (a) Purpose of the System (mission statement), (b) Scope, (c) Users and Stakeholders, (d) Assumptions and Constraints
2. Functional Requirements
3. Non-Functional Requirements
4. Interface Requirements — (a) User, (b) Hardware, (c) Software
5. Data Dictionary

Plus: it should be written in **natural language, unambiguously**, and may include diagrams. **IEEE 830-1998** is the recommended practice. Development team members are *seldom the best writers of formal documents, yet often have to write it* — so **involve a technical writer**.

## Tutorial #3 Q2 — Projector Controller State Machine (Dialog Map)

**The problem:**
> 8:30am lectures are frustrating: projectors, turned off at the end of the previous day, take a long time to become ready. At the Projector Controller Panel, Professor Jane:
> - Turns on the projector
> - As the projector warms up, it first gives a beep and a **red indicator light continues to blink**
> - When ready, the indicator light turns **green**; the projector takes input from the PC **by default**
> - Jane presses the **"LAPTOP"** switch
>
> After the lecture, Jane could turn off the projector by pressing **"OFF"**. However, to save her colleagues the angst, she decides to leave it ON.
>
> Model the projector's system behavior using a State Machine diagram.

### Model answer shape

```
   ●
   │
   ↓
┌──────────────────────────────┐
│ Off                          │
└──────────────────────────────┘
   │ press ON
   ↓
┌──────────────────────────────────────────┐
│ WarmingUp                                │
│ entry / beep()                           │
│ do    / blink(red indicator)             │
└──────────────────────────────────────────┘
   │ [warm-up complete]      ← a completion/time transition, no user event
   ↓
┌──────────────────────────────────────────┐
│ Ready — PC Input          (default)      │
│ entry / indicator := green               │
│ do    / project(PC source)               │
└──────────────────────────────────────────┘
   │ press LAPTOP                      ↑ press PC
   ↓                                   │
┌──────────────────────────────────────────┐
│ Ready — Laptop Input                     │
│ do / project(Laptop source)              │
└──────────────────────────────────────────┘
   │
   └── press OFF ────────────────> Off   (also from Ready–PC Input)
```

### Learning points

1. **States are *stable conditions*, not actions.** `WarmingUp`, `Ready–PC Input`, `Ready–Laptop Input`, `Off` are states. "Press the LAPTOP switch" is **not** a state — it is the *event on a transition*. This is the single most common error on this question.
2. **Put continuous behaviour in `do /`, instantaneous behaviour in `entry /` or `exit /`.** The blinking red light persists for the whole of warm-up → `do / blink(red)`. The beep happens once on arrival → `entry / beep()`. The light turning green happens once on becoming ready → `entry / indicator := green`.
3. **Not every transition needs a user event.** The warm-up → ready transition is triggered by the device itself (a completion or time-based transition), written as a bare guard `[warm-up complete]` or `after(warm-up period)`. Recognising this is part of the question — the problem statement says the projector *"take[s] a long time to become ready"*, which is precisely why warm-up is a state and not a transition.
4. **"Takes input from the PC by default" is a default sub-state.** Two clean modellings, both acceptable:
   - Two sibling states `Ready–PC Input` and `Ready–Laptop Input`, with the warm-up transition entering `Ready–PC Input`.
   - A composite state `Ready` with nested states `PC Input` (marked as the initial sub-state with a ●) and `Laptop Input`. The composite form is tidier because the `OFF` transition can then be drawn once from the `Ready` boundary rather than twice.
5. **Model the OFF transition even though Jane doesn't use it.** The question says she *could* press OFF but *decides* not to. The **system** still supports it; the state machine models system behaviour, not one user's habit. Leaving it out is a scoping error — but it is worth a sentence noting that in Jane's actual usage the machine stays in `Ready`.
6. **The diagram has a start node; whether it has an end node is a judgement.** A projector that is switched off and on again indefinitely is a loop — `Off` is both the initial and the "resting" state, and an explicit end node is optional. The lecture says explicitly: *"finally an end node (unless the system is in an infinite loop and there is no end node)."*
7. **Why this is also a dialog map.** The Projector Controller Panel *is* a user interface: each state is what the panel shows (blinking red / solid green) and each transition is a button. Drawing it surfaces exactly the question the scenario is complaining about — the user has no feedback on *how long* warm-up takes. That is a **usability non-functional requirement** discovered by modelling, which is the lecture's stated benefit: *"the dialog map helps us find missing or incorrect navigation pathways early, when they are cheap to fix."*
8. **Could this be an activity diagram instead?** No — and knowing why is the point. The projector is defined by the *condition it is in* (warming / ready / off) and by *events that change that condition*. That is a state machine. An activity diagram would be right for modelling *Jane's workflow for setting up a lecture*.

---

# Chapter 7 — Writing the Software Requirements Specification

**Reading:** [S] Ch. 4 (esp. §4.6 Requirements specification) · IEEE 830-1998

## Learning Outcomes

**1. Place the SRS in the requirements activities.**

```
Elicit Requirements → Analyse Requirements → Validate Requirements
        ↓                      ↓                      ↓
  PMS: Document        Analysis Model:          SRS: Document
                       Problem Model
```

**2. Define what an SRS *is* — six statements to be able to reproduce.**
1. The **output** of Requirements Elicitation and Requirements Analysis.
2. An organisation's understanding **in writing** of a customer's or potential client's system requirements and dependencies, at a particular point in time, usually prior to any actual design or development work.
3. A **two-way insurance policy** that assures both the client and the organisation understand each other's requirements from that perspective at a given point in time.
4. A statement in **precise and clear language** describing the functions and capabilities a software system must provide, as well as any required constraints the system must abide by.
5. A **blueprint** for completing a project with as little cost growth as possible.
6. Detailed functional and non-functional requirements — **it does NOT contain any design suggestions.**

> **Point 6 is the one examiners probe.** The SRS says *what*, never *how*. "The system shall store asset records in a MySQL database" is a design decision smuggled into an SRS.

**3. State the four purposes of the SRS.**
1. Give the customer **assurance** that the development organisation understands the problems to be solved and the software behaviour necessary to address them.
2. **Decompose** the problem into component parts.
3. Serve as an **input to the design specification** — so it must contain sufficient detail in the functional requirements for a design solution to be devised.
4. Serve as the **parent/master document for testing and validation strategies** applied to the requirements for verification in the testing stage.

**4. Know who writes it and how.** Natural language, unambiguous, diagrams as necessary. Detailed FRs and NFRs must be defined and understood by the development team. *Development team members (programmers and managers) are seldom the best writers of formal documents — however, they often have to write it!* **Good practice: involve a technical writer** with the development team, because they are better at assessing and planning documentation projects and better meet customer document needs.

**5. Reproduce the SRS structure with the content of each section.**

| § | Section | What goes in it |
|---|---|---|
| **1** | **Product Description** | |
| 1(a) | Purpose of the System | The **Project Mission Statement** plus what the system does from a high-level perspective. **Not long — 100–200 words is sufficient.** |
| 1(b) | Scope of the System | **Identify the system and the software to which this document applies**, including identification number(s) and title(s) as applicable. |
| 1(c) | Users and Stakeholders | **All** the people and organisations with an interest in the system: users, clients, funding bodies, standards bodies… |
| 1(d) | Assumptions and Constraints | Any information that may affect the SRS — e.g. assuming external interfaces are fully specified and will not change, regulations that must be met… |
| **2** | **Functional Requirements** | Precise **numbered** statements, supported as appropriate by **Activity Diagrams, Use Case Diagrams with Use Case Descriptions, Class Diagrams, Sequence Diagrams, Communication Diagrams, State Machine Diagrams and Prototype UI** |
| **3** | **Non-Functional Requirements** | Precise numbered statements covering **Performance, Standards, Reliability, Availability, Security, Maintainability, Portability** |
| **4** | **Interface Requirements** | (a) **User** — required screen formats, page/window layouts, content of reports or menus, availability of programmable function keys; (b) **Hardware** — number of ports, instruction sets, etc.; (c) **Software** — interfaces to a data management system, an operating system, a mathematical package… |
| **5** | **Data Dictionary** | Unambiguously defines **all terms, phrases and abbreviations** used in the SRS |

**6. Apply the nine language quality characteristics of an SRS.**

| # | Characteristic | Test to apply |
|---|---|---|
| 1 | **Correct** | Does each requirement accurately describe the functionality to be delivered? **Only user representatives can determine correctness** — hence they must be included in requirements inspections. |
| 2 | **Feasible** | Can each requirement be implemented within the known capabilities and limitations of the system and its environment? |
| 3 | **Necessary** | Does it document something customers really need, or something required for conformance to an external requirement, interface or standard? **If you cannot identify the origin of the requirement, perhaps it is not really necessary.** |
| 4 | **Unambiguous** | Can the reader draw only one interpretation? Do multiple readers arrive at the same interpretation? |
| 5 | **Verifiable** | Can you devise tests, inspections or demonstrations to determine whether it is properly implemented? |
| 6 | **Complete** | No requirements or necessary information missing. **Hard to spot — missing requirements aren't there.** Organise requirements **hierarchically** so reviewers can see the structure and tell if something is absent. |
| 7 | **Consistent** | Does it conflict with other software requirements, or with higher-level system/business requirements? **Disagreements must be resolved before development proceeds.** |
| 8 | **Modifiable** | Can the SRS be revised and a history of changes maintained? Requires each requirement to be **uniquely labeled and expressed separately** so it can be referred to unambiguously. |
| 9 | **Traceable** | Can each requirement be linked to its source — a higher-level system requirement, a use case, or a voice-of-the-customer statement? |

**7. Use the right words — a direct exam target.**

**Words to USE:**

| Word | When |
|---|---|
| **Shall** | To dictate the provision of a functional capability |
| **Must / Must not** | Most often to establish a performance requirement or constraint |
| **Is required to** | As an imperative in SRS statements |
| **Are applicable** | To include, by reference, standards or other documentation as an addition to the requirement being specified |
| **Responsible for** | As an imperative in SRSs written for systems with pre-defined architectures |
| **Will** | To cite things that the **operational or development environment** is to provide to the capability being specified |

> Note the careful distinction: **shall/must** = an obligation on *the system*; **will** = a statement about *the environment*.

**Words to AVOID** — they create uncertainty:
`adequate` · `as a minimum` · `be capable of…` · `as applicable` · `as appropriate` · `effective` · `if possible` · `if practical` · `timely` · `normal`

## Tutorial
None mapped directly, but the SRS is the deliverable for the lab project and the language rules are applied in Tutorial #1.

---

# Chapter 8 — Software Processes

**Reading:** [S] Ch. 2 *(this deck is adapted directly from Sommerville)*

## Learning Outcomes

**1. Define the software process.** A **structured set of activities** required to develop a software system. There are many different software processes, but **all** involve four fundamental activities:

| Activity | Meaning |
|---|---|
| **Specification** | Defining what the system should do |
| **Design and implementation** | Defining the organization of the system and implementing it |
| **Validation** | Checking that it does what the customer wants |
| **Evolution** | Changing the system in response to changing customer needs |

A **software process model** is an **abstract representation** of a process — a description of a process from some particular perspective.

**2. Know what a process description contains.** Beyond the activities and their ordering:
- **Products** — the outcomes of a process activity
- **Roles** — the responsibilities of the people involved
- **Pre- and post-conditions** — statements true before and after an activity is enacted or a product produced

**3. Contrast plan-driven and agile processes.**
- **Plan-driven** — all process activities are **planned in advance** and progress is measured against the plan.
- **Agile** — planning is **incremental**; it is easier to change the process to reflect changing customer requirements.
- **In practice, most practical processes include elements of both.**
- **There are no right or wrong software processes.**

**4. Compare the three general process models.**

### The Waterfall Model
A **plan-driven** model with **separate and distinct** phases of specification and development.

Phases:
1. Requirements analysis and definition
2. System and software design
3. Implementation and unit testing
4. Integration and system testing
5. Operation and maintenance

**Main drawback:** the difficulty of **accommodating change** once the process is underway — in principle, a phase must be complete before moving to the next.

**Problems:**
- Inflexible partitioning into distinct stages makes it difficult to respond to changing customer requirements.
- Therefore **only appropriate when requirements are well understood and changes will be fairly limited** during the design process.
- **Few business systems have stable requirements.**
- Mostly used for **large systems engineering projects developed at several sites** — there the plan-driven nature helps **coordinate the work**.

### Incremental Development
Specification, development and validation are **interleaved**. May be plan-driven **or** agile.

**Benefits:**
- **The cost of accommodating changing customer requirements is reduced** — much less analysis and documentation has to be redone than with waterfall.
- **Easier to get customer feedback** — customers can comment on demonstrations and see how much has been implemented.
- **More rapid delivery and deployment of useful software** — customers gain value earlier.

**Problems:**
- **The process is not visible.** Managers need regular deliverables to measure progress; if systems are developed quickly it is not cost-effective to produce documents reflecting every version.
- **System structure tends to degrade as increments are added.** Unless time and money are spent on **refactoring**, regular change corrupts the structure, and incorporating further changes becomes increasingly difficult and costly.

### Integration and Configuration
Based on **software reuse**: systems are integrated from existing components or application systems (sometimes called **COTS** — Commercial-Off-The-Shelf). Reused elements may be **configured** to adapt their behaviour and functionality to users' requirements. **Reuse is now the standard approach for building many types of business system.**

**Types of reusable software:**
1. **Stand-alone application systems** (COTS) configured for use in a particular environment
2. **Collections of objects** developed as a package to be integrated with a component framework such as .NET or J2EE
3. **Web services** developed to service standards and available for remote invocation

**Reuse-oriented process stages:** Requirements specification → Software discovery and evaluation → Requirements refinement → Application system configuration → Component adaptation and integration

**Advantages:** reduced **costs and risks** (less software written from scratch); **faster delivery and deployment**.
**Disadvantages:** **requirements compromises are inevitable**, so the system may not meet users' real needs; **loss of control over the evolution** of reused system elements.

> In practice, most large systems are developed using a process that incorporates elements from **all** of these models.

**5. Understand how process activities are organised differently.** Real software processes are **inter-leaved sequences of technical, collaborative and managerial activities**. The four basic activities are organised differently in different processes — in the waterfall model they are **in sequence**; in incremental development they are **interleaved**.

**6. Recite the key points.**
- Software processes are the activities involved in producing a software system; software process models are abstract representations of these processes.
- General process models describe the organization of software processes — e.g. waterfall, incremental development, reuse-oriented development.
- **Requirements engineering** is the process of developing a software specification.
- **Design and implementation** processes transform a requirements specification into an executable software system.
- **Software validation** checks that the system conforms to its specification **and** that it meets the real needs of its users.
- **Software evolution** takes place when you change existing systems to meet new requirements. **The software must evolve to remain useful.**

## Tutorial #4 Q1–Q4 — Software Processes

### Q1. Why are software development costs so high?

**Learning points — organise the answer under causes, not as a list of grumbles.**

1. **Software is designed, not manufactured.** Essentially *all* of the cost is in development (people) rather than replication (machines). There are no economies of scale in production to amortise the design cost against, and the output is labour-intensive, knowledge-intensive work by expensive skilled people.
2. **Inherent complexity.** Brooks' *essential* difficulties — **complexity** (no two parts alike; state space grows non-linearly), **conformity** (software must conform to pre-existing systems, standards and human institutions it cannot change), **changeability** (it is pressured to change precisely *because* it is seen as easy to change), and **invisibility** (no natural geometric representation, so progress and structure are hard to see).
3. **Requirements volatility and rework.** [S Ch.2] — few business systems have stable requirements. Every change after a phase is "complete" forces analysis and documentation to be redone. Cost of fixing a defect rises by roughly an order of magnitude per phase it escapes (requirements → design → code → test → field).
4. **Communication overhead.** Effort does not scale linearly with team size: communication paths grow as *n(n−1)/2*. Adding people to a late project makes it later (Brooks' Law).
5. **Verification and validation are expensive.** Exhaustive testing is impossible, so substantial effort goes into test design, test automation, reviews and inspections — and into the *consequences* of defects that still escape.
6. **The whole-life view.** Development is only the first cost. Maintenance typically dominates total lifetime cost (→ Q2), and it is accounted against the same software.
7. **Project failure and overrun.** A nontrivial share of projects are cancelled or massively overrun; the industry prices that risk in.
8. **Supporting costs** often forgotten: project management, configuration management, documentation, tooling and licences, training, deployment, regulatory compliance.

### Q2. Why do we spend so much time and effort maintaining existing software?

**Learning points**

1. **Scale first:** maintenance consumes the **majority of total lifetime cost** — commonly quoted at 60–80% [S Ch. 9]. The question is therefore not "why any" but "why so much".
2. **Maintenance is not mostly bug-fixing.** The standard taxonomy:
   - **Corrective** (~20%) — fixing defects
   - **Adaptive** (~20%) — adapting to a changed environment: new OS, new hardware, new platform, new regulations, new interfacing systems
   - **Perfective / Enhancement** (~60%) — adding or changing functionality as business needs change
   So most "maintenance" effort is actually **continued development**.
3. **The software must evolve to remain useful** — the explicit lecture point. Business, environment and expectations all move; software that stands still becomes wrong even if no line changes.
4. **Structure degrades under change** — the lecture's stated problem with incremental development. **Unless time and money are spent on refactoring, regular change corrupts the structure**, and each subsequent change becomes harder and costlier. (Lehman's laws: *continuing change* and *increasing complexity*.)
5. **Understanding cost dominates.** A maintainer spends most of their time *reading* and *comprehending* existing code before changing a line, especially when documentation is out of date, the design rationale was never recorded, and the original developers have left.
6. **Change ripples.** Poorly modularised systems with high coupling mean a local change requires non-local edits, and every edit requires **regression testing** of things that were previously working.
7. **Decisions made in development are paid for in maintenance** — this is the link back to the course's emphasis on traceability, modularity, low coupling / high cohesion, and documentation. The *maintainable* in the course's definition of software engineering is not decoration.
8. **Legacy constraints.** Old technologies, obsolete languages, dependencies no longer supported, and a prohibition on "just rewriting it" because the system is business-critical.

### Q3. Discuss the characteristics of software that affect its development

**Learning points — these are properties of the artefact that force the engineering approach.**

| Characteristic | Consequence for development |
|---|---|
| **Intangible / invisible** | No natural geometric representation; progress cannot be observed the way a building's can. Forces us to create **models** (UML) and **milestones with work products** to make progress visible. |
| **Complex** | State space and interactions grow non-linearly with size. Forces **decomposition, abstraction and modularity**. |
| **Changeable / malleable** | Because it *can* be changed, it *will* be asked to change. Forces **change management, configuration management**, and process models that absorb change (incremental, agile). |
| **Conforming** | Must fit existing hardware, standards, regulations and human processes that it cannot alter. Forces **interface requirements** and constraint analysis. |
| **Does not wear out, but deteriorates** | No physical degradation, but the **structure degrades** under repeated change. Forces **refactoring** and attention to design quality. |
| **Discrete, not continuous** | A one-bit change can flip behaviour entirely; there is no "small input ⇒ small output" guarantee. Means **testing can show the presence of defects but not their absence**, and drives systematic test design (equivalence classes, boundary values — Ch. 13). |
| **Developed, not manufactured** | Cost is in design, replication is free. Means **quality must be built into the development process**, not inspected into the product line. |
| **Largely custom-built** | Limited reuse historically; each system solves a somewhat novel problem. Drives the push toward **reuse-oriented / COTS-based** development. |
| **Logical, not physical, product** | No raw-material or supply-chain constraints — the binding constraint is **people**, which makes the process a *people* problem as much as a technical one (the agile "people not process" principle). |

### Q4. What are the two distinct differences between software development and hardware manufacturing?

**Learning points — the question says *two distinct differences*, so give exactly two, named and explained.**

**Difference 1 — Software is *developed / engineered*, not *manufactured*.**
- Hardware cost has two components: a one-off **design** cost **plus** a recurring **per-unit manufacturing** cost (materials, assembly, yield loss, QC per unit). Quality problems in hardware can arise during manufacture.
- Software has essentially **only** the design/development cost; **replication is effectively free and perfect**. There is no manufacturing phase where quality can be lost or gained.
- **Consequence:** in hardware, you can improve quality by improving the production line. In software, **quality can only come from the development process itself** — reviews, design quality, testing — because there is no production line to fix. Economies of scale therefore work completely differently: doubling hardware volume lowers unit cost; "doubling" software copies costs nothing but doesn't lower the development cost either.

**Difference 2 — Software does not wear out; hardware does.**
- Hardware follows the **"bathtub curve"**: a high *infant mortality* failure rate from manufacturing defects, falling to a low steady rate, then **rising again as components physically wear out** (fatigue, corrosion, dust, temperature). Hardware is repaired by **replacing a failed part with an identical spare**.
- Software has no physical wear mechanism. Its *idealised* failure curve falls during debugging and then stays flat forever. But the **actual** curve is a sequence of **spikes and a rising floor**: each change introduces new defects, which are then fixed, and the overall defect rate creeps upward because **the structure degrades with every modification**. Software "deteriorates" through **change**, not through use.
- **Consequence:** there are no spare parts for software — a failed component cannot be swapped for an identical copy, because an identical copy has the identical defect. Every software failure means a **design/maintenance** action, which is why maintenance dominates lifetime cost (Q2).

> *Other defensible pairs exist* (e.g. hardware has a supply chain and physical lead times; hardware design is largely frozen before manufacture while software requirements change during development). But the two above are the canonical Pressman/Sommerville pair and the ones the question is fishing for.

---

# Chapter 9 — Agile Software Development & Extreme Programming

**Reading:** [S] Ch. 3 *(this deck is adapted directly from Sommerville)*

## Learning Outcomes

**1. Understand why agile emerged.**
- **Rapid development and delivery is now often the most important requirement** for software systems.
- Businesses operate in a **fast-changing** environment and it is practically impossible to produce a set of stable software requirements.
- Software has to **evolve quickly** to reflect changing business needs.
- Plan-driven development is **essential for some types of system but does not meet these business needs**.
- Agile methods emerged in the **late 1990s**, aiming to **radically reduce the delivery time** for working software systems.

**2. Characterise agile development.**
- Program **specification, design and implementation are inter-leaved**
- The system is developed as a **series of versions or increments**, with stakeholders involved in version specification and evaluation
- **Frequent delivery** of new versions for evaluation
- **Extensive tool support** (e.g. automated testing tools)
- **Minimal documentation — focus on working code**

**3. Contrast plan-driven and agile precisely.**
- **Plan-driven:** based around **separate development stages**, with the outputs to be produced at each stage **planned in advance**. *Not necessarily waterfall* — plan-driven **incremental** development is possible. **Iteration occurs within activities.**
- **Agile:** specification, design, implementation and testing are **inter-leaved**, and the outputs of the process are **decided through negotiation during** development.

**4. Reproduce the Agile Manifesto.** The aim is to reduce overheads in the software process (e.g. by limiting documentation) and to respond quickly to changing requirements without excessive rework.

> *We are uncovering better ways of developing software by doing it and helping others do it. Through this work we have come to value:*
>
> - **Individuals and interactions** over *processes and tools*
> - **Working software** over *comprehensive documentation*
> - **Customer collaboration** over *contract negotiation*
> - **Responding to change** over *following a plan*
>
> *That is, while there is value in the items on the right, we value the items on the left more.*

**5. Reproduce the five principles of agile methods.**

| Principle | Description |
|---|---|
| **Customer involvement** | Customers should be closely involved throughout development. Their role is to provide and prioritize new system requirements and to evaluate the iterations of the system. |
| **Incremental delivery** | The software is developed in increments, with the customer specifying the requirements to be included in each increment. |
| **People not process** | The skills of the development team should be recognized and exploited. Team members should be left to develop their own ways of working without prescriptive processes. |
| **Embrace change** | Expect system requirements to change, and design the system to accommodate these changes. |
| **Maintain simplicity** | Focus on simplicity in both the software and the development process. Wherever possible, actively work to eliminate complexity from the system. |

**6. Know where agile applies — and where it struggles.**

**Applicable to:**
- **Product development** where a software company is developing a small or medium-sized product for sale
- **Custom system development within an organization**, where there is a **clear commitment from the customer to become involved** in the development process and where there are **few external rules and regulations** affecting the software

**Problems across organizations:**
- Project managers **without experience of agile** may be reluctant to accept the risk of a new approach
- Large organizations often have **quality procedures and standards** all projects must follow which, being bureaucratic, are likely to be **incompatible** with agile methods
- Agile seems to work best when **team members have a relatively high skill level**; large organizations have a wide range of skills and abilities
- There may be **cultural resistance**, especially in organizations with a long history of conventional systems engineering

**7. Know Extreme Programming (XP).** A very influential agile method from the late 1990s that introduced a range of agile development techniques. XP takes an **'extreme' approach to iterative development**:
- New versions may be built **several times per day**
- Increments are delivered to customers **every 2 weeks**
- **All tests must be run for every build**, and the build is only accepted if tests run successfully

**8. Reproduce the XP practices.**

| Principle or practice | Description |
|---|---|
| **Incremental planning** | Requirements are recorded on **story cards**; the stories included in a release are determined by the **time available and their relative priority**. Developers break these stories into development **'Tasks'**. |
| **Small releases** | The **minimal useful set of functionality that provides business value** is developed first. Releases are frequent and incrementally add functionality. |
| **Simple design** | **Enough design is carried out to meet the current requirements and no more.** |
| **Test-first development** | An **automated unit test framework** is used to write tests for a new piece of functionality **before that functionality itself is implemented**. |
| **Refactoring** | All developers are expected to **refactor the code continuously** as soon as possible code improvements are found. This keeps the code **simple and maintainable**. |
| **Pair programming** | Developers work **in pairs**, checking each other's work and providing the support to always do a good job. |
| **Collective ownership** | The pairs work on **all areas of the system**, so **no islands of expertise develop** and all developers take responsibility for all the code. **Anyone can change anything.** |
| **Continuous integration** | As soon as work on a task is complete it is **integrated into the whole system**. After any integration, **all the unit tests must pass**. |
| **Sustainable pace** | **Large amounts of overtime are not acceptable** — the net effect is to reduce code quality and medium-term productivity. |
| **On-site customer** | A representative of the end-user should be **available full time** to the XP team. The customer is **a member of the development team** and is responsible for bringing system requirements to the team for implementation. |

**9. Know which XP practices actually stuck.** XP has a technical focus and is **not easy to integrate with management practice in most organizations**. Consequently, **while agile development uses practices from XP, the method as originally defined is not widely used**. The four **influential** practices:
1. **User stories for specification**
2. **Refactoring**
3. **Test-first development**
4. **Pair programming**

**10. User stories for requirements.** In XP, a customer/user is **part of the XP team** and is responsible for making decisions on requirements. User requirements are expressed as **user stories or scenarios**, written on **cards**; the development team breaks them into **implementation tasks**, which are the basis of **schedule and cost estimates**. The customer **chooses the stories for inclusion in the next release** based on their priorities and the schedule estimates.

**11. Refactoring — know the argument.**
- Conventional wisdom is to **design for change**: worth spending effort anticipating changes as this reduces costs later in the life cycle.
- **XP maintains that this is not worthwhile, because changes cannot be reliably anticipated.**
- Instead it proposes **constant code improvement (refactoring)** to make changes easier **when** they have to be implemented.
- The team looks for possible improvements and makes them **even where there is no immediate need**.
- This **improves the understandability** of the software and so **reduces the need for documentation**; changes become easier because the code is well-structured and clear.
- **However, some changes require architecture refactoring, and this is much more expensive.**

**Examples of refactoring:** re-organization of a class hierarchy to remove duplicate code · tidying up and renaming attributes and methods to make them easier to understand · replacing inline code with calls to methods in a program library.

**12. Test-first / test-driven development.**
- XP tests the program **after every change**.
- XP testing features: **test-first development**; **incremental test development from scenarios**; **user involvement in test development and validation**; **automated test harnesses** run all component tests each time a new release is built.
- **Writing tests before code clarifies the requirements to be implemented.**
- Tests are written **as programs rather than data**, so they can be executed automatically, and each test **includes a check that it has executed correctly**. Usually relies on a framework such as **JUnit**.
- **All previous and new tests are run automatically when new functionality is added**, checking that the new functionality has not introduced errors.
- **Test automation** means tests are written as executable components **before** the task is implemented. They should be **stand-alone**, should **simulate the submission of input** to be tested, and should **check that the result meets the output specification**. Because testing is automated, **there is always a set of tests that can be quickly and easily executed**.

**13. Pair programming.**
- Programmers **sit together at the same computer** to develop the software.
- **Pairs are created dynamically** so that all team members work with each other.
- **The sharing of knowledge reduces the overall risk to the project when team members leave.**
- **It is not necessarily inefficient** — there is some evidence that a pair working together is **more efficient than 2 programmers working separately**.
- It helps develop **common ownership** of code and spreads knowledge across the team.
- It serves as an **informal review process** — each line of code is looked at by more than one person.
- It **encourages refactoring**, as the whole team benefits from improving the system code.

## Tutorial #4 Q5 — Characteristics of eXtreme Programming

### (i) When to use XP

**Learning points**

1. **Answer with conditions, not with a definition.** XP is appropriate when:
   - The project is **small to medium** in size with a **small, co-located team** (roughly up to 10–12 developers) — the practices depend on constant face-to-face interaction.
   - **Requirements are volatile or poorly understood** at the start and are expected to change. If requirements are stable and well understood, a plan-driven process is cheaper.
   - A **customer representative can be on-site full time** — the *on-site customer* practice is non-negotiable; without it, incremental planning and story prioritisation have no authority.
   - The team is **skilled and self-disciplined** — "people not process" assumes capable people.
   - There are **few external regulatory or certification constraints**, and the organisation does not mandate heavyweight documentation or stage-gate quality procedures.
   - **Rapid delivery matters more than comprehensive documentation**, and the organisational culture tolerates minimal documentation.
   - The technical environment supports **automated unit testing and continuous integration** — without a test harness, test-first development and continuous integration are impossible.
2. **State where XP is NOT appropriate**, which is half the marks:
   - **Safety-critical, mission-critical or regulated systems** (avionics, medical devices, nuclear) needing certification evidence, formal specification, and auditable documentation.
   - **Large systems** needing up-front architectural design, and **distributed teams** across sites/time zones.
   - **Fixed-price, fixed-scope contracts**, where "responding to change over following a plan" conflicts with the contract.
   - Where the **customer cannot or will not be continuously involved**.
   - Projects requiring **long-lived documentation for a maintenance team that is not the development team**.
3. **Note the honest caveat from the lecture:** XP has a technical focus and is **not easy to integrate with management practice in most organizations** — as originally defined it is **not widely used**; what survives is the four influential practices.

### (ii) Pair programming

**Learning points — discuss mechanism, benefits, costs.**

1. **Mechanism:** two programmers at one machine, one "driving" (typing) and one "navigating" (reviewing, thinking ahead); roles swap frequently. **Pairs are formed dynamically** so every member works with every other member over time.
2. **Benefits:**
   - **Continuous informal review** — every line is seen by at least two people as it is written, so defects are caught at the cheapest possible moment.
   - **Knowledge sharing / risk reduction** — spreads knowledge across the team, so the project is less exposed when a member leaves. Directly supports **collective ownership**.
   - **Encourages refactoring** — both parties benefit from improving the code, so neither resists the cost.
   - **Higher discipline** — harder to cut corners with an observer; sustains coding standards.
   - **Faster onboarding** of new members.
3. **The efficiency question — this is what the question is testing.** The naive objection is that it halves output. The lecture's position: **pair programming is not necessarily inefficient, and there is some evidence that a pair working together is more efficient than 2 programmers working separately.** The reasoning: the pair produces **fewer defects**, and defect-removal effort later typically exceeds the apparent duplication now; and the review that would otherwise be a separate scheduled activity is absorbed into the writing.
4. **Costs and limits worth mentioning:** roughly 15% more raw person-hours in most studies, for substantially fewer defects; it is tiring and unsuitable for an 8-hour continuous day (cf. **sustainable pace**); it depends on compatible personalities and comparable skill levels; and it does not work for distributed teams without good tooling. It is also wasteful on trivial or purely mechanical tasks.

### (iii) Test-driven development (TDD)

**Learning points**

1. **The cycle:** write a failing test for a small piece of new functionality → write the **minimum** code to make it pass → refactor → repeat. Tests come **before** the code, always.
2. **Why it works — four arguments from the lecture:**
   - **Writing tests before code clarifies the requirements to be implemented.** You cannot write a test for behaviour you have not pinned down, so TDD is a *specification* technique as much as a testing one.
   - **Tests are written as programs, not data**, so they can be executed automatically and each test **includes a check that it executed correctly**.
   - **All previous and new tests are run automatically when new functionality is added**, so regressions are caught immediately — this is what makes **continuous integration** and **refactoring** safe.
   - **Tests are stand-alone**, simulate the submission of input, and check the result meets the output specification.
3. **Relationship to other practices** — this is the mark-earning connection: TDD is the enabler for **refactoring** (you dare not restructure code without a regression net) and for **continuous integration** (the build is accepted only if all tests pass). XP's practices are **mutually reinforcing**, not independent.
4. **Tooling:** an automated unit-test framework such as **JUnit**; an automated test harness runs all component tests on every build.
5. **Additional XP testing features:** **incremental test development from scenarios** (user stories become acceptance tests) and **user involvement in test development and validation**.
6. **Limitations worth noting:** TDD gives excellent unit-level coverage but does not by itself produce good integration, performance or usability testing; tests can be written to match a buggy understanding of the requirement; and it adds up-front effort that is only repaid over the life of the code.

### (iv) Code refactoring

**Learning points**

1. **Definition:** improving the **internal structure** of existing code **without changing its external behaviour**.
2. **The XP argument — state both sides, because the question says "discuss":**
   - *Conventional wisdom:* **design for change** — spend time and effort anticipating changes, since this reduces costs later in the life cycle.
   - *XP's counter-position:* **this is not worthwhile, because changes cannot be reliably anticipated.** Speculative flexibility is usually wrong flexibility. Instead, keep the design **simple** (*enough design to meet current requirements and no more*) and rely on **constant code improvement** to make changes easy **when** they actually arrive.
3. **Practice:** developers refactor **continuously, as soon as possible improvements are found** — and **even where there is no immediate need for them**.
4. **Benefits:** improves **understandability**, which in turn **reduces the need for documentation**; changes become easier because the code is well-structured and clear; it keeps the code **simple and maintainable**; and it counteracts the **structure degradation** that the Chapter 8 lecture identifies as the central problem of incremental development.
5. **The limitation to state:** **some changes require architecture refactoring, and this is much more expensive.** Refactoring is cheap at the level of classes and methods; it is not cheap at the level of system structure. This is precisely why Chapter 11's architectural decisions still matter in an agile project, and why "scaling agile methods for large systems is difficult — large systems need up-front design."
6. **Concrete examples from the lecture:** re-organizing a class hierarchy to remove duplicate code · tidying up and renaming attributes and methods to make them easier to understand · replacing inline code with calls to methods in a program library.
7. **Refactoring requires a safety net** — it is only safe in the presence of an automated regression test suite, which is why it is paired with TDD.

---

# Chapter 10 — Scrum

**Reading:** [S] §3.4 Agile project management · *(lecture deck `9 - Agile` pp. 29–65)*

## Learning Outcomes

**1. Understand why agile project management differs.** The principal responsibility of software project managers is to **deliver on time and within budget**. The standard approach is **plan-driven**: managers draw up a plan showing *what* should be delivered, *when*, and *who* will work on it. **Agile project management requires a different approach, adapted to incremental development.**

**2. Know what Scrum is.** Scrum is an agile method that focuses on **managing iterative development rather than specific agile practices**. Three phases:
1. **Outline planning phase** — establish the general objectives for the project and design the software architecture
2. **A series of sprint cycles** — each cycle develops an increment of the system
3. **Project closure phase** — wrap up, complete required documentation such as system help frames and user manuals, and assess the lessons learned

**3. Reproduce the Scrum terminology.**

| Term | Definition |
|---|---|
| **Development team** | A **self-organizing** group of software developers, **no more than 7 people**, responsible for developing the software and other essential project documents |
| **Potentially shippable product increment** | The software increment delivered from a sprint. It should be **'potentially shippable'** — in a finished state with no further work such as testing needed to incorporate it into the final product. *In practice this is not always achievable.* |
| **Product backlog** | A list of 'to do' items the Scrum team must tackle: feature definitions, software requirements, user stories, or supplementary tasks such as architecture definition or user documentation |
| **Product owner** | An individual (or small group) who **identifies product features/requirements, prioritizes them for development, and continuously reviews the product backlog** to ensure the project continues to meet critical business needs. May be a customer, a product manager, or another stakeholder representative |
| **Scrum** | A **daily meeting** of the Scrum team reviewing progress and prioritizing the day's work. Ideally a short **face-to-face** meeting including the whole team |
| **ScrumMaster** | Responsible for **ensuring the Scrum process is followed** and guiding the team in effective use of Scrum; **interfaces with the rest of the company** and ensures the team is **not diverted by outside interference**. *Scrum developers are adamant the ScrumMaster should not be thought of as a project manager.* |
| **Sprint** | A development iteration, usually **2–4 weeks** long |
| **Velocity** | An estimate of **how much product backlog effort a team can cover in a single sprint**. Understanding velocity helps the team estimate what can be covered in a sprint and provides a basis for measuring improving performance |

**4. Know the sprint cycle.**
- Sprints are **fixed length**, normally **2–4 weeks**.
- The starting point for planning is the **product backlog** — the list of work to be done.
- The **selection phase** involves the whole project team working **with the customer** to select features and functionality from the product backlog for this sprint.
- Once agreed, **the team organizes itself** to develop the software.
- During this stage the team is **isolated from the customer and the organization**, with all communications channelled through the **Scrum master**, whose role is to **protect the development team from external distractions**.
- At the end of the sprint, the work done is **reviewed and presented to stakeholders**. The next sprint cycle then begins.

**5. The three Scrum roles in detail.**

**Product Owner**
- Has a **clear vision and goals** for the product; **represents the interests of the customers/stakeholders**
- Responsible for **maximizing the value of the Product** resulting from the work of the Development Team
- Balances **Scope, Schedule, Quality and Cost** to arrive at *the right product*
- **Responsible for the Product Backlog** — its content, availability and ordering

**Scrum Master**
- A **servant-leader** — focus is on the needs of the team members and those they serve (the customer), with the goal of achieving results in line with the organization's values, principles and business objectives
- **Teaches and coaches** the organization and team in adopting and using Scrum to perform at the highest level
- **Facilitates Scrum events**
- **Helps the team remove and prevent impediments**
- Also: arranges daily meetings, tracks the backlog, records decisions, measures progress against the backlog, communicates with customers and management outside the team

**Development Team**
- A team of **5 to 9 professionals** **responsible for the working product** at the end of each Sprint
- **Flat structure**: no titles other than developer, no sub-teams
- **Owns the Sprint Backlog** and decides how much is realistic for each Sprint
- Produces a **thoroughly tested, defect-free "Done" Product Increment** in each Sprint

**6. The three Scrum artifacts.**

**Product Backlog**
- An **ordered list** of everything known to be needed **in** or **for** the product to achieve maximum value
- The **single source of requirements** for any changes to be made to the product
- The **Product Owner is responsible** for it — content, availability and ordering
- **User Stories** are a way of expressing **Features** on the Product Backlog

**Sprint Backlog**
- The set of **Product Backlog Items (PBIs) selected for the Sprint**, plus a **plan for delivering the product Increment and realizing the Sprint Goal**
- The sprint backlog is **unchanged during the period of the Sprint**
- Items **not "Done"** by the end of the Sprint are **added back to the Product Backlog**
- **PBIs are broken down into tasks**; tasks are estimated in **hours, usually 1–16**. A task of more than 16 hours is **broken down further**

**Product Increment**
- At the end of each Sprint, "Done" items are **integrated and tested with the increments of all previous Sprints** → a **Potentially Shippable Product**
- The Product Increment is in a **potentially releasable state** — the Product Owner **could** release it if they wanted, as **the collection of completed features** (i.e. the delivery of a Release)

**7. The Scrum events.**

| Event | Time-box | Purpose |
|---|---|---|
| **Sprint** | **2–4 weeks** | A time-boxed event in which a **"Done" product increment is created**. Each sprint has a **Sprint Goal** which **does not change during the sprint**. **The time-box is never extended — the Sprint ends when the time-box expires.** At every sprint the Scrum Team will **inspect and adapt the Product and the Process**. |
| **Sprint Planning** | — | Two questions. *What work can get done?* — the PO presents the **ordered** PBIs; the Scrum Master **facilitates**, gives advice, asks questions, helps identify risks; the PBIs are **broken down to tasks estimated jointly in hours**; **only the Development Team can assess how much can be accomplished.** *How will the chosen work get done?* — the Development Team decides how it will build the functionality into a "Done" Increment, does planning and design to ensure the Sprint Goal is met (and may **invite others for technical or domain advice**); the Scrum Master helps with any arrangements needed. |
| **Daily Scrum** | **15 minutes**, same place and time each day | A **stand-up meeting** of the Scrum Team. **Three questions:** *"What did I do yesterday?"*, *"What will I do today?"*, *"Are there any issues or impediments?"* **Optimises team collaboration and performance** by inspecting work since the last Daily Scrum and adapting progress toward the **Sprint Goal**. Helps with better communication, decision-making and improved level of knowledge. |
| **Sprint Review** | **1 hr × number of weeks** in the Sprint | Held at the **end of each Sprint**, including the **Product Owner and key stakeholders**. **Hands-on with what's been built**, and active discussion of: *What is the current state of the Product?* and *What should be added or improved in future Sprints to deliver maximum value?* **Output: a revised Product Backlog by the Product Owner.** |
| **Sprint Retrospective** | **45 mins × number of weeks** in the Sprint | Between the **Scrum Team** at the end of the sprint, **after the Sprint Review**. Discusses: inspect **how** the sprint went with regard to **process, tool and people**; identify items that went well and potential improvements; **create an action plan** to implement improvements. **Input:** results from the Sprint. **Output:** lessons learned, improvements, and an action list for the next Sprint. |

> **Review vs. Retrospective — the classic exam distinction:** the **Review** inspects the **Product** (with stakeholders); the **Retrospective** inspects the **Process, tools and people** (team only).

**8. Sprint Burndown Chart.** A **graphical representation of work left to do versus time** (hours remaining on the y-axis, day of sprint on the x-axis). Purpose:
- Monitoring **project scope creep**
- Keeping the team **running on schedule**
- **Comparing the planned work against the team progression**

**9. Velocity.**
- Velocity is the **average size of Product Backlog items, in number of points, that the team can deliver during a Sprint**
- It **measures the amount of work done** during a Sprint — **a key metric in Scrum**
- **Evaluated only as an average. One Sprint's number is meaningless.**
- **Tasks** are estimated in **real units** using hours or quarter-days
- **Points cannot be converted to hours**

**10. Characteristics of a good Product Backlog — "DEEP".**

| Letter | Characteristic | Meaning |
|---|---|---|
| **D** | **Detailed appropriately** | Not all items in a PB will be at the same level of detail at the same time. **PBIs to be worked on soon should be at the top of the backlog, small in size and very detailed** so they can be worked on in the near sprint. **PBIs that will be worked on later can be larger and less detailed.** |
| **E** | **Estimated** | Each PBI has a **size estimate** corresponding to the effort required to develop it. The PO uses these estimates as one of several inputs to help determine a PBI's **priority** (and therefore position) in the PB. |
| **E** | **Emergent** | The product backlog is **never complete or frozen**. It is **continuously updated** based on a stream of economically valuable information that is constantly arriving. |
| **P** | **Prioritized** | Items are ordered; it is useful to prioritize the **near-term** items destined for the next few Sprints. |

**11. Product Backlog Grooming (Refinement).** Three principal activities:
1. **Creating and refining** (adding details to) PBIs
2. **Estimating** PBIs
3. **Prioritizing** PBIs

It is an **ongoing process** — items are reviewed and revised (estimated, inserted, re-prioritized, refined, deleted). **As a general rule the Development Team spends up to 10% of its time each sprint assisting with refinement activities.**

**12. User Stories.**
- User Stories are expressed in **everyday language** and describe a specific **goal (what)** from the **perspective of a user (who)**, along with the **reason (why)** they want it.
- Template:
  ```
  As a <role>,          ← WHO
  I want to <action>,   ← WHAT
  (so that <benefit>)   ← WHY
  ```
- **Epics** — a large body of work that can be broken down into multiple (user stories).

**13. The 3 Cs approach to user stories.**

| C | Meaning |
|---|---|
| **Card** | Represents the **capture of the statement of intent** of the user story. Traditionally written on **index cards or post-it notes**. **Cards can be re-organized when agile requirements change.** |
| **Conversation** | The **details behind** the User Story, **where the clearer understanding comes from**. Provides **shared context that cannot be achieved via formal documentation**. |
| **Confirmation** | Represents the **acceptance criteria** of the user story, which **confirms the intended value is delivered**. |

**14. Acceptance Criteria.** A set of **predefined scope and requirements that must be executed by developers to consider the user story finished.** May include:
- **Functional Criteria** — specific user functions or business processes that must be in place. *e.g. "A user is able to access a list of available reports."*
- **Non-functional Criteria** — specific non-functional conditions the implementation must meet, such as design elements. *e.g. "Edit buttons and Workflow buttons comply with the Site Button Design."*

**Characteristics of a good acceptance criterion:**
- **State an intent, not a solution** — e.g. *"The user can choose an account"* rather than *"The user can select the account from a drop-down"*
- **Independent of implementation** — ideally the phrasing would be the same whether implemented on web, mobile or a voice-activated system
- **Relatively high level** — not every detail needs to be in writing

**15. Teamwork and benefits of Scrum.**
- The whole team attends **short daily meetings** where all members share information, describe progress since the last meeting, problems that have arisen, and what is planned for the following day. **Everyone knows what is going on and, if problems arise, short-term work can be re-planned to cope.**

**Scrum benefits:**
- The product is broken down into a set of **manageable and understandable chunks**
- **Unstable requirements do not hold up progress**
- The whole team has **visibility of everything** and team communication is improved
- Customers see **on-time delivery of increments** and gain feedback on how the product works
- **Trust between customers and developers** is established and a positive culture is created in which everyone expects the project to succeed

**16. Key points.**
- Agile methods are **incremental development methods** focusing on rapid development, frequent releases, reducing process overheads by minimizing documentation, and producing high-quality code.
- Agile practices include: **user stories for system specification**, **frequent releases**, **continuous software improvement**, **test-first development**, **customer participation in the development team**.
- **Scrum is an agile method that provides a project management framework**, centred on a set of **sprints** — fixed time periods when a system increment is developed.
- **Many practical development methods are a mixture of plan-based and agile development.**
- **Scaling agile methods for large systems is difficult** — large systems need up-front design and some documentation, and organizational practice may conflict with the informality of agile approaches.

## Tutorial #5 — Scrum

### Q1. What considerations are crucial to deciding whether to adopt Agile/Scrum in a project?

**Learning points — group the considerations; a flat list scores poorly.**

**(a) Product and requirements**
- **Requirements volatility** — if requirements are unstable or poorly understood, agile's incremental negotiation is an advantage. If they are stable and fully known, plan-driven is cheaper and more predictable.
- **Product size and type** — agile is strongest for **small or medium-sized products for sale**, or **custom systems within an organization**. Very large systems need **up-front architectural design** and some documentation.
- **Criticality** — safety-critical / mission-critical / regulated systems need formal specification, certification evidence and auditable documentation that agile's "minimal documentation" does not supply.
- **Is early partial value useful?** Agile only pays if a partial system is worth having; a system that is worthless until 100% complete gains less from incremental delivery.

**(b) Customer**
- **Clear commitment from the customer to become involved** — this is the lecture's stated precondition. Scrum without an engaged, empowered Product Owner degrades into a daily-standup ritual with no prioritisation authority.
- **Can one person legitimately speak for all stakeholders?** A fragmented customer makes backlog ordering impossible.
- **Contract model** — fixed-price/fixed-scope contracts conflict with "responding to change over following a plan". Agile needs a time-and-materials or incremental-delivery contract.

**(c) Team**
- **Skill level** — agile works best when **team members have a relatively high skill level**; large organizations have a wide range of skills and abilities.
- **Team size** — Development Team of **5–9** (no more than 7 in the Sommerville definition); larger efforts require scaling frameworks, which is **difficult**.
- **Self-organisation and co-location** — the team must be able to organise itself and communicate face to face (the Daily Scrum assumes it).
- **Engineering practice maturity** — "potentially shippable" every sprint is impossible without automated testing, continuous integration and a real **Definition of Done**.

**(d) Organisation**
- **Quality procedures and standards** — large organizations often have **bureaucratic** procedures all projects must follow, likely **incompatible** with agile methods.
- **Management experience and willingness** — project managers **without experience of agile may be reluctant to accept the risk** of a new approach.
- **Cultural resistance**, especially where there is a long history of conventional systems engineering.
- **Ability to protect the team** — the ScrumMaster must genuinely be able to shield the team from outside interference; if the organisation reassigns people mid-sprint, the sprint commitment is meaningless.

**(e) The honest conclusion.** **There are no right or wrong software processes** (Ch. 8), and **many practical development methods are a mixture of plan-based and agile development**. The real decision is usually *which parts* of Scrum to adopt, not a binary choice.

### Q2. Discuss the ways of estimating Velocity in Scrum

**Learning points — there are three recognised approaches; give all three with their trade-offs.**

**Method 1 — Use historical data (the preferred method).**
Average the points actually completed over the **last 3 or so sprints** with the **same team, same sprint length**. Only **"Done"** items count — partially finished PBIs score zero and go back to the Product Backlog.
- *Why it's best:* it is **empirical** — it measures what this team actually achieves, including their real overheads, interruptions and definition of done.
- *Requires:* at least a few completed sprints, and a stable team, so it is unavailable at project start.
- Recall the lecture's constraint: velocity is **evaluated only as an average — one Sprint's number is meaningless.** A single sprint is noise. Many teams quote a *range* (e.g. worst/average/best of the last three sprints) rather than a point value, for forecasting.

**Method 2 — Run one or more sprints and observe (empirical bootstrapping).**
If there is no history, simply **run the first sprint**, take a conservative guess at how much to commit to, and **measure the observed velocity at sprint close**. The lecture's Sprint Backlog diagram labels exactly this: *"Close Sprint → Completed = observed velocity"*, with unfinished items going *"Into next sprint."*
- *Why use it:* fastest route to a trustworthy number; converges after 2–3 sprints.
- *Cost:* the first one or two sprints' forecasts are unreliable, so don't make external commitments on them.

**Method 3 — Forecast from team capacity (used only before any sprint has run).**
Compute available capacity and convert:
```
Available hours = (team members) × (days in sprint) × (hours/day) × (focus factor)
```
where the **focus factor** (typically 0.6–0.8) discounts meetings, support, leave, context switching, and the ~10% spent on backlog refinement. Then estimate how many points of top-priority PBIs fit into those hours, by task-breaking the top backlog items into tasks estimated in hours (**1–16 hours each**; anything longer is broken down further).
- *Caveat, and the thing the question is probing:* the lecture states flatly that **points cannot be converted to hours**. Points measure *relative size*; hours measure *duration*. So this method is a **one-off bootstrap heuristic**, not an ongoing measurement, and it must be replaced by observed velocity as soon as data exists.

**Supporting practices to mention:**
- **Planning Poker / relative sizing** against a reference story, using a Fibonacci-like scale, keeps point estimates consistent so that velocity means something sprint to sprint.
- **Velocity is a planning and forecasting tool, not a performance target.** Comparing velocities *between teams* is meaningless (points are team-relative) and using velocity as a productivity KPI reliably causes point inflation.
- Velocity must be **re-baselined** when team size, sprint length, or the Definition of Done changes.

### Q3. What are the characteristics of a good product backlog?

**Learning points — the expected answer is DEEP, with each letter explained, not just expanded.**

| | Characteristic | Explanation | Why it matters |
|---|---|---|---|
| **D** | **Detailed appropriately** | Items are **not all at the same level of detail at the same time**. Items near the top (to be worked on soon) are **small and highly detailed** so they can be taken into a near sprint; items further down are **larger and less detailed**. | Avoids wasting analysis effort on items that may be reprioritised away or never built — the backlog is a *just-in-time* document. |
| **E** | **Estimated** | Every PBI carries a **size estimate** of the effort to develop it. | The Product Owner uses size as one input (alongside value and risk) to decide **priority and position**; velocity is meaningless without sized items. |
| **E** | **Emergent** | The backlog is **never complete or frozen**; it is **continuously updated** as economically valuable information arrives. | This is Scrum's mechanism for "embrace change" — new learning enters through the backlog rather than through scope-change paperwork. |
| **P** | **Prioritized** | Items are **ordered**, with particular care given to the **near-term items destined for the next few sprints**. | The Development Team pulls from the top; ordering is how the Product Owner exercises their responsibility for **maximizing the value of the Product**. |

**Add these for full marks:**
- The backlog is the **single source of requirements** for any change to the product — if it's not in the backlog, it isn't being built.
- The **Product Owner is responsible** for its content, availability and ordering.
- It is kept DEEP by **ongoing grooming/refinement**: creating and refining PBIs, estimating them, and prioritizing them — with the Development Team spending **up to 10% of each sprint** assisting.
- Individual items should satisfy **INVEST** (Q4) — INVEST is the quality test for a *single* PBI; DEEP is the quality test for the *whole backlog*. Saying this explicitly connects Q3 and Q4 and is usually what the tutor is looking for.

### Q4. What does the INVEST mnemonic of Agile software development stand for?

> **Note:** INVEST is not on the slides in this folder — it comes from the user-story literature (Bill Wake) and is standard examinable Scrum material. It is the quality checklist for an **individual user story / PBI**.

| Letter | Criterion | What it means | Failure symptom |
|---|---|---|---|
| **I** | **Independent** | The story should be **self-contained** and not depend on other stories, so it can be scheduled and implemented in any order. | Stories that must be done in a fixed sequence prevent the PO from reprioritising freely. |
| **N** | **Negotiable** | A story is **not a contract**. It captures the *intent*; the details are worked out in **conversation** between the team and the Product Owner. | An over-specified story card removes the team's design latitude and the "Conversation" of the 3 Cs. |
| **V** | **Valuable** | The story must deliver **value to a user or customer** — which is why the template ends *"so that \<benefit\>"*. | Purely technical tasks phrased as stories ("refactor the DAO layer") have no user-visible value; they belong as tasks or technical PBIs with a stated business justification. |
| **E** | **Estimable** | The team must be able to **size it**. If they can't, the story needs more conversation, or a **spike** to reduce uncertainty. | Unestimable stories cannot be prioritised sensibly or fitted into a sprint. |
| **S** | **Small** | It must **fit comfortably within a single sprint** — ideally a few days of work. Large stories are **Epics** and must be split. | A story that spans sprints can never be "Done", so it never becomes part of a potentially shippable increment. |
| **T** | **Testable** | There must be **acceptance criteria** that let you objectively decide whether it is done — the **"Confirmation"** of the 3 Cs. | Without testable criteria, "Done" is a matter of opinion, which destroys the Product Increment guarantee. |

**Connections worth stating:**
- **INVEST ↔ the 3 Cs:** *Negotiable* is the **Card**, its elaboration is the **Conversation**, and *Testable* is the **Confirmation** (acceptance criteria).
- **INVEST ↔ DEEP:** INVEST is per-item quality; DEEP is whole-backlog quality. *Small* and *Estimable* in INVEST are what make *Detailed appropriately* and *Estimated* achievable in DEEP.
- **INVEST ↔ Chapter 2:** *Testable* here is the same property as **verifiable** in a traditional SRS, and *Independent*/*Small* is the agile analogue of **atomic**. The vocabulary changes; the underlying requirement-quality principle does not.

### Q5. Under Scrum, a Product Increment is both complete and potentially shippable. Why is it important to have working software delivered at the end of each Sprint?

**Learning points**

1. **It is the only honest measure of progress.** *"Working software over comprehensive documentation."* A design document or a 90%-complete module is unverifiable progress; a running increment is not. **The process is not visible** is the stated problem of incremental development (Ch. 8) — a shippable increment is the fix.
2. **It enables fast, real feedback.** Stakeholders get **hands-on with what's been built** at the Sprint Review, and the discussion is about *what is the current state of the Product* and *what should be added or improved*. Feedback on something you can use is qualitatively better than feedback on a specification. The output is a **revised Product Backlog**, so feedback is immediately actionable.
3. **It reduces risk early.** Integration, performance, and "we misunderstood the requirement" risks are discovered **every two to four weeks** instead of at the end. In a waterfall project these risks all land in the integration/testing phase, which is exactly where they are most expensive.
4. **It eliminates the integration big-bang.** Each sprint's "Done" items are **integrated and tested with the increments of all previous Sprints**, so integration debt never accumulates. There is no separate, unbounded integration phase.
5. **It enforces a real Definition of Done and prevents hidden debt.** "Potentially shippable" means **no further work such as testing is needed**. This stops the team from banking apparent progress that is actually undone work — the classic way velocity becomes a lie. Items **not "Done" are added back to the Product Backlog**, which makes incompleteness visible rather than hidden.
6. **It gives the business a real option.** The increment is in a **potentially releasable state** — the Product Owner **could** release it. That means the business can **release early, or stop the project at any sprint boundary, and still own something of value.** This is a genuine financial option created by the process.
7. **It builds trust.** The lecture lists it among Scrum's benefits: **customers see on-time delivery of increments and gain feedback; trust between customers and developers is established and a positive culture is created in which everyone expects the project to succeed.**
8. **It makes velocity meaningful.** Velocity measures **work done** — only "Done" counts. Without a strict shippable-increment rule, velocity measures work *started*, which is useless for forecasting.
9. **Acknowledge the caveat** — the lecture itself is honest about it: *"The idea is that this should be 'potentially shippable'… In practice, this is not always achievable."* A good answer notes that the discipline is the goal and that falling short of it is common, especially where the technical practices (automated testing, CI) are immature.

### Q6. Calculate the velocity and cost of the project

**Given**
- Total size of the product backlog = **64 points**
- Scrum Team = Product Owner + Scrum Master + **six** Development Team members = **8 people**
- Cost of **each member of the Scrum Team** per Sprint = **$2,000**
- Number of Sprints to complete the project = **8**

**Velocity**

Velocity is the average number of points the team delivers per sprint. The whole backlog (64 points) is to be completed in 8 sprints, so:

```
Velocity = Total backlog points ÷ Number of sprints
         = 64 points ÷ 8 sprints
         = 8 points per sprint
```

**Cost**

Note carefully: the cost is **per member of the Scrum Team**, and the **Scrum Team includes the Product Owner and the Scrum Master**, not just the six developers.

```
Scrum Team size   = 1 (PO) + 1 (SM) + 6 (Dev Team) = 8 members
Cost per Sprint   = 8 members × $2,000 = $16,000
Total project cost = $16,000 × 8 Sprints = $128,000
```

**Answer: velocity = 8 points per sprint; total project cost = $128,000.**

**Learning points**

1. **The trap is the team size.** The question deliberately says *"The Scrum Team consists of Product Owner, Scrum Master and six members in the Development Team"* and then *"the cost of each member in the Scrum Team"*. Using 6 instead of 8 gives $96,000 and is the intended wrong answer. **Read whose cost is being charged.**
2. **Velocity is in points per sprint**, not points per week and not hours. Always state the unit. The lecture is explicit: **points cannot be converted to hours**.
3. **Useful derived figure:** cost per point = $128,000 ÷ 64 = **$2,000 per point**, or equivalently $16,000 per sprint ÷ 8 points. This is the number a Product Owner uses for **cost-of-delay** and ROI decisions on individual PBIs — it is the practical reason velocity is tracked at all.
4. **Understand the direction of the real-world calculation.** Here you are told the number of sprints and asked to derive velocity. In practice it runs the other way: you **measure** velocity empirically over the first few sprints, then **forecast** `sprints needed = remaining backlog points ÷ velocity`, and from that derive cost and a release date. Being able to state the relationship in both directions is the point of the question.
5. **State the assumptions**, because a fully correct answer flags them: velocity is assumed constant across all 8 sprints (in reality it is an **average**, and **one sprint's number is meaningless**); the backlog is assumed not to grow (in reality it is **emergent**); and all 64 points are assumed to reach "Done".

---

# Chapter 11 — System Design & Software Architecture

**Reading:** [S] Ch. 6 Architectural design · [BD] Ch. 6 System Design: Decomposing the System, Ch. 7 System Design: Addressing Design Goals

## Learning Outcomes

**1. Place system design in the SDLC — the problem/solution boundary.**

```
 ◄────────────── PROBLEM ──────────────►│◄────────── SOLUTION ──────────►
 Requirements   Requirement   Requirements │ System    Object    Impl   Testing
 Elicitation →  Specification → Analysis   │ Design  → Design  →      →
                                Analysis   │  SW
                                 Model     │Architecture → Design → Source → Test
                                           │              Model     Code    Cases
        expressed in → structured by → implemented by → realized by → verified by
```

**2. Understand the two translations that precede design.**

**(a) Elicitation: understand what customers want.**
> From the **project mission statement** — *informal, vague, incomplete* — to the **Requirement Specification (SRS)** — *formal, technical, consistent*: functional & non-functional requirements, data dictionary, use case model.

**(b) Analysis: bridge the customer perspective to the software engineer perspective.**
> From the **SRS** (FRs & NFRs, data dictionary, use case model — *more about the customer*) to the **Analysis Model** (class diagram with **boundary, control, entity** classes; sequence diagram; state machine — *more about the software engineer*).

**3. Know why design is hard — three pressures.**

| Pressure | Detail |
|---|---|
| **Systems are getting larger** | Source size, binary size · number of users and user inputs · number of developers · life of the project (decades) · number of changes and versions. **Complexity is increasing** — environment, technologies, hardware. |
| **Projects are constrained** | **Cost is critical** (limited budget/resource) · **schedule constraints** (tight schedule) · **maintenance** |
| **Non-functional requirements must be met** | Performance · Availability · Security · Scalability · Extensibility |

**4. Define software architecture.**

> **Software architecture is a description of the high-level structure of a software system in terms of architectural elements and the interactions between them.**
>
> *"Abstractly, software architecture involves the description of **elements** from which systems are built, **interactions** among those elements, **patterns** that guide their composition, and **constraints** on these patterns."* — Shaw and Garlan, 1996

**5. Reduce it to the formula:**
> **Software Architecture = { Components, Connectors }**

- **Components** — a unit of software that **performs some function at run-time**. *Examples:* programs, objects, processes, clients, servers, databases.
- **Connectors** — the **interactions among components**: communication, coordination, or cooperation. *Examples:* shared variable access, procedure calls, remote procedure calls, communication protocols, data streams, transaction streams.
  > **Implementations of connectors are usually distributed over many system components and often do not correspond to discrete elements of the running system.** (This is why connectors are easy to miss when reverse-engineering an architecture.)

*Worked example — a WWW client/server architecture:* on the **client**, `Presentation Manager`, `UI Manager`, `Access Manager`, `Protocol Manager`, `Stream Manager`, `Cache Manager`, plus `External Viewer`, `View Control` and `File System`; on the **server**, `HTTP Server`, `Path Resolver`, `Access List`, `Stream Manager`, `CGI`; connected by the **HTTP protocol**.

**6. Know the three properties of an architecture.**
- **Architecture is abstract** — the details of the components and connectors are **hidden**.
- **Architecture is about structure and interactions** — focus on the **topology**: components, and data and control communication.
- **Architecture is purposeful** — it exists to **demonstrate or analyse the properties of interest**, and to serve as design documentation and transferable knowledge about software design and evaluation.

**7. Know the five inputs that shape a design.**

| Input | Content |
|---|---|
| **Functional Requirement** | Dynamic Models · Analysis Object Models |
| **Non-functional Requirement** | Efficiency · Reliability · Robustness · Security · Maintainability |
| **Design Principles** | Modularity · Abstraction · Open-Closed · Reusability |
| **Design Patterns** | Layered Architecture · Client and Server · Data Centered |
| **Constraints** | Languages · Libraries · Communications |

Summarised at the end of the deck as: **Why** (functional + non-functional requirements) → **What** (design principles + design patterns) → **How** (constraints).

**8. Know the design principles by name.**
- **Modularity**
- **Abstraction**
- **Open-Closed Principle** — open for extension, closed for modification
- **Reusability**
- **Single Responsibility Principle**
- **Principle of Least Knowledge** (Law of Demeter)
- **Don't Repeat Yourself (DRY)**
- **Separation of Concerns: Low Coupling and High Cohesion**

> *The lecture's worked illustration of abstraction + open-closed:* `ResourceManager` holds a `datastore` reference typed to the **abstract** `DataStoreInterface` (`retrieveMap()`, `createIncident(time, desc)`, `dispatchResource()`), which is realized by `FlatFileImpl`, `MySQLImpl` and `DB2Impl`. Adding a new storage technology requires **no change** to `ResourceManager`. This is the same structural idea you will apply as the **Strategy** pattern in Tutorial #6.

**9. Define architectural style.**

> One of the hallmarks of software architectural design is the use of **idiomatic patterns of system organization**. **An architectural style defines a family of systems in terms of a pattern of structural organization.** It provides:
> - A **vocabulary of component and connector types**
> - A **set of constraints** on how they can be combined
> - **One or more semantic models** that specify how to determine a system's overall properties from the properties of its parts

**What a style specifies:**
- **A set of component types** — e.g. filters in pipe-and-filter styles; MVC
- **A set of connectors** — subroutine calls, remote procedure calls, data streams, sockets
- **A topological structure**
- **A set of semantic constraints** — e.g. *filters in a pipe-and-filter architecture do not share state with each other*; *one layer can only call the service provided by the lower layer in a layered system*

**What a style does NOT specify** (i.e. what varies between systems in the same style):
- **The number of components involved** — a pipe-and-filter architecture may have 2 filters connected by 1 pipe, or 20 filters connected by 19 pipes
- **The mechanism of interaction** — in a layered system, the call to the lower layer may be a local procedure call, a remote procedure call, or another IPC mechanism
- **The function of the system and components** — one component may be a database, but the kind of data may vary

**10. Reproduce the taxonomy of architectural styles.**

| Family | Styles |
|---|---|
| **Data flow** | Batch sequential · Pipe-and-filter |
| **Data-centered** | Repository · Blackboard |
| **Virtual machine** | Interpreter · Rule-based system |
| **Call and return** | Main program and subroutine · Object-oriented · **Layered system** |
| **Independent components** | Communicating processes — **client & server** · Event systems (**Implicit invocation** · Explicit invocation) |

**11. Know the Layered Architecture in detail — the style the tutorial uses.** The lecture's **3-Layered Architecture** example:

```
┌────────────────────────────────────────────────────┐
│ Presentation                                       │
│   ┌─────────────┐          ┌──────────────┐        │
│   │ FieldOfficerUI│        │ DispatcherUI │        │
│   └─────────────┘          └──────────────┘        │
└────────────────────────────────────────────────────┘
          ╎ ╎ ╎   (dependencies point downward only)
┌────────────────────────────────────────────────────┐
│ App Logic                                          │
│  ┌────────────┐  ┌────────────┐  ┌──────────────┐  │
│  │  Resource  │  │    Map     │  │   Incident   │  │
│  │ Management │  │ Management │  │  Management  │  │
│  └────────────┘  └────────────┘  └──────────────┘  │
└────────────────────────────────────────────────────┘
          ╎ ╎ ╎
┌────────────────────────────────────────────────────┐
│ Persistent Data                                    │
│              ┌──────────────┐                      │
│              │   Database   │                      │
│              └──────────────┘                      │
└────────────────────────────────────────────────────┘
```

Note the mapping to Chapter 5's stereotypes: **Presentation ↔ `<<boundary>>`**, **App Logic ↔ `<<control>>`**, **Persistent Data ↔ `<<entity>>`**.

The semantic constraint: **one layer can only call the service provided by the lower layer.** A *closed* architecture permits calls only to the layer immediately below; an *open* architecture permits calls to any lower layer (faster, but weaker modularity).

The **Android platform stack** is given as a real-world example: `Applications` → `Application Framework` → `Libraries` + `Android Runtime` → `Linux Kernel`.

**12. Know the trade-offs of the Independent Components / event-based style.**

| Advantages | Disadvantages |
|---|---|
| **Modifiability** by decoupling the computation | **Components are independent** — did the message arrive? *Solution: complicated protocols* |
| **Concurrent execution** | **Correctness is hard to achieve** |
| **Scalability** | |
| **Easy integration** | |

**13. Understand the design process as a descriptive model.** Designers do not go straight from requirements to a design. The lecture's model: *External requirements → Identify nature of requirements → Requirements specification → Analyze & build model of problem → **Postulate design solution(s)** → Validate each solution against the model → **Mismatches between model and requirements** → either **Revise design solution**, **Seek new solution**, or **Elaborate solution** → **Compare solutions** against specification/comparison criteria → **Selected design solution** → validated 'Blueprint' model.* New constraints feed back in throughout.

Key insight: design is **generate-and-test with multiple candidate solutions**, not a single derivation.

**14. Remember what architecture is *for*.** The deck's closing motivation slide lists the properties architecture buys you: **Maintainability · Extensibility · New Features · Performance · Scalability.** These are precisely the **non-functional requirements** from Chapter 2 — the architecture is where they are satisfied or lost.

## Tutorial #6 Q1 — Architectural Styles for the GES Conceptual Model

> *"Refer to the conceptual model developed in Tutorial #3 Q1. Use proper architectural styles to model dependencies among boundary, control, and entity objects."*
>
> (The tutorial sheet says "Tutorial#4"; the conceptual model is actually developed in Tutorial #3 Q1 — the numbering in the handout is off by one here.)

**Learning points**

1. **The answer is a Layered Architecture**, because the question hands you the three stereotypes and asks you to organise their *dependencies*. The three-layer mapping is the one the lecture draws explicitly:

   | Layer | Stereotype | GES examples |
   |---|---|---|
   | **Presentation** | `<<boundary>>` | `ShipmentArrivalUI`, `AllocationUI`, `SiloMonitorUI`, `ProcessingPlantNotifier` |
   | **Application Logic** | `<<control>>` | `ShipmentController`, `AllocationController`, `SiloConditionController` |
   | **Persistent Data** | `<<entity>>` | `Shipment`, `Silo`, `Grain`, `Allocation`, `ProcessingPlant` + the database/repository |

2. **The architecture is in the *direction and restriction* of the dependencies, not in the boxes.** State the constraint explicitly: **dependencies point downward only** — Presentation depends on App Logic, App Logic depends on Persistent Data; **never the reverse, and never Presentation directly to Persistent Data** (in a closed layered architecture). Drawing three boxes without stating this rule misses the point of the question.

3. **Justify the style against non-functional requirements**, since that is what architecture is for:
   - **Modifiability / maintainability** — the UI can be replaced (desktop → mobile, which is exactly what Tutorial #6 Q2 then does) without touching business logic.
   - **Supportability** — the database can be swapped (recall the NFR from Chapter 2: *"replaceable with any commercial product supporting standard SQL queries"*) without touching the layers above.
   - **Reusability** — the same control layer serves multiple boundary classes.
   - **Separation of concerns, low coupling, high cohesion** — named design principles from the deck.

4. **Mention the second, complementary style.** A well-rounded answer notes that within the Presentation layer, **MVC** (an instance of the **Independent Components / Implicit Invocation** family) applies: the View observes the Model and is notified of changes. Naming MVC here sets up **Tutorial #7 Q1**, where the Observer pattern is the required answer — MVC's model–view notification *is* Observer.

5. **Consider a third style if the GES description warrants it.** If GES continuously ingests sensor readings (silo temperature/humidity), an **event-based / implicit invocation** style for the monitoring sub-system is defensible, with the stated trade-off: **modifiability, concurrency, scalability and easy integration** versus **"was the message received?"** and **correctness is hard to achieve**.

6. **Draw it as a UML package or component diagram** with the layers as packages and dashed dependency arrows between them — and keep every arrow pointing down.

7. **Common mistakes to avoid:** putting entity classes in the top layer because the UI "shows" them; letting a boundary class call the database directly "for performance"; and having an entity class call a control class (which inverts the dependency and destroys the layering).

---

# Chapter 12 — Design Patterns *(no lecture slides in this folder)*

**Reading:** [BD] Ch. 8 *Object Design: Reusing Pattern Solutions* · [S] §7.2 Design patterns · [F] Ch. 3, 5

> **Why this chapter is here.** Tutorial #6 Q2 and all of Tutorial #7 examine design patterns, but no pattern deck is present in this folder. The Lecture 12 deck names *Design Patterns* as one of the five design inputs and lists the principles (**Open-Closed, Modularity, Abstraction, Reusability, Single Responsibility, Least Knowledge, DRY**) that patterns exist to satisfy. The content below is reconstructed from [BD] Ch. 8, which is the course's prescribed source.

## Learning Outcomes

**1. Define a design pattern.** A **template solution** to a recurring design problem — a named, documented pairing of a **problem context** with a **solution structure** and its **consequences**. A pattern is not code and not a library; it is a reusable *design*.

**2. Know the four elements of a pattern description:** **Name** · **Problem** (the design issue and its context) · **Solution** (the participating classes, their responsibilities and collaborations) · **Consequences** (the trade-offs).

**3. Know the three categories.**

| Category | Purpose | Examples in this course |
|---|---|---|
| **Creational** | Abstract the instantiation process | **Abstract Factory**, **Factory Method**, Builder, Singleton |
| **Structural** | Compose classes/objects into larger structures | **Adapter**, **Bridge**, Composite, Facade, Proxy |
| **Behavioral** | Assign responsibility and manage communication | **Strategy**, **Observer**, Command, State, Template Method |

**4. Know the design principles patterns serve.**
- **Open-Closed Principle** — software entities should be **open for extension, closed for modification**. This is *the* principle behind Strategy, Observer and Abstract Factory, and the reason all three appear in the tutorials.
- **Program to an interface, not an implementation.**
- **Favour composition over inheritance.**
- **Encapsulate what varies.** — The single most useful heuristic for choosing a pattern: find the thing that changes, and put it behind an interface.
- **Low coupling / high cohesion** (named in Lecture 12).

### The four patterns examined by the tutorials

#### Strategy (Behavioral)
**Problem.** A family of algorithms or policies exists; the client must be able to use any of them, and new ones must be addable without changing the client.

**Structure.**
```
┌──────────────┐ strategy ┌─────────────────────────┐
│   Context    │─────────▷│   «interface» Strategy  │
│              │          ├─────────────────────────┤
│ setStrategy()│          │ + algorithmOperation()  │
│ request()    │          └─────────────────────────┘
└──────────────┘                     △ △ △
                                     ╎ ╎ ╎  (realization)
                  ┌──────────────────┘ ╎ └──────────────────┐
         ┌──────────────────┐ ┌──────────────────┐ ┌──────────────────┐
         │ ConcreteStrategyA│ │ ConcreteStrategyB│ │ ConcreteStrategyC│
         └──────────────────┘ └──────────────────┘ └──────────────────┘
```

**Roles.** *Context* holds a reference to a Strategy and delegates to it; *Strategy* declares the common interface; *ConcreteStrategy* implements one algorithm; the *Client* chooses and injects the concrete strategy.

**Consequences.** + New algorithms are added without modifying the Context (Open-Closed). + Eliminates conditional branching over algorithm type. − The client must know which strategies exist in order to choose one — **this is the hole that the Factory pattern fills** (Tutorial #7 Q2).

#### Observer (Behavioral)
**Problem.** A one-to-many dependency: when one object changes state, an unknown and varying number of dependents must be notified, without the subject being coupled to their concrete classes.

**Structure.**
```
┌────────────────────────────┐              ┌──────────────────────┐
│         Subject            │ observers *  │ «interface» Observer │
├────────────────────────────┤─────────────▷├──────────────────────┤
│ + attach(Observer)         │              │ + update()           │
│ + detach(Observer)         │              └──────────────────────┘
│ + notify()                 │                        △
└────────────────────────────┘                        ╎
             △                                        ╎
             ╎                              ┌──────────────────────┐
┌────────────────────────────┐    subject   │  ConcreteObserver    │
│      ConcreteSubject       │◁─────────────│ + update()           │
│ - state                    │              │ - observerState      │
│ + getState() / setState()  │              └──────────────────────┘
└────────────────────────────┘
```

**Roles.** *Subject* keeps the observer list and provides `attach`/`detach`/`notify`; *Observer* declares `update()`; *ConcreteSubject* holds the state and calls `notify()` when it changes; *ConcreteObserver* implements `update()` and reacts.

**Push vs. pull.** *Push* — the subject passes the changed data in `update(data)`. *Pull* — the subject passes only itself, and each observer calls `getState()` to fetch what it needs. Pull suits observers with **differing interests**.

**Consequences.** + Subject and observers are loosely coupled; observers can be added/removed **at run time**. + Supports broadcast. − Unexpected cascading updates; the subject cannot easily tell which observers care about *which* change (addressed by registering interest per topic).

> Observer is the notification mechanism inside **MVC** — the View observes the Model.

#### Abstract Factory (Creational)
**Problem.** Provide an interface for creating **families of related or dependent objects** without specifying their concrete classes. The client should be insulated from *which* family is in use.

**Structure.**
```
                       ┌─────────────────────────────┐
     client ──────────▷│ «interface» AbstractFactory │
                       ├─────────────────────────────┤
                       │ + createProductA()          │
                       │ + createProductB()          │
                       └─────────────────────────────┘
                              △             △
                              ╎             ╎
              ┌───────────────────┐  ┌───────────────────┐
              │ ConcreteFactory1  │  │ ConcreteFactory2  │
              └───────────────────┘  └───────────────────┘
                     │ creates              │ creates
                     ▼                      ▼
              ProductA1, ProductB1   ProductA2, ProductB2
                     ╎                      ╎
                     └──────▷ «interface» AbstractProductA / B ◁──────┘
```

**Consequences.** + Isolates concrete classes; the client depends only on interfaces. + Makes exchanging whole product families easy and enforces consistency among products. − Supporting a *new kind of product* requires changing the AbstractFactory interface and every concrete factory.

**Factory Method** is the simpler single-product sibling: a method that defers instantiation of one product to subclasses.

#### Bridge / Adapter (Structural) — useful supporting patterns
- **Bridge** — decouple an abstraction from its implementation so that the two can vary independently. Structurally similar to Strategy, but the *intent* differs: Strategy varies **behaviour/policy**; Bridge varies **platform/implementation**. Either is defensible for the Tutorial #6 Q2 network-protocol problem, provided you justify the intent.
- **Adapter** — convert the interface of an existing class into the interface the client expects. Relevant when the concrete protocol or notification libraries are third-party and have incompatible APIs.

**5. Know how to choose a pattern** — the method the tutorials actually test:
1. **Find what varies** in the problem statement. Look for lists ("LAN, WiFi, Bluetooth, 3G, 4G"), words like *variety*, *vary greatly*, *change over time*, and requirements for *future extension with minimal impact*.
2. **Classify the variation:** varying **algorithm/policy** → Strategy · varying **set of interested parties** → Observer · varying **object families to create** → Abstract Factory · varying **number of parts in a whole** → Composite · varying **state-dependent behaviour** → State.
3. **Check it against the Open-Closed Principle** — can you add a new variant without modifying existing classes? If not, the pattern is wrongly applied.
4. **Name the roles explicitly** when you present the class diagram. Marks are awarded for stating *which class plays which role*, not just for drawing boxes.

## Tutorial #6 Q2 — Network Access Protocols

> *"The elevator manager uses a mobile device to process shipment and allocation. This mobile device must deal with a variety of network access protocols (LAN, WiFi, Bluetooth, 3G, 4G). Furthermore, we want to be able to deal with further network protocols with minimal impacts on the application."*
> *(a) Identify the design problem and apply an appropriate design pattern.*
> *(b) Draw a UML class diagram depicting the classes in the design pattern and explain their roles.*

### (a) The design problem

**Learning points**

1. **Name the problem precisely before naming the pattern.** The problem is: *the application must perform the same logical operation — send/receive data — using any one of several interchangeable network access mechanisms, where the mechanism is selected at run time and the set of mechanisms must be extensible without modifying the application.*
2. **Point at the evidence in the text.** "a **variety** of network access protocols" → a family of interchangeable algorithms. "deal with **further** network protocols with **minimal impacts** on the application" → the **Open-Closed Principle** stated in plain English.
3. **State what goes wrong without a pattern.** A naive implementation puts a `switch`/`if-else` over protocol type in the application code, repeated at every call site. Every new protocol means editing and re-testing the application — modification, not extension. High coupling, low cohesion, violation of Open-Closed and Single Responsibility.
4. **The pattern: Strategy.** (A **Bridge** answer is also defensible if you argue the intent is decoupling the application abstraction from varying platform implementations. Say which you chose and why — the tutorial has no single model answer.)

### (b) Class diagram and roles

```
┌─────────────────────────────┐            ┌──────────────────────────────────┐
│    NetworkConnection        │ strategy   │  «interface» NetworkProtocol     │
│        «Context»            │───────────▷│          «Strategy»              │
├─────────────────────────────┤            ├──────────────────────────────────┤
│ - protocol : NetworkProtocol│            │ + connect() : boolean            │
├─────────────────────────────┤            │ + send(data : Message) : boolean │
│ + setProtocol(p)            │            │ + receive() : Message            │
│ + send(data)                │            │ + disconnect()                   │
│ + receive()                 │            └──────────────────────────────────┘
└─────────────────────────────┘                  △    △    △    △    △
            △                                    ╎    ╎    ╎    ╎    ╎
            │ uses                 ┌─────────────┘    ╎    ╎    ╎    └──────────────┐
┌───────────────────────┐   ┌──────────────┐ ┌─────────────┐ ┌────────────┐ ┌────────────┐
│ ShipmentAllocationApp │   │ LANProtocol  │ │WiFiProtocol │ │ Bluetooth  │ │ ThreeG /   │
│   (mobile device)     │   │              │ │             │ │  Protocol  │ │ FourG      │
└───────────────────────┘   └──────────────┘ └─────────────┘ └────────────┘ └────────────┘
                              «ConcreteStrategy»  ...            ...            ...
```

**Roles to explain in the answer:**

| Class | Role | Responsibility |
|---|---|---|
| `NetworkConnection` | **Context** | Holds a reference to a `NetworkProtocol` and **delegates** all network operations to it. Provides `setProtocol()` so the protocol can be swapped **at run time**. It never names a concrete protocol class. |
| `NetworkProtocol` | **Strategy** (abstract class / interface) | Declares the **common interface** all protocols must honour — `connect()`, `send()`, `receive()`, `disconnect()`. This is the stable abstraction that makes the Context closed to modification. |
| `LANProtocol`, `WiFiProtocol`, `BluetoothProtocol`, `ThreeGProtocol`, `FourGProtocol` | **ConcreteStrategy** | Each implements the interface for one specific access technology, encapsulating all of its protocol-specific detail. |
| `ShipmentAllocationApp` | **Client** | The GES mobile application. Uses `NetworkConnection` and is entirely unaware of which concrete protocol is in play. |

**Why this satisfies the requirement — say this explicitly:**
- **Adding `5GProtocol` means writing one new class that implements `NetworkProtocol`.** No existing class is edited. That is "further network protocols with **minimal impacts on the application**", and that is the **Open-Closed Principle** satisfied.
- The protocol can be **changed at run time** (e.g. hand off from WiFi to 4G when the manager walks out of range) because the Context holds a reference, not a hard-coded type.
- All protocol-specific detail is **encapsulated** in one class each → **high cohesion**; the application depends only on an interface → **low coupling**.
- Conditional logic over protocol type **disappears from the application**.

**The known weakness — flag it, because Tutorial #7 Q2 is built on it:** *somebody still has to decide which `ConcreteStrategy` to instantiate, and that somebody currently has to `new` a concrete class.* The client is therefore still coupled to the concrete protocol classes at the point of creation. **That is the gap the Factory pattern closes.**

---

## Tutorial #7 Q1 — Notifying Processing Plants

> *"Once grain arrives or leaves, GES will notify processing plants. The processing plants can register their interests in specific types of grains. GES will notify the registered processing plants using the plant's preferred communication means, including email, SMS, or a combination of these means. The interests and preferred communication means of the processing plants vary greatly, and the processing plants can change their interests and preferred communication means over time. Furthermore, GES should be easily extended to support new communication means once they become available."*

### (a) The design problem and pattern

**Learning points**

1. **Read carefully — there are *two* independent variations in this problem**, and a full-mark answer identifies both:
   - **Variation 1 — who gets notified.** "processing plants can **register** their interests" · "can **change** their interests over time" · a varying number of interested parties. → **Observer pattern**.
   - **Variation 2 — how they get notified.** "**email, SMS, or the combination** of these" · "preferred communication means **vary greatly**" · "can **change** over time" · "**easily extended** to support new communication means". → **Strategy pattern** (and the "combination" clause additionally suggests **Composite**).

   Answering with Observer alone addresses half the question; the "extended to support new communication means" sentence is there specifically to make you reach for a second pattern.

2. **Map the roles for Observer:** GES (specifically a `GrainEvent`/`Silo`/`GrainInventory` class) is the **Subject**; each `ProcessingPlant` is a **ConcreteObserver**. Registration of interest is `attach()`; de-registration is `detach()`; grain arrival/departure triggers `notify()`.

3. **Handle "interests in specific types of grains."** A plain Observer broadcasts to *all* observers. Two standard refinements, either acceptable if justified:
   - **Topic/subject-per-grain-type:** one Subject per `GrainType`, so plants attach only to the types they care about. Cleanest, and scales.
   - **Filtered notification:** a single Subject, with each observer registering a `Set<GrainType>` of interests; `notify()` consults the registration before calling `update()`. Simpler, fewer objects.
   State which you chose. This is exactly the known weakness of Observer — *the subject cannot easily tell which observers care about which change* — and showing you know how to address it is worth marks.

4. **Use pull, not push**, or justify push. Because plants have differing interests, `update(subject, event)` letting each plant fetch what it needs is a better fit than pushing a fixed payload.

### (b) Class diagram and roles

```
┌─────────────────────────────────────┐          ┌──────────────────────────────┐
│          GrainInventory             │ observers│  «interface» GrainObserver   │
│            «Subject»                │    *     │        «Observer»            │
├─────────────────────────────────────┤─────────▷├──────────────────────────────┤
│ - observers : List<GrainObserver>   │          │ + update(e : GrainEvent)     │
├─────────────────────────────────────┤          └──────────────────────────────┘
│ + attach(o, interests : Set<Grain>) │                        △
│ + detach(o)                         │                        ╎
│ + notify(e : GrainEvent)            │          ┌──────────────────────────────┐
│ + grainArrived(...) / grainLeft(...)│          │     ProcessingPlant          │
└─────────────────────────────────────┘          │   «ConcreteObserver»         │
                                                 ├──────────────────────────────┤
                                                 │ - interests : Set<GrainType> │
                                                 │ - channel : NotificationChannel│
                                                 ├──────────────────────────────┤
                                                 │ + update(e : GrainEvent)     │
                                                 │ + setChannel(c)              │
                                                 └──────────────────────────────┘
                                                              │ channel
                                                              ▼
                                   ┌──────────────────────────────────────────┐
                                   │ «interface» NotificationChannel          │
                                   │            «Strategy»                    │
                                   ├──────────────────────────────────────────┤
                                   │ + send(plant, message)                   │
                                   └──────────────────────────────────────────┘
                                        △        △         △          △
                                        ╎        ╎         ╎          ╎
                          ┌─────────────┘  ┌─────┘   ┌─────┘    ┌─────┘
                  ┌──────────────┐ ┌──────────────┐ ┌──────────────┐ ┌─────────────────────────┐
                  │EmailChannel  │ │ SMSChannel   │ │ PushChannel  │ │ CompositeChannel        │
                  │«ConcreteStr.»│ │«ConcreteStr.»│ │   (future)   │ │ «Composite»             │
                  └──────────────┘ └──────────────┘ └──────────────┘ │ - children : List<NC>   │
                                                                     │ + send() → forwards to  │
                                                                     │   every child           │
                                                                     └─────────────────────────┘
```

**Roles to explain:**

| Class | Role | Responsibility |
|---|---|---|
| `GrainInventory` | **Subject** | Maintains the observer registry with each plant's grain-type interests; calls `notify()` when grain arrives or leaves. Knows nothing about plants beyond the `GrainObserver` interface. |
| `GrainObserver` | **Observer** interface | Declares `update()`. Decouples the subject from `ProcessingPlant`. |
| `ProcessingPlant` | **ConcreteObserver** | Registers/de-registers its interests; on `update()`, formats the message and **delegates delivery to its `NotificationChannel`**. Holds its preferred channel, changeable at run time via `setChannel()`. |
| `NotificationChannel` | **Strategy** interface | The stable abstraction for *how* a message is delivered. |
| `EmailChannel`, `SMSChannel`, … | **ConcreteStrategy** | Each encapsulates one delivery mechanism. |
| `CompositeChannel` | **Composite** | Holds a list of `NotificationChannel`s and forwards `send()` to each — this is what satisfies *"or the combination of these means"*. Because it **implements the same interface** it holds, a plant that wants email + SMS is configured identically to one that wants email alone. |

**Why this satisfies each stated requirement:**

| Requirement in the problem | Satisfied by |
|---|---|
| "plants can **register** their interests" | `attach(observer, interests)` on the Subject |
| "interests … **change over time**" | `attach`/`detach` at run time; Observer explicitly supports dynamic registration |
| "notify using the plant's **preferred** communication means" | each `ProcessingPlant` holds its own `NotificationChannel` |
| "email, SMS, **or the combination**" | `CompositeChannel` |
| "communication means … **change over time**" | `setChannel()` — the strategy is swappable at run time |
| "**easily extended** to support new communication means" | a new `ConcreteStrategy` class; **no existing class is modified** (Open-Closed) |
| "interests and means **vary greatly**" | each plant is configured independently; no conditional logic anywhere |

---

## Tutorial #7 Q2 — Completing the Tutorial #6 Design

> *"Refer to the design pattern solution developed in Question 2 of Tutorial #6. (a) Discuss what is missing in the solution. (b) Add a relevant design pattern to the design solution to complete the design."*

### (a) What is missing

**Learning points**

1. **The Strategy pattern solves *use*, not *creation*.** `NetworkConnection` is beautifully decoupled from the concrete protocols — but **someone still has to execute `new WiFiProtocol()`**. Wherever that line lives, that class is coupled to every concrete protocol class.
2. **Spell out the consequences**, because "something creates it" is not yet an answer:
   - The **client/application remains coupled to every concrete `NetworkProtocol` subclass**, which is precisely the coupling Strategy was introduced to remove. The decoupling is incomplete — it has merely moved.
   - The **Open-Closed Principle is still violated at the creation point**: adding `5GProtocol` requires editing the selection code (a `switch` on protocol type, or a chain of `if`s), re-compiling and re-testing it. So "minimal impacts on the application" is **not actually achieved** by Strategy alone.
   - **Selection logic is likely duplicated** at every point in the mobile application that needs a connection → violates **DRY**.
   - There is **no single place** to apply cross-cutting creation concerns: device-capability checks (does this handset have Bluetooth?), configuration, credentials, connection pooling, fallback ordering.
   - **Testability** suffers — you cannot substitute a mock protocol without editing the creation code.
3. **Optionally note a second gap:** nothing in the Tutorial #6 design decides *which* protocol is appropriate for the current environment (signal availability, cost, bandwidth), nor handles **run-time switching** when the chosen protocol becomes unavailable.

### (b) The pattern to add: Factory

Use a **Factory Method** or **Abstract Factory** (either is acceptable; Abstract Factory is the stronger answer if related objects must be created together — e.g. a protocol *and* its matching connection-configuration or security handler).

```
┌───────────────────────┐          ┌───────────────────────────────────────┐
│ ShipmentAllocationApp │─────────▷│ «interface» NetworkProtocolFactory    │
│       «Client»        │          │           «AbstractFactory»           │
└───────────────────────┘          ├───────────────────────────────────────┤
            │                      │ + createProtocol() : NetworkProtocol  │
            │ uses                 │ + createConfig()   : ConnectionConfig │
            ▼                      └───────────────────────────────────────┘
┌───────────────────────┐                   △       △       △       △
│  NetworkConnection    │                   ╎       ╎       ╎       ╎
│      «Context»        │     ┌─────────────┘  ┌────┘  ┌────┘  ┌────┘
└───────────────────────┘ ┌──────────────┐┌──────────────┐┌──────────────┐┌──────────────┐
            │             │ LANFactory   ││ WiFiFactory  ││BluetoothFact.││ FourGFactory │
            │ strategy    │«ConcreteFact»││              ││              ││              │
            ▼             └──────────────┘└──────────────┘└──────────────┘└──────────────┘
┌───────────────────────────┐      │ creates       │ creates      │ creates     │ creates
│ «interface»               │      ▼               ▼              ▼             ▼
│  NetworkProtocol          │◁── LANProtocol   WiFiProtocol  BluetoothProt.  FourGProtocol
│       «Strategy»          │
└───────────────────────────┘
```

A simpler **Factory Method / parameterised factory** variant, which is perfectly acceptable for this question:

```
┌─────────────────────────────────────────────┐
│          NetworkProtocolFactory             │
├─────────────────────────────────────────────┤
│ + createProtocol(type : ProtocolType)       │
│                       : NetworkProtocol     │
│ + createBestAvailable() : NetworkProtocol   │
└─────────────────────────────────────────────┘
          │ creates (the only class that knows the concrete types)
          ▼
   LANProtocol | WiFiProtocol | BluetoothProtocol | ThreeGProtocol | FourGProtocol
```

**Roles to explain:**

| Class | Role | Responsibility |
|---|---|---|
| `NetworkProtocolFactory` | **AbstractFactory / Factory** | Declares the creation interface. The client depends only on this. |
| `WiFiFactory`, `FourGFactory`, … | **ConcreteFactory** | Each knows how to instantiate and configure exactly one protocol family. |
| `NetworkProtocol` | **AbstractProduct** / **Strategy** | The product interface — the same interface the Context consumes. |
| `WiFiProtocol`, … | **ConcreteProduct** / **ConcreteStrategy** | The created objects. |
| `NetworkConnection` | **Context** | Unchanged from Tutorial #6 — it still just delegates. |
| `ShipmentAllocationApp` | **Client** | Now asks the factory for a protocol; **never names a concrete class**. |

**Why this completes the design — the argument to make:**

1. **All knowledge of concrete protocol classes is now confined to one place** (the factory). The application depends only on `NetworkProtocolFactory` and `NetworkProtocol`, both abstractions. *Program to an interface, not an implementation.*
2. **Open-Closed is now genuinely satisfied end to end.** Adding `5GProtocol` means adding a `FiveGProtocol` class **and** a `FiveGFactory` class — zero modifications to the application, the Context, or any existing protocol. The requirement "deal with further network protocols **with minimal impacts on the application**" is finally met in full.
3. **The selection logic exists once**, in the factory, where device-capability checks, fallback ordering and configuration can live cohesively.
4. **Strategy and Factory are complementary, not alternatives** — this is the examinable insight. **Factory answers "which object do I create?"; Strategy answers "how do I use it interchangeably?"** Neither is complete without the other when the set of implementations must be extensible. Saying this sentence explicitly is usually what the tutor is listening for.
5. *Optional extension worth a line:* if exactly one connection manager should exist for the device, the factory can be a **Singleton**; and a **Facade** over `NetworkConnection` + factory would give the rest of the GES app a single simple entry point.

---

# Chapter 13 — Testing I: Equivalence Class Partitioning & Boundary Value Analysis *(no lecture slides in this folder)*

**Reading:** [S] Ch. 8 *Software testing* · [BD] Ch. 11 *Testing* · Copeland, *A Practitioner's Guide to Software Test Design*

## Learning Outcomes

**1. Know why systematic test design is necessary.** Exhaustive testing is impossible — the input space of even a trivial function is astronomically large. **Testing can show the presence of defects but not their absence** (Dijkstra). The goal of test design is therefore to **choose a small set of test cases with a high probability of finding defects**, and to be able to **justify** the choice.

**2. Distinguish black-box from white-box testing.**

| | **Black-box (functional)** | **White-box (structural)** |
|---|---|---|
| Basis | The **specification** — what the software should do | The **code** — its internal structure |
| Knowledge needed | None of the implementation | Full source access |
| Techniques | Equivalence class partitioning, boundary value analysis, decision tables, state-based testing, use-case testing | Statement coverage, branch coverage, path coverage, basis path testing (Ch. 14) |
| Finds | Missing functionality, wrong behaviour against spec | Untested code, dead code, logic errors inside a unit |
| Misses | Untested code paths the spec doesn't mention | Missing functionality — you cannot test code that was never written |

The two are **complementary**; neither replaces the other.

**3. Equivalence Class Partitioning (ECP).**

**Principle.** Partition the input domain into **equivalence classes** — sets of values for which the program is expected to behave **equivalently**. If one member of a class reveals a defect, the others are assumed to as well; if one passes, the others are assumed to pass. Therefore **test one representative value per class**.

**How to derive classes.** For each input condition, identify:
- **Valid** equivalence classes — inputs the specification says are acceptable
- **Invalid** equivalence classes — inputs outside the acceptable set

Common rules:

| If the input condition specifies… | Then derive… |
|---|---|
| a **range** (e.g. 1–999) | 1 valid class (within), 2 invalid classes (below, above) |
| a **specific value** or count | 1 valid class, 2 invalid (one more, one fewer) |
| a **set of values** treated differently | 1 valid class **per member**, 1 invalid class |
| a **boolean / must-be condition** | 1 valid class, 1 invalid class |

**Benefit.** Reduces the number of test cases dramatically while retaining coverage of behaviourally distinct inputs, and makes the coverage argument **explicit and reviewable**.

**4. Boundary Value Analysis (BVA).**

**Principle.** **Defects cluster at the boundaries of equivalence classes** — off-by-one errors, `<` written for `<=`, wrong initialisation, wrong loop termination. ECP tells you *which* partitions exist; BVA tells you *which values within them* to pick.

**How to derive boundary values.** For each boundary of each equivalence class, test:
- the value **on** the boundary
- the value **immediately below** it
- the value **immediately above** it

(Often written as the **min−1, min, min+1, max−1, max, max+1** set, plus a **nominal** value inside the class.)

**Robustness testing** extends BVA to include values **outside the legal range entirely**, to check error handling.

**5. Combining multiple inputs.**

| Strategy | Description | Number of tests |
|---|---|---|
| **Weak normal** | Vary **one** variable at a time through its boundary values; hold all others at a **nominal** value. Only valid values used. | ~4n + 1 for n variables |
| **Strong normal** | **Cartesian product** of all valid classes across all variables. | multiplicative — grows fast |
| **Weak robust** | Weak normal plus **invalid** values, one at a time. | ~6n + 1 |
| **Strong robust** | Cartesian product including invalid classes. | largest |

**The single-fault assumption** justifies the "weak" strategies: failures rarely result from two simultaneous faults, so varying one input at a time while holding others nominal is usually sufficient and far cheaper.

**6. Document test cases properly.** A test case is not an input — it is a tuple:
> **Test Case ID · Description / class or boundary covered · Precondition · Input values · Expected output · Actual output · Pass/Fail**

**Expected output must be derived from the specification *before* execution**, otherwise you are not testing, you are observing.

## Tutorial #8 — Equivalence Class and Boundary Value Testing (GES Silo)

> *"A silo cannot accept any more grain if its temperature or humidity exceeds normal levels. Humidity ranges 0–100%, the normal humidity is 35–50%. Temperature ranges −10–100 °C, the normal temperature is 40–60 °C."*
> *(a) Determine equivalence classes and boundary values for humidity and temperature.*
> *(b) Systematically design a set of test cases to test whether the silo can accept grain or not, based on its temperature and humidity.*

### Reading the specification first — the step students skip

The spec defines **two nested ranges per variable**, which produces **five** equivalence classes each, not two:
- the **physically/legally valid measurement range** (humidity 0–100, temperature −10–100) — outside this, input is **invalid** and should be rejected or flagged as a sensor error;
- the **normal (acceptable) sub-range** inside it (humidity 35–50, temperature 40–60) — inside this, the silo may accept grain;
- and the **valid-but-abnormal** regions above and below normal — inside this, the silo **rejects** grain.

Also note the acceptance rule: *"cannot accept any more grain if its temperature **or** humidity exceeds normal levels"* →
> **ACCEPT ⟺ (35 ≤ humidity ≤ 50) AND (40 ≤ temperature ≤ 60)**

### (a) Equivalence classes and boundary values

**HUMIDITY** (range 0–100%, normal 35–50%)

| EC ID | Equivalence class | Condition | Validity | Expected silo behaviour |
|---|---|---|---|---|
| **H1** | Below measurable range | h < 0 | **Invalid** | Reject input / sensor error |
| **H2** | Valid but too low | 0 ≤ h < 35 | Valid | **Cannot accept grain** |
| **H3** | **Normal** | 35 ≤ h ≤ 50 | Valid | **Can accept grain** (if temperature also normal) |
| **H4** | Valid but too high | 50 < h ≤ 100 | Valid | **Cannot accept grain** |
| **H5** | Above measurable range | h > 100 | **Invalid** | Reject input / sensor error |

**Humidity boundary values** (on, just below, just above each boundary):

| Boundary | Values to test | Class moved between |
|---|---|---|
| Lower limit of range, 0 | **−1, 0, 1** | H1 ↔ H2 |
| Lower limit of normal, 35 | **34, 35, 36** | H2 ↔ H3 |
| Upper limit of normal, 50 | **49, 50, 51** | H3 ↔ H4 |
| Upper limit of range, 100 | **99, 100, 101** | H4 ↔ H5 |

Nominal (typical) values: H2 → 20, H3 → 42, H4 → 75.

**TEMPERATURE** (range −10 to 100 °C, normal 40–60 °C)

| EC ID | Equivalence class | Condition | Validity | Expected silo behaviour |
|---|---|---|---|---|
| **T1** | Below measurable range | t < −10 | **Invalid** | Reject input / sensor error |
| **T2** | Valid but too low | −10 ≤ t < 40 | Valid | **Cannot accept grain** |
| **T3** | **Normal** | 40 ≤ t ≤ 60 | Valid | **Can accept grain** (if humidity also normal) |
| **T4** | Valid but too high | 60 < t ≤ 100 | Valid | **Cannot accept grain** |
| **T5** | Above measurable range | t > 100 | **Invalid** | Reject input / sensor error |

**Temperature boundary values:**

| Boundary | Values to test | Class moved between |
|---|---|---|
| Lower limit of range, −10 | **−11, −10, −9** | T1 ↔ T2 |
| Lower limit of normal, 40 | **39, 40, 41** | T2 ↔ T3 |
| Upper limit of normal, 60 | **59, 60, 61** | T3 ↔ T4 |
| Upper limit of range, 100 | **99, 100, 101** | T4 ↔ T5 |

Nominal values: T2 → 20, T3 → 50, T4 → 80.

### (b) Systematic test case design

**Strategy: weak robust equivalence testing + boundary value analysis.** Vary **one** variable at a time across its classes and boundaries, holding the other at a **nominal normal** value (humidity 42%, temperature 50 °C). This applies the **single-fault assumption** and keeps the suite small; then add a handful of combination cases to cover the AND rule.

**Part 1 — Humidity varied, temperature held at nominal normal (50 °C)**

| TC | Humidity (%) | Temp (°C) | Covers | Expected result |
|---|---|---|---|---|
| TC01 | −1 | 50 | H1 boundary (below range) | **Invalid input / sensor error** |
| TC02 | 0 | 50 | H2 boundary (min of range) | **Reject grain** (too low) |
| TC03 | 1 | 50 | H2 boundary | **Reject grain** (too low) |
| TC04 | 20 | 50 | H2 nominal | **Reject grain** (too low) |
| TC05 | 34 | 50 | H2 boundary (just below normal) | **Reject grain** (too low) |
| TC06 | **35** | 50 | **H3 boundary (min normal)** | **ACCEPT grain** |
| TC07 | 36 | 50 | H3 boundary | **ACCEPT grain** |
| TC08 | 42 | 50 | H3 nominal | **ACCEPT grain** |
| TC09 | 49 | 50 | H3 boundary | **ACCEPT grain** |
| TC10 | **50** | 50 | **H3 boundary (max normal)** | **ACCEPT grain** |
| TC11 | 51 | 50 | H4 boundary (just above normal) | **Reject grain** (too high) |
| TC12 | 75 | 50 | H4 nominal | **Reject grain** (too high) |
| TC13 | 99 | 50 | H4 boundary | **Reject grain** (too high) |
| TC14 | 100 | 50 | H4 boundary (max of range) | **Reject grain** (too high) |
| TC15 | 101 | 50 | H5 boundary (above range) | **Invalid input / sensor error** |

**Part 2 — Temperature varied, humidity held at nominal normal (42%)**

| TC | Humidity (%) | Temp (°C) | Covers | Expected result |
|---|---|---|---|---|
| TC16 | 42 | −11 | T1 boundary (below range) | **Invalid input / sensor error** |
| TC17 | 42 | −10 | T2 boundary (min of range) | **Reject grain** (too cold) |
| TC18 | 42 | −9 | T2 boundary | **Reject grain** (too cold) |
| TC19 | 42 | 20 | T2 nominal | **Reject grain** (too cold) |
| TC20 | 42 | 39 | T2 boundary (just below normal) | **Reject grain** (too cold) |
| TC21 | 42 | **40** | **T3 boundary (min normal)** | **ACCEPT grain** |
| TC22 | 42 | 41 | T3 boundary | **ACCEPT grain** |
| TC23 | 42 | 50 | T3 nominal | **ACCEPT grain** |
| TC24 | 42 | 59 | T3 boundary | **ACCEPT grain** |
| TC25 | 42 | **60** | **T3 boundary (max normal)** | **ACCEPT grain** |
| TC26 | 42 | 61 | T4 boundary (just above normal) | **Reject grain** (too hot) |
| TC27 | 42 | 80 | T4 nominal | **Reject grain** (too hot) |
| TC28 | 42 | 99 | T4 boundary | **Reject grain** (too hot) |
| TC29 | 42 | 100 | T4 boundary (max of range) | **Reject grain** (too hot) |
| TC30 | 42 | 101 | T5 boundary (above range) | **Invalid input / sensor error** |

**Part 3 — Combination cases for the AND decision rule**

Weak (one-at-a-time) testing never exercises the case where **both** conditions are abnormal, or where they **disagree**. Add a decision-table-style block:

| TC | Humidity | Temp | Humidity normal? | Temp normal? | Expected result |
|---|---|---|---|---|---|
| TC31 | 42 | 50 | ✓ | ✓ | **ACCEPT** |
| TC32 | 20 | 50 | ✗ (low) | ✓ | **Reject** |
| TC33 | 42 | 80 | ✓ | ✗ (high) | **Reject** |
| TC34 | 75 | 80 | ✗ (high) | ✗ (high) | **Reject** |
| TC35 | 20 | 20 | ✗ (low) | ✗ (low) | **Reject** |
| TC36 | 35 | 40 | ✓ (both at min boundary) | ✓ | **ACCEPT** |
| TC37 | 50 | 60 | ✓ (both at max boundary) | ✓ | **ACCEPT** |
| TC38 | 51 | 61 | ✗ (both just outside) | ✗ | **Reject** |

### Learning points

1. **Derive five classes per variable, not two.** The question gives *two* nested ranges per variable and the most common error is collapsing them — producing only "normal / not normal" and missing the invalid-input classes entirely. The phrase "Humidity **ranges** 0–100%" is the measurement range; "the **normal** humidity is 35–50%" is the acceptance range. They mean different things and have different expected behaviours.
2. **BVA is about the *transition points*, which are the normal-range edges.** TC05/TC06 (34 → 35) and TC10/TC11 (50 → 51) are the highest-value tests in the entire suite, because they are exactly where a `<` versus `<=` error lives. Likewise TC20/TC21 (39 → 40) and TC25/TC26 (60 → 61). If you only had four tests, use these.
3. **Pick the "hold" value deliberately.** When varying humidity, hold temperature at a **nominal normal** value (50 °C, not 40 or 60). If you held it at a boundary or an abnormal value, every test would reject regardless of the humidity value and the humidity partitioning would be untested — a classic masking error.
4. **State the decision rule explicitly before designing combinations.** *"cannot accept … if temperature **or** humidity exceeds normal"* ⟹ ACCEPT requires **both** normal. Part 3 is a small decision table exercising all four combinations of the two conditions.
5. **Boundary values depend on the data type.** These tables assume **integers**, so "just below 35" is 34. If humidity is a real number, the adjacent values are 34.9 and 35.1 (or the smallest representable increment). **Say which you assumed** — it is a legitimate TBD and raising it shows you understand what a boundary is.
6. **Every test case needs an expected result derived from the spec.** The tables above pair every input with a predicted outcome. A list of input values with no expected results is not a test suite.
7. **Note what the specification does not say** — these are genuine requirements gaps to raise with the client, exactly as in Tutorial #1:
   - What should the system do with an **out-of-range reading** (h = −1, t = 150)? Reject the reading, raise a sensor alarm, or treat as "cannot accept"? The spec is silent; TC01/TC15/TC16/TC30 expose this.
   - Are the normal limits **inclusive**? "normal humidity is 35–50%" reads as inclusive, which is what the tables assume — but it is worth confirming, since it determines whether TC06 and TC10 accept or reject.
   - What happens on a **missing or stale** reading?
8. **Count the saving.** A naive attempt to test every integer pair in range would be 102 × 112 ≈ 11,400 tests. This suite is **38**, and every one of them is justified by a named equivalence class or boundary. That justification — not the count — is what makes it a *systematic* design.

---

# Chapter 14 — Testing II: Control Flow Testing *(no lecture slides in this folder)*

**Reading:** [S] §8.1 Development testing · [BD] Ch. 11 · McCabe, *A Complexity Measure* (1976)

## Learning Outcomes

**1. Build a Control Flow Graph (CFG).** A directed graph in which:
- **Nodes** represent **statements or blocks of sequential statements** that always execute together (a *basic block*)
- **Edges** represent **transfers of control** between nodes
- **Predicate nodes** are nodes with **two or more outgoing edges** — they correspond to decisions (`if`, `while`, `for`, `case`)
- There is one **entry** node and (conventionally) one **exit** node

**Construction rules:**

| Construct | CFG fragment |
|---|---|
| Sequence | one node per statement, or a single node for a run of statements with no branching |
| `if (c) { A }` | predicate node → A → merge; predicate node → merge |
| `if (c) { A } else { B }` | predicate node → A → merge; predicate node → B → merge |
| `while (c) { A }` | predicate node → A → **back-edge to the predicate node**; predicate node → exit |
| `do { A } while (c)` | A → predicate node → back-edge to A; predicate node → exit |
| `switch` | predicate node with one edge per case |

**2. Compute Cyclomatic Complexity, V(G).** Three equivalent formulas:

```
(1)  V(G) = E − N + 2        E = number of edges, N = number of nodes
(2)  V(G) = P + 1            P = number of predicate (decision) nodes
(3)  V(G) = R                R = number of enclosed regions + 1 (the outer region),
                                 for a planar graph
```

**Interpretation of V(G):**
- The number of **linearly independent paths** through the code — i.e. the size of the **basis path set**
- An **upper bound** on the number of test cases needed for branch coverage, and a **lower bound** on the number needed for path coverage
- A **complexity metric**: values above ~10 indicate a module that should be considered for refactoring

**Compound conditions.** If a decision contains compound predicates joined by `&&` or `||`, each atomic condition can be treated as a **separate predicate node** (short-circuit evaluation makes this the literal control flow). Convention varies:
- Counting the whole decision as **one** predicate node → the simpler, conventional answer
- Counting **each atomic condition** → the more rigorous answer, giving a higher V(G)

**Always state which convention you used.**

**3. Know the coverage criteria, in increasing strength.**

| Criterion | Requirement | Note |
|---|---|---|
| **Statement coverage** | Every statement executed at least once | Weakest; an `if` with no `else` reaches 100% without ever taking the false branch |
| **Branch (decision) coverage** | Every **decision outcome** (true *and* false) taken at least once | **Subsumes statement coverage** |
| **Condition coverage** | Every **atomic condition** evaluates both true and false | Does not necessarily subsume branch coverage |
| **Branch/condition coverage** | Both of the above | |
| **MC/DC** | Each atomic condition shown to **independently affect** the decision outcome | Required for avionics (DO-178B Level A) |
| **Path coverage** | Every **execution path** taken | Infeasible in general — a single loop gives unbounded paths |
| **Basis path coverage** | Every path in a **basis set** of V(G) linearly independent paths | **The practical compromise** — McCabe's method |

**4. Derive a basis path set.**
1. Draw the CFG
2. Compute V(G)
3. Identify a **baseline path** — typically the simplest path through the code
4. Derive each further path by **flipping one decision** at a time relative to an already-derived path, keeping all other decisions as they were
5. Stop at V(G) paths
6. **Design a test case (input values + expected output) for each path**

A path is **linearly independent** if it introduces at least one edge not present in any previously derived path.

**5. Know the limitation.** Some basis paths may be **infeasible** — no input can cause them, because of dependencies between decisions. When this happens, say so explicitly and substitute the nearest feasible path. Reporting an infeasible path with a fabricated test case is worse than reporting the infeasibility.

## Tutorial #9 — Control Flow Testing

**The code under test:**

```java
public int sum(int n, int upperbound){
 1   int result, i;
 2   result = 0;
 3   i = 0;
 4   if(n < 0) {
 5       n = -n;
 6   }
 7   while(i < n && result <= upperbound){
 8       i = i + 1;
 9       result = result + i;
10   }
11   if(result <= upperbound){
12       System.out.println("The sum is " + result);
13   } else {
14       System.out.println("The sum is too large!");
15   }
16   return result;
}
```

### (a) Control Flow Graph

**Node definitions** (grouping sequential statements into basic blocks):

| Node | Statements | Type |
|---|---|---|
| **N1** | 1, 2, 3 — `result = 0; i = 0;` | entry / block |
| **N2** | 4 — `if (n < 0)` | **predicate** |
| **N3** | 5 — `n = -n;` | block |
| **N4** | 7 — `while (i < n && result <= upperbound)` | **predicate** |
| **N5** | 8, 9 — `i = i + 1; result = result + i;` | block (loop body) |
| **N6** | 11 — `if (result <= upperbound)` | **predicate** |
| **N7** | 12 — print "The sum is …" | block |
| **N8** | 14 — print "The sum is too large!" | block |
| **N9** | 16 — `return result;` | exit |

**The graph:**

```
                        ┌─────┐
                        │ N1  │  result=0; i=0
                        └──┬──┘
                           │
                        ┌──▼──┐
                        │ N2  │  if (n < 0)
                        └┬───┬┘
                 true    │   │   false
                ┌────────┘   └────────┐
             ┌──▼──┐                  │
             │ N3  │  n = -n          │
             └──┬──┘                  │
                └────────┐   ┌────────┘
                      ┌──▼───▼──┐
            ┌────────▶│   N4    │  while (i<n && result<=upperbound)
            │         └┬───────┬┘
            │   true   │       │   false
            │       ┌──▼──┐    │
            │       │ N5  │    │   i=i+1; result=result+i
            │       └──┬──┘    │
            └──────────┘       │   (back edge)
                               │
                            ┌──▼──┐
                            │ N6  │  if (result <= upperbound)
                            └┬───┬┘
                     true    │   │   false
                          ┌──▼─┐ └─┬────┐
                          │ N7 │   │ N8 │
                          └──┬─┘   └─┬──┘
                             └───┬───┘
                              ┌──▼──┐
                              │ N9  │  return result
                              └─────┘
```

**Edge list (E = 11):**

| # | Edge | Meaning |
|---|---|---|
| 1 | N1 → N2 | sequence |
| 2 | N2 → N3 | `n < 0` **true** |
| 3 | N2 → N4 | `n < 0` **false** |
| 4 | N3 → N4 | sequence after negation |
| 5 | N4 → N5 | loop condition **true** (enter body) |
| 6 | N5 → N4 | **back edge** (re-test condition) |
| 7 | N4 → N6 | loop condition **false** (exit loop) |
| 8 | N6 → N7 | `result <= upperbound` **true** |
| 9 | N6 → N8 | `result <= upperbound` **false** |
| 10 | N7 → N9 | sequence |
| 11 | N8 → N9 | sequence |

### (b) Cyclomatic Complexity

**Method 1 — edges and nodes:**
```
E = 11,  N = 9
V(G) = E − N + 2 = 11 − 9 + 2 = 4
```

**Method 2 — predicate nodes:**
```
Predicate nodes: N2 (if n<0), N4 (while), N6 (if result<=upperbound)
P = 3
V(G) = P + 1 = 3 + 1 = 4
```

**Method 3 — regions:** the planar CFG encloses 3 regions (the `if` at N2, the loop at N4–N5, the `if/else` at N6), plus the outer region: **V(G) = 4.** ✔ All three agree.

> **V(G) = 4**

**Note on the compound condition.** The `while` guard is `i < n && result <= upperbound` — two atomic conditions. Treating it as **one** decision (the convention used above) gives **V(G) = 4**. Treating each atomic condition as its own predicate node gives **P = 4** and **V(G) = 5**. State your convention; **4** is the expected answer.

### (c) Test cases for 100% statement coverage and 100% branch coverage

**Which statements are hard to reach?**
- Line 5 (`n = -n`) requires **n < 0**
- Lines 8–9 require the loop body to execute **at least once**
- Line 12 requires **result ≤ upperbound** at line 11
- Line 14 requires **result > upperbound** at line 11

**Test suite:**

| TC | n | upperbound | Trace | Output | Return |
|---|---|---|---|---|---|
| **TC1** | **−3** | **10** | `n<0` true → n=3; loop runs 3× (i=1,r=1; i=2,r=3; i=3,r=6); exits when i=3 is not < 3; 6 ≤ 10 true | `The sum is 6` | 6 |
| **TC2** | **3** | **2** | `n<0` false; loop: i=1,r=1 (1≤2 ok); i=2,r=3; re-test i=2<3 true but 3≤2 **false** → exit; 3 ≤ 2 false | `The sum is too large!` | 3 |

**Statement coverage check:**

| Line | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 | 15 | 16 |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| TC1 | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | — | — | — | ✓ |
| TC2 | ✓ | ✓ | ✓ | ✓ | — | — | ✓ | ✓ | ✓ | ✓ | ✓ | — | ✓ | ✓ | ✓ | ✓ |

**→ 100% statement coverage with 2 test cases.**

**Branch coverage check** (6 outcomes across 3 decisions):

| Decision | Outcome | Covered by |
|---|---|---|
| `if (n < 0)` | **true** | TC1 |
| `if (n < 0)` | **false** | TC2 |
| `while (…)` | **true** (enter body) | TC1, TC2 |
| `while (…)` | **false** (exit loop) | TC1, TC2 |
| `if (result <= upperbound)` | **true** | TC1 |
| `if (result <= upperbound)` | **false** | TC2 |

**→ 100% branch coverage with the same 2 test cases.**

**Bonus — condition coverage on the compound guard.** The loop can exit for two different reasons, and the two tests cover both: TC1 exits because **`i < n` became false**; TC2 exits because **`result <= upperbound` became false**. So this suite also achieves condition coverage on the `while` guard — worth pointing out, as it is the kind of detail that distinguishes a complete answer.

### (d) Basis set of linearly independent paths, with test cases and expected outcomes

**V(G) = 4**, so the basis set contains **4** paths. Taking P1 as the baseline and flipping one decision at a time:

| Path | Node sequence | Decisions | New edge(s) introduced |
|---|---|---|---|
| **P1** (baseline) | N1 → N2 → N4 → N6 → N7 → N9 | n<0 **F**; loop **0×**; result≤ub **T** | — (baseline) |
| **P2** | N1 → N2 → **N3** → N4 → N6 → **N8** → N9 | n<0 **T**; loop **0×**; result≤ub **F** | N2→N3, N3→N4, N6→N8, N8→N9 |
| **P3** | N1 → N2 → N4 → **N5** → N4 → N6 → N7 → N9 | n<0 **F**; loop **1×**; result≤ub **T** | N4→N5, N5→N4 |
| **P4** | N1 → N2 → N4 → N5 → N4 → N5 → N4 → N6 → N8 → N9 | n<0 **F**; loop **2×**; result≤ub **F** | (independent combination — exits loop via the second sub-condition) |

**Test cases:**

| Path | Test case (n, upperbound) | Execution trace | Expected output | Expected return |
|---|---|---|---|---|
| **P1** | **n = 0, upperbound = 10** | result=0, i=0; `0<0` false; `0<0` false → loop skipped; `0 ≤ 10` true | `The sum is 0` | **0** |
| **P2** | **n = −1, upperbound = −1** | result=0, i=0; `−1<0` **true** → n=1; guard: `0<1` true **but** `0 ≤ −1` **false** → loop skipped; `0 ≤ −1` **false** | `The sum is too large!` | **0** |
| **P3** | **n = 1, upperbound = 10** | result=0, i=0; `1<0` false; iter 1: i=1, result=1; re-test `1<1` false → exit; `1 ≤ 10` true | `The sum is 1` | **1** |
| **P4** | **n = 3, upperbound = 2** | result=0, i=0; `3<0` false; iter 1: i=1, r=1; guard `1<3` ∧ `1≤2` true; iter 2: i=2, r=3; guard `2<3` true ∧ `3≤2` **false** → exit; `3 ≤ 2` **false** | `The sum is too large!` | **3** |

**Verification of linear independence.** Each path introduces at least one edge not present in the paths before it: P2 adds the `n<0` true branch (N2→N3, N3→N4) and the else branch (N6→N8, N8→N9); P3 adds the loop body edges (N4→N5, N5→N4); P4 cannot be expressed as a linear combination of P1–P3 (matching the N4→N5 coefficient forces a combination that produces the wrong N6→N7 coefficient). All four are independent, and 4 = V(G), so this is a valid **basis set**.

### Learning points

1. **Group statements into basic blocks, don't draw one node per line.** Lines 1–3 have no branching and always execute together, so they are one node. Lines 8–9 likewise. Doing it line-by-line still gives the correct V(G) — because `E − N + 2` is invariant under splitting a node in a sequence — but it makes the graph unreadable. Check this yourself: splitting one node into two adds one node **and** one edge, so V(G) is unchanged. That invariance is a useful sanity check.
2. **Lines 6, 10, 13 and 15 are closing braces**, not statements. They do not become nodes, but they *are* counted in the question's numbering, so make sure your statement-coverage table is consistent about them.
3. **Verify V(G) with at least two of the three formulas.** `E − N + 2` and `P + 1` are independent calculations; if they disagree, you have miscounted edges (the usual culprit is forgetting the **back edge** N5 → N4, or forgetting that the `while` predicate has **two** outgoing edges).
4. **The `while` loop contributes exactly one predicate node with two edges out, plus one back edge.** A common error is drawing the loop body's exit as going to N6 directly — it must return to the condition node, because the condition is re-evaluated.
5. **Branch coverage subsumes statement coverage** — so once you have shown 100% branch coverage, 100% statement coverage follows. It is still worth presenting the statement table to show the reasoning, but stating the subsumption shows understanding.
6. **Two tests suffice for parts (c), four for part (d) — and the difference is the point of the question.** Branch coverage asks only that each *decision outcome* occurs somewhere; basis path testing asks that V(G) *independent combinations* of outcomes occur. Basis paths are strictly stronger, which is why V(G) is described as an upper bound on the tests needed for branch coverage and a lower bound for path coverage.
7. **Check every basis path for feasibility, and adjust.** This question has a trap: the "obvious" second basis path — take the `n<0` branch, skip the loop, and print "The sum is" — is **infeasible**. If `n < 0` then after `n = -n` we have n ≥ 1, so `i < n` is true at the first test; the only way to skip the loop is `result <= upperbound` being false at entry, i.e. `0 > upperbound`. But then at line 11 `result` is still 0, so `0 <= upperbound` is false there too, forcing the **else** branch. Hence P2 must end at N8, not N7 — which is exactly why its test case is `n = −1, upperbound = −1`. Finding this is most of the marks for part (d).
8. **A basis set is not unique.** Different baseline choices give different valid basis sets of the same size. What must hold: exactly V(G) paths, each introducing something new, each (ideally) feasible, and each with a concrete test case and a **predicted** expected outcome.
9. **Always give expected outputs, not just inputs.** Part (d) explicitly asks for "a test case (input parameters) **and expected outcome**" — and the expected outcome must include both the printed string **and** the return value, since `sum` does both.
10. **Note the latent defect this exercise exposes.** `sum(n, upperbound)` is documented as "the sum of 1..n", but when `n < 0` it silently computes the sum of `1..|n|` — and when the loop exits early on `result > upperbound` it returns a **partial** sum while reporting "too large". Both are specification questions, not coding errors *per se*, and control-flow testing alone will never flag them — you need the **black-box** techniques of Chapter 13 to compare behaviour against the specification. This is the clearest illustration in the whole course of why white-box and black-box testing are complementary.

---

# Quick-Reference Appendix

## A. The deliverable chain, end to end

```
Client's informal problem statement
        ↓ Requirements Elicitation (Ch. 2–4)
Project Mission Statement · Functional Requirements · Non-Functional Requirements
Use Case Diagram + Use Case Descriptions · Data Dictionary · UI Prototype
        ↓ Requirements Analysis (Ch. 5–6)
Conceptual model: Class Diagram (boundary / control / entity)
Dynamic model: State Machine Diagrams · Activity Diagrams · Sequence Diagrams
        ↓ Specification (Ch. 7)
Software Requirements Specification  ──── SIGN-OFF ────
        ↓ System Design (Ch. 11)
Software Architecture: components + connectors, architectural style
        ↓ Object Design (Ch. 12)
Design patterns applied · Design Model
        ↓ Implementation
Source Code
        ↓ Testing (Ch. 13–14)
Test Cases → Test Report → User Acceptance Test
```

## B. Which UML diagram, when

| Question you're answering | Diagram | Chapter |
|---|---|---|
| Who uses the system, and to do what? | **Use Case Diagram** | 3 |
| What are the steps of this interaction? | **Use Case Description** (text) | 4 |
| What things exist, and how do they relate? | **Class Diagram** | 5 |
| What condition is this object in, and what changes it? | **State Machine Diagram** | 6 |
| What is the flow of work / what happens next? | **Activity Diagram** | 6 |
| How do these screens connect? | **Dialog Map** (a state machine) | 6 |
| In what order do objects send messages? | **Sequence Diagram** | 6 (ref.) |
| How is the system structured at a high level? | **Package / Component Diagram** | 11 |

## C. Relationship notation cheat sheet

| Relationship | Meaning | Notation |
|---|---|---|
| Generalization (class parent) | "is a" | solid line, **black** arrowhead → parent |
| Generalization (abstract parent) | "is a" | solid line, **white** arrowhead → parent |
| Realization (interface) | "implements" | **dashed** line, white arrowhead → interface |
| Association | "uses / relates to" | solid line |
| Aggregation | "**is part of**" | solid line, **white** diamond at the whole |
| Composition | "**is entirely made of**" — parts die with the whole | solid line, **black** diamond at the whole |
| Dependency | "**uses temporarily**" | **dotted** line, open arrowhead → supplier |
| `<<include>>` | reuse — **always** performed | dashed arrow, stereotype, → included use case |
| `<<extend>>` | optional — performed **only** in unusual circumstances | dashed arrow, stereotype, → **base** use case |

## D. Acronyms and mnemonics

| | |
|---|---|
| **SDLC** | Software Development Life Cycle |
| **PLC** | Project Life Cycle |
| **PMS** | Project Mission Statement |
| **SRS** | Software Requirements Specification |
| **FR / NFR** | Functional / Non-Functional Requirement |
| **TBD** | To Be Determined — an uncertainty to raise with the client; **never guess** |
| **COTS** | Commercial Off-The-Shelf |
| **XP** | eXtreme Programming |
| **TDD** | Test-Driven Development |
| **PBI** | Product Backlog Item |
| **PO / SM** | Product Owner / Scrum Master |
| **DEEP** | **D**etailed appropriately · **E**stimated · **E**mergent · **P**rioritized — a good *product backlog* |
| **INVEST** | **I**ndependent · **N**egotiable · **V**aluable · **E**stimable · **S**mall · **T**estable — a good *user story* |
| **3 Cs** | **C**ard · **C**onversation · **C**onfirmation — the parts of a user story |
| **ECP / BVA** | Equivalence Class Partitioning / Boundary Value Analysis |
| **V(G)** | Cyclomatic complexity = E − N + 2 = P + 1 |
| **MVC** | Model–View–Controller |

## E. Numbers worth memorising

| Value | Context |
|---|---|
| **2–4 weeks** | Sprint length |
| **5–9** (no more than 7) | Development Team size |
| **15 minutes** | Daily Scrum time-box |
| **1 hr × weeks in sprint** | Sprint Review time-box |
| **45 mins × weeks in sprint** | Sprint Retrospective time-box |
| **1–16 hours** | Task estimate range; longer tasks are broken down |
| **up to 10%** | Development Team time per sprint spent on backlog refinement |
| **every 2 weeks** | XP increment delivery to customers |
| **IEEE 830-1998** | Recommended Practice for Software Requirements Specifications |
| **UML 2.5** (Aug 2015) | Current UML version; v1.1 adopted by OMG 1997 |
| **~10** | Cyclomatic complexity threshold above which a module warrants refactoring |

---

## Gaps in this folder — what to obtain

| Missing item | Needed for | Where to get it |
|---|---|---|
| **Grain Elevator System problem statement** | Tutorials 2, 3, 6, 7, 8 | NTULearn (released week 1) |
| **Lecture 7** (numbering gap between decks 6 and 8) | — | NTULearn |
| **Lectures 10–11** (gap between deck 9 and Lecture 12) | — | NTULearn |
| **Design Patterns lecture(s)** | Tutorials 6 Q2, 7 | NTULearn; meanwhile [BD] Ch. 8 |
| **Testing lecture(s)** | Tutorials 8, 9 | NTULearn; meanwhile [S] Ch. 8, [BD] Ch. 11, Copeland |
| **Sequence Diagrams** — referenced in Ch. 6 and 11 but not developed in any deck here | SRS §2, analysis model | [F] Ch. 4; [BD] §2.4.3 |
| **Use Case Description Template**, **SRS Template** | Lab project | NTULearn course website |

---

*Compiled 5 October 2026 from the lecture decks and tutorial sheet in this folder, cross-referenced against Sommerville 10e, Bruegge & Dutoit 3e, and Fowler's UML Distilled 3e.*
