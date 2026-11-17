# SC2006 — Past-Year Paper → Lecture / Tutorial / Textbook Map

> **Built from** OCR of all 19 files in `PYP_Qns/` (scanned PDFs), cross-checked against every lecture deck and `Tutorial Questions.pdf` in this folder. Garbled OCR lines were re-read from the page images.
>
> **Citation shorthand**
> - **L3 p12** = lecture deck `3 - Requirements Elicitation 2.pdf`, page 12. Decks: L1 Intro · L2/L3/L4 Requirements Elicitation 1/2/3 · L5 Conceptual Models · L6 Dynamic Models · SRS = `Writing SRS.pdf` · L8 Software Processes · L9 Agile (XP p13–28, Scrum p31–63) · L12 System Design · L13 Object Design (Strategy, Observer) · L14 Design Patterns (Factory, Dynamic Loading, Façade) · L15 MVC · L16 Testing Intro · L17 Equivalence Class · L18 Boundary Value · L19 = `Lecture 19-20 Control Flow Testing` · L21 = `Lecture 21` (p2–12 white-box recap, p13–22 maintenance)
> - **T6 Q2** = Tutorial 6, Question 2
> - **[S] 6.3.1** = Sommerville, *Software Engineering* 10th ed. (Global Ed.), section 6.3.1
> - Other books, used only where Sommerville has nothing: **[F]** Fowler *UML Distilled* 3e · **[BD]** Bruegge & Dutoit 3e
>
> **Coverage flag**
> - ✅ The slides/tutorials are enough.
> - ⚠ The slides only touch on it. Read the [S] section given.
> - ❌ Not in the slides. The [S] section is given where Sommerville covers it; otherwise it's marked out of syllabus or "reasoning" (answer from first principles).

---

## 0. Things to know about the files

| File | Issue |
|---|---|
| `AY2021_S1_Questions.pdf` | **Mislabelled.** It is the *2021-22 Sem 1* paper (Nov/Dec 2021) and is identical to `AY2122_S1`. It is a 1-hour, 2-question, closed-book paper. |
| `AY1819_S1_Questions.pdf` | **Wrong course.** It is **CZ3003 Software Systems Analysis & Design** (closed book). Several of its questions are outside SC2006. They are still mapped below and flagged. |
| `AY2122_S2_Solutions.pdf` | **Wrong solution.** It is the Carpark solution, identical to `AY2021_S2_Solutions`. There is no real solution for the AY21/22 S2 "System X diet app" paper. |
| AY22/23 onward | No solution files exist for these papers. |

So there are **17 distinct SC2006 papers plus 1 CZ3003 paper**.

---

## 1. The exam blueprint (stable since AY22/23)

Every 2-hour paper from AY22/23 onward follows the same 4 × 25-mark skeleton:

| Q | Typical parts | Marks | Study from |
|---|---|---|---|
| **Q1** | Use-case diagram with «include»/«extend» · Use-case description *or* activity diagram | 17–19 + 6–8 | L3, L4, L6 · T2 |
| **Q2** | Conceptual class diagram (B/C/E stereotypes) · State-machine *or* activity diagram · Waterfall vs Agile / process-model question · Scrum scenario question | 7–9 · 6–8 · 4–5 · 5–6 | L5, L6, L8, L9 · T3, T4, T5 |
| **Q3** | Architecture + detailed class diagram · Alternative architecture / NFR-driven architecture · "Scenario where >1 design pattern combine" + class diagram · Opinion question (pattern overuse, AI, evaluation) | 8 · 6–8 · 6–8 · 3–5 | L12, L13, L14, L15 · T6, T7 |
| **Q4** | Equivalence classes → boundary values → defensive test cases for **4 inputs** (ASCII string, N-digit int, date range, enum) · Testing / maintenance / AI-for-SE theory | 4+4+5 · 8–12 | L16, L17, L18, L21 · T8 |

### Topic frequency across the 17 SC2006 papers

| Topic | Papers (count) | Trend |
|---|---|---|
| Use-case diagram | 16/17 | Every paper. Worth 17–19 marks since AY22/23. |
| EC + BV + defensive test cases | 16/17 | Every paper. Now always uses the "4-input" template. |
| Architecture proposal (+ class diagram) | 16/17 | Every paper |
| Conceptual class diagram (B/C/E) | 14/17 | Almost every paper |
| Use-case description | 14/17 | Almost every paper |
| Process models (Waterfall/Incremental/Agile/I&C) | 11/17 | Every paper since AY21/22 |
| Scrum (scenario, velocity, backlog) | 9/17 | Every paper since AY21/22 |
| State-machine diagram | 8/17 | Common since AY19/20 |
| Activity diagram (swimlanes) | 7/17 | Every paper since AY22/23 S2 |
| Observer pattern (explicit) | 7/17 | Older papers. Now folded into "combine patterns". |
| Combine >1 design pattern | 7/17 | Every paper since AY22/23 |
| CFG + cyclomatic complexity + basis paths | 7/17 | **Not seen since AY20/21 S2.** Still taught in L19/L21 and T9, so still examinable. |
| Project scheduling (CPM/WBS/estimation) | 6/17 | **Not seen since AY20/21 S2.** Not in the current slides. |
| Dialog map | 5/17 | Last seen AY22/23 S1 |
| Maintenance / refactoring theory | 6/17 | Since AY21/22 |
| LLM / AI-in-SE opinion | 5/17 | Every paper since AY22/23 S2 |
| Sequence / communication diagram | 4/17 | Not since AY21/22 S1. Not in current slides. |

---

## 2. Paper-by-paper breakdown

### AY15/16 Sem 2 — *CloudPSI* (PSI from crowd photos) · open book · solution ✔

| Q | Mk | What's asked | Topic | Slides | Tut | Flag / Textbook |
|---|---|---|---|---|---|---|
| 1(a) | 12 | Actors and UCD with «include»/«extend» | Use-case diagram | L3 p6–22 (include p12–13, extend p14, include vs extend p15) | T2 Q1a | ✅ |
| 1(b) | 13 | UC description: upload photo (pre/post-conditions, flow) | Use-case description | L4 p4–17 (ATM worked example p7–11, template p17) | T2 Q1b | ✅ |
| 2(a) | 8 | Classes + associations, labelled B/C/E | Conceptual model | L5 p8–21 (stereotypes p17, worked example p18–21) | T3 Q1 | ✅ |
| 2(b) | 12 | Dialog map of the mobile app | Dialog map | L6 p6–8 | T3 Q2 | ✅ |
| 2(c) | 5 | Estimate difficulty, complexity and effort of the ML component | Effort estimation | — | — | ❌ [S] 23.5 Estimation techniques, 23.6 COCOMO II; [S] 2.3.1 prototyping to reduce uncertainty |
| 3(a) | 4 | Architecture for web + mobile access, and its benefits | Client-server / layered / MVC | L12 p19–22; L13 p4 (WWW client-server); L15 p16–25 | T6 Q1 | ✅ (extra: [S] 6.3.3) |
| 3(b)(i) | 4 | Pattern for location-based hazard alerts | Observer with interest subscription and selective notification | L13 p24–25, p38–40 | T7 Q1a | ✅ |
| 3(b)(ii) | 8 | Observer class diagram and class roles | Observer | L13 p33, p35, p40 | T7 Q1b | ✅ |
| 3(c) | 9 | Swap ML algorithms without affecting internals | Strategy (+ Factory) | L13 p11–12; L14 p8 | T6 Q2 | ✅ |
| 4(a)(i–iii) | 2/2/8 | ECs, BVs and defensive tests for PSI level × health status | EC / BV testing | L17 p12–27; L18 p11–18 | T8 | ✅ |
| 4(b)(i) | 4 | CFG of `findCity` (for + if) | Control-flow graph | L19 p5–15 (for p10, if p7) | T9a | ✅ |
| 4(b)(ii) | 1 | Must you test `computeDistance` when unit-testing? | Unit-test isolation | L16 p14 | — | ⚠ [S] 8.1.1 (stubs / mock objects) |
| 4(b)(iii) | 8 | Basis paths and test cases | Basis-path testing | L19 p22–35 (loops p35) | T9d | ✅ |

### AY16/17 Sem 1 — *ReportZika* · open book · solution ✔

| Q | Mk | What's asked | Topic | Slides | Tut | Flag / Textbook |
|---|---|---|---|---|---|---|
| 1(a) | 4 | Choose an SDLC model and justify it | Process models | L8 p5–17; L9 p10 | T5 Q1 | ✅ |
| 1(b) | 14 | Actors and UCD | Use-case diagram | L3 p6–22 | T2 Q1a | ✅ |
| 1(c) | 7 | UC description: report a case / upload photos | Use-case description | L4 p4–17 | T2 Q1b | ✅ |
| 2(a) | 10 | Class diagram with multiplicities | Conceptual model | L5 p10–14 (associations p10–11) | T3 Q1 | ✅ |
| 2(b) | 10 | Dialog map | Dialog map | L6 p6–8 | T3 Q2 | ✅ |
| 2(c) | 5 | WBS, two time-estimation methods, shortest completion time | Project scheduling | L1 p10 (mentions WBS only) | — | ❌ [S] 23.2 (project plan), 23.3 Project scheduling (task dependencies, activity charts, critical path), 23.5 Estimation |
| 3(a)(i) | 7 | Architecture for web + mobile; contents of each component | Client-server / 3-layer | L12 p11–22; L13 p4 | T6 Q1 | ✅ (extra: [S] 6.3.1, 6.3.3) |
| 3(a)(ii) | 6 | Benefits of the architecture | Architecture trade-offs | L12 p22–24; L15 p25 | — | ⚠ [S] 6.3 (each pattern's "advantages/disadvantages" table) |
| 3(b)(i–ii) | 4/8 | Pattern for location-based alerts + class diagram | Observer | L13 p24–40 | T7 Q1 | ✅ |
| 4(a)(i–iii) | 2/2/8 | ECs, BVs and defensive tests for Zika cases × pregnancy class | EC / BV | L17; L18 | T8 | ✅ |
| 4(b)(i) | 5 | CFG of `locateTown` (for + break) | CFG | L19 p7, p10 | T9a | ✅ |
| 4(b)(ii) | 8 | Basis paths and test cases | Basis-path testing | L19 p22–35 | T9d | ✅ |

### AY16/17 Sem 2 — *Voicemail system* · open book · solution ✔ (handwritten)

| Q | Mk | What's asked | Topic | Slides | Tut | Flag / Textbook |
|---|---|---|---|---|---|---|
| 1(a) | 12 | UCD with «include»/«extend» | Use-case diagram | L3 | T2 Q1a | ✅ |
| 1(b) | 13 | UC description: leave a message | Use-case description | L4 | T2 Q1b | ✅ |
| 2(a) | 8 | Classes + associations | Conceptual model | L5 | T3 Q1 | ✅ |
| 2(b) | 12 | Dialog map | Dialog map | L6 p6–8 | T3 Q2 | ✅ |
| 2(c) | 5 | WBS; three estimation methods; name the diagram/technique for the shortest and longest time (network diagram, CPM/PERT) | Project scheduling | — | — | ❌ [S] 23.3, 23.5 (PERT is not in [S]; know the name) |
| 3(a)(i–ii) | 6/1 | Layered architecture with B/C/E classes and their dependencies | Layered architecture | L12 p19 (a layer calls only the layer below), p22 | T6 Q1 | ✅ |
| 3(a)(iii) | 4 | Three strengths and one weakness of layering | Layered architecture | L12 p22; L15 p15 (weakness) | — | ⚠ [S] 6.3.1 (layered architecture pattern table) |
| 3(b)(i–ii) | 4/2 | Design problems of three interchangeable access options; pick a pattern | Strategy | L13 p11; L14 p6 | T6 Q2a | ✅ |
| 3(b)(iii) | 8 | Class diagram and roles | Strategy (+ Factory) | L13 p11; L14 p7–8 | T6 Q2b, T7 Q2 | ✅ |
| 4(a)(i–iii) | 3/3/5 | ECs, BVs and tests for hotkey 100–699 | EC / BV | L17 p15–16; L18 p11–15 | T8 | ✅ |
| 4(b)(i–iii) | 6/2/6 | CFG, CC and basis paths for `messageMenu` (if/else-if chain) | Control-flow testing | L19 p7–8, p11, p25–34 | T9 | ✅ |

### AY17/18 Sem 1 — *XYZ Bank home-loan system* · open book · solution ✔

| Q | Mk | What's asked | Topic | Slides | Tut | Flag / Textbook |
|---|---|---|---|---|---|---|
| 1(a) | 10 | UCD | Use-case diagram | L3 | T2 Q1a | ✅ |
| 1(b) | 10 | UC description: compute funds availability | Use-case description | L4 | T2 Q1b | ✅ |
| 1(c) | 5 | Dialog map: adjust bank expenses | Dialog map | L6 p6–8 | T3 Q2 | ✅ |
| 2(a) | 9 | Class diagram | Conceptual model | L5 | T3 Q1 | ✅ |
| 2(b) | 13 | Sequence diagram: compute funds availability | Sequence diagram | L12 p5 (named only) | — | ❌ [S] 5.2.2 Sequence diagrams (+ 7.1.4) |
| 2(c) | 3 | Your role in the course project | Course project / team roles | L1 p12–14; L9 p39–41 | — | personal answer |
| 3(a)(i–ii) | 1/4 | Architecture; three benefits and one drawback | Layered / MVC | L12 p22–24; L15 p25 | T6 Q1 | ⚠ [S] 6.3 |
| 3(a)(iii–iv) | 4/3 | Architecture diagram with B/C/E classes and dependencies; each class's responsibility | Layered + analysis classes | L12 p22; L5 p17 | T6 Q1 | ✅ |
| 3(b)(i–iii) | 3/2/8 | Extensible payment methods: problems, pattern, class diagram | Strategy (+ Factory) | L13 p11–12; L14 p6–9 | T6 Q2, T7 Q2 | ✅ |
| 4(a)(i–iii) | 3/4/5 | ECs, BVs and tests for employment status + income 0–99,999 | EC / BV | L17 p18 (hiring rules), p28; L18 p13–15 | T8 | ✅ |
| 4(b)(i–iii) | 5/2/6 | CFG, CC and basis paths for `displayBorrowerMenu` (while + switch) | Control-flow testing | L19 p9, p11, p25–35 | T9 | ✅ |

### AY18/19 Sem 1 — **CZ3003** paper (*CoffeeBot*) · closed book · *not SC2006*

| Q | Mk | What's asked | Topic | Slides | Tut | Flag / Textbook |
|---|---|---|---|---|---|---|
| 1(a) | 5 | Steps of the requirements development process and how they relate | RE process | L12 p3 (elicitation → analysis → specification → validation); L4 p18–22 | — | ⚠ [S] 4.2 RE processes |
| 1(b) | 6 | Three skills of a requirements analyst | — | — | — | ❌ out of SC2006 syllabus |
| 1(c) | 6 | Three elicitation techniques and when to use each | Elicitation | L2 p7; L4 p21 | — | ⚠ [S] 4.3.1 (interviewing, ethnography), 4.3.2 (stories and scenarios) |
| 1(d) | 8 | Decision table for a credit-card application; completeness and consistency | Decision tables | SRS p13–14 (complete / consistent only) | — | ❌ out of syllabus |
| 2(a) | 5 | Efficiency vs reusability trade-off | NFR conflicts | L12 p9, p16; L13 p7 | — | ⚠ [S] 4.1.2 (NFR conflicts), 6.1 (architecture vs NFRs) |
| 2(b) | 4 | Two "meta-design principles" | — | Nearest: L12 p16–17; L14 p16 | — | ❌ CZ3003-specific |
| 2(c) | 6 | Pipe-and-filter components/connectors, pros and cons | Architectural style | L12 p12, p19–21 | — | ⚠ [S] 6.3.4 |
| 2(d) | 10 | State diagram for an elevator (≤ 10 states) | State machine | L6 p3–9 | T3 Q2 | ✅ |
| 3(a–d) | 6/8/6/5 | Component lists; UML component diagram (composition and decomposition); T/S/I/R categories | Component diagrams | L12 p12–13 (components/connectors only) | — | ❌ CZ3003-specific (some background in [S] Ch 16 CBSE) |
| 4(a) | 4 | Draw message passing between components | Interaction modelling | — | — | ⚠ [S] 5.2.2 |
| 4(b) | 5 | Add a security component so only staff can order | Security architecture | L12 p9 (security as an NFR) | — | ❌ [S] 13 Security engineering |
| 4(c) | 3 | A social group that might oppose CoffeeBot | Ethics / society | — | — | ❌ [S] 1.2 Software engineering ethics |
| 4(d) | 5 | Minimum number of classes, applying a pattern (Composite) | Composite pattern | L13 p10 (catalogue only) | — | ❌ not taught |
| 4(e) | 6+2 | Software product vs software system; why reuse conflicts with certification | SE fundamentals | — | — | ❌ [S] 1.1 (generic vs customised products), 15.1 (reuse issues) |

### AY18/19 Sem 2 — *CSMS (Computer Services Management)* · open book · solution ✔

| Q | Mk | What's asked | Topic | Slides | Tut | Flag / Textbook |
|---|---|---|---|---|---|---|
| 1(a)(i–iii) | 3/3/2 | Network diagram; forward pass → critical path and shortest time; backward pass → slack of Task C | CPM scheduling | — | — | ❌ [S] 23.3 (activity charts, critical path). Forward/backward-pass arithmetic is standard CPM; practise worked examples. |
| 1(b) | 10 | UCD with generalisation, «include», «extend» **and extension points** | Use-case diagram | L3 p11–15; L5 p12–13 (generalisation) | T2 Q1a | ⚠ extension points are not on the slides → [F] Ch 9 |
| 1(c) | 7 | UC description with one alternative flow | Use-case description | L4 p7–11 (alt flows p10) | T2 Q1b | ✅ |
| 2(a) | 12 | Conceptual class diagram using B/C/E icons | Conceptual model | L5 p17, p20–21 | T3 Q1 | ✅ |
| 2(b) | 13 | **Communication diagram** with numbered messages | Communication diagram | — | — | ❌ not in [S] → [F] Ch 12 / [BD] Ch 2 |
| 3(a)(i–ii) | 8/4 | Architecture and diagram; three benefits and one drawback | Layered / MVC | L12 p22–24; L15 p25 | T6 Q1 | ⚠ [S] 6.3 |
| 3(b)(i) | 4 | Push vs pull update in Observer | Observer | L13 p28–37 | — | ✅ |
| 3(b)(ii–iii) | 3/6 | Where Observer applies in CSMS; class diagram and roles | Observer | L13 p24, p33, p35 | T7 Q1 | ✅ |
| 4(a)(i–iii) | 3/4/5 | ECs, BVs and tests: customer no. 10001–89999, priority enum, job time 10–60 | EC / BV | L17; L18 | T8 | ✅ |
| 4(b)(i–iii) | 5/2/6 | CFG, CC and basis paths for `calculateWaitingTime` (while + if + throw; stub return values) | Control-flow testing | L19 p8–9, p25–35 | T9 | ✅ |

### AY19/20 Sem 1 — *Video Rental System (VRS)* · open book · solution ✔

| Q | Mk | What's asked | Topic | Slides | Tut | Flag / Textbook |
|---|---|---|---|---|---|---|
| 1(a) | 10 | UCD | Use-case diagram | L3 | T2 Q1a | ✅ |
| 1(b) | 8 | UC description: rent video | Use-case description | L4 | T2 Q1b | ✅ |
| 1(c) | 7 | Conceptual class diagram with stereotypes | Conceptual model | L5 p17 | T3 Q1 | ✅ |
| 2(a) | 10 | Sequence diagram: rent video | Sequence diagram | — | — | ❌ [S] 5.2.2 |
| 2(b) | 7 | State machine: renting component | State machine | L6 p3–9 | T3 Q2 | ✅ |
| 2(c)(i–ii) | 5/3 | Critical path from activity list; recompute when B = 80 h | CPM scheduling | — | — | ❌ [S] 23.3 |
| 3(a)(i) | 8 | Architecture + detailed class diagram (attributes, methods) | Layered / MVC | L12 p22; L15 p16–24 (Excel MVC p23) | T6 Q1 | ✅ |
| 3(a)(ii) | 6 | Alternative architecture using a different pattern; advantages | MVC vs layered | L15 p15–25 | — | ⚠ [S] 6.3 |
| 3(b)(i) | 4 | The object-design process for VRS | Object design | L13 p5 (interface spec, reuse, restructuring, optimisation) | — | ⚠ [S] 7.1 |
| 3(b)(ii) | 2 | Scenario for Strategy + Factory + Dynamic Loading | Pattern combination | L14 p8–14 | T7 Q2 | ✅ |
| 3(b)(iii) | 5 | Push/pull Observer in Java Swing | Observer / event handling | L13 p34–37, p41–45 | — | ✅ |
| 4(a)(i–iii) | 3/4/5 | ECs, BVs and tests: name (ASCII), type (enum), year 1900–2019 | EC / BV | L17 p17–21; L18 | T8 | ✅ |
| 4(b)(i–iii) | 5/2/6 | CFG, CC and basis paths for `payLateFee` (for + nested if/else) | Control-flow testing | L19 | T9 | ✅ |

### AY20/21 Sem 2 — *Carpark System* · open book · solution ✔

| Q | Mk | What's asked | Topic | Slides | Tut | Flag / Textbook |
|---|---|---|---|---|---|---|
| 1(a) | 10 | UCD | Use-case diagram | L3 | T2 Q1a | ✅ |
| 1(b) | 8 | UC description: leave the carpark | Use-case description | L4 | T2 Q1b | ✅ |
| 1(c) | 7 | Conceptual class diagram with stereotypes | Conceptual model | L5 | T3 Q1 | ✅ |
| 2(a) | 7 | State machine: carpark-leaving component | State machine | L6 p3–9 | T3 Q2 | ✅ |
| 2(b) | 8 | Activity diagram with swimlanes (car, component, gate) | Activity diagram | L6 p10–16 (swimlanes p13–15) | — | ✅ |
| 2(c)(i–iii) | 2/6/2 | Task diagram; forward/backward pass; shortest duration and slack of D | CPM scheduling | — | — | ❌ [S] 23.3 |
| 3(a)(i–ii) | 8/6 | Architecture + class diagram; alternative pattern-based architecture | Layered / MVC | L12; L15 | T6 Q1 | ⚠ [S] 6.3 |
| 3(b)(i) | 4 | Two Observer scenarios besides Swing | Observer | L13 p13–23 (course, baby, stock-market examples) | T7 Q1 | ✅ |
| 3(b)(ii) | 5 | Façade scenario with at least three APIs | Façade | L14 p15–20 | — | ✅ |
| 3(b)(iii) | 2 | Disadvantages of dynamic loading | Dynamic loading | L14 p10–14 (benefits only) | — | ⚠ reasoning: runtime class-not-found errors, no compile-time checks, start-up cost, security of loading arbitrary code |
| 4(a)(i–iii) | 4/4/5 | ECs, BVs and tests: plate (ASCII), type (enum), entry date 2000–2021, 10-digit ID | EC / BV | L17; L18 | T8 | ✅ |
| 4(b)(i–iii) | 5/2/5 | CFG, CC and basis paths for `checkAvailableSlot` (for + nested if) | Control-flow testing | L19 | T9 | ✅ |

### AY21/22 Sem 1 — 1-hour, 2-question paper · closed book · solution ✔ (*same file as `AY2021_S1`*)

| Q | Mk | What's asked | Topic | Slides | Tut | Flag / Textbook |
|---|---|---|---|---|---|---|
| 1(a) | 16 | Is «include» merely for splitting a use case? (think reuse) | «include» semantics | L3 p12–15 (p15: "include = reuse of functionality") | T2 Q1a | ✅ |
| 1(b) | 14 | State machine for a Stack, including error operations | State machine | L6 p3–9 | T3 Q2 | ✅ |
| 1(c) | 17 | Sequence diagram for LIBSYS (Article, Form, Workspace, Printer) | Sequence diagram | — | — | ❌ [S] 5.2.2 (LIBSYS is Sommerville's running example from earlier editions) |
| 1(d) | 3 | Which relationship is the dashed arrow CourseSchedule → Course? | Dependency | L5 p12, p14 | T3 Q1b | ✅ |
| 2(a) | 12 | Fundamental premises of agile methods | Agile | L9 p3–9 (manifesto p8, principles p9) | T5 Q1 | ✅ (extra: [S] 3.1) |
| 2(b) | 14 | Steps of the Scrum sprint cycle | Scrum | L9 p34–36, p46–51 | T5 | ✅ |
| 2(c) | 16 | Product-backlog properties that make Scrum dynamic | Product backlog (DEEP) | L9 p42, p54–56 | T5 Q3 | ✅ |
| 2(d) | 8 | Velocity and cost: 128 points, 8 sprints, 8 people at $4K | Velocity | L9 p53 | **T5 Q6 (same question, different numbers)** | ✅ |

### AY21/22 Sem 2 — *System X: diet-photo app* · open book · **no genuine solution**

| Q | Mk | What's asked | Topic | Slides | Tut | Flag / Textbook |
|---|---|---|---|---|---|---|
| 1(a) | 10 | UCD | Use-case diagram | L3 | T2 Q1a | ✅ |
| 1(b) | 7 | UC description: user login | Use-case description | L4 | T2 Q1b | ✅ |
| 1(c) | 8 | State machine: login | State machine | L6 p3–9 | T3 Q2 | ✅ |
| 2(a) | 8 | Conceptual class diagram (B/C/E) | Conceptual model | L5 | T3 Q1 | ✅ |
| 2(b)(i–ii) | 3/6 | Waterfall or Agile, with justification; pros and cons of each | Process models | L8 p7–10; L9 p4–6, p10 | T5 Q1 | ✅ (extra: [S] 2.1, 3.4.2) |
| 2(c) | 8 | Summarise XP and Scrum, and how they differ | XP vs Scrum | L9 p13–28 (XP), p31–63 (Scrum), p17 ("XP has a technical focus") | T4 Q5, T5 | ✅ |
| 3(a)(i–ii) | 8/6 | Architecture + class diagram; alternative architecture | Layered / MVC | L12; L15 | T6 Q1 | ⚠ [S] 6.3 |
| 3(b)(i) | 6 | Observer scenario + class diagram | Observer | L13 p24–40 | T7 Q1 | ✅ |
| 3(b)(ii) | 5 | Extend that Observer with another pattern | Observer + Strategy / Factory | L15 p22 (Observer + Strategy in MVC); L14 p8 | T7 Q1, T7 Q2 | ✅ |
| 4(a)(i–iii) | 4/4/5 | ECs, BVs and tests: name (ASCII), race (enum), DOB 1900–2010, 2-digit BMI | EC / BV | L17; L18 | T8 | ✅ |
| 4(b)(i) | 4 | Two uses of cyclomatic complexity besides basis-path testing | CC as a metric | L19 p25–26 | — | ⚠ [S] 24.4 (CC as a static product metric), 9.3.1 (maintenance prediction) |
| 4(b)(ii) | 4 | Data-flow vs control-flow testing | White-box families | L16 p13 (named only) | — | ❌ reason from the definition the question gives |
| 4(b)(iii) | 4 | Two kinds of information for estimating maintenance effort | Maintenance prediction | L21 p14–19 | T4 Q2 | ⚠ [S] 9.3.1 (number of change requests, complexity metrics, time to implement a change) |

### AY22/23 Sem 1 — *System X: car-selling system* · open book · no solution

| Q | Mk | What's asked | Topic | Slides | Tut | Flag / Textbook |
|---|---|---|---|---|---|---|
| 1(a) | 17 | UCD | Use-case diagram | L3 | T2 Q1a | ✅ |
| 1(b) | 8 | UC description: hold a car | Use-case description | L4 | T2 Q1b | ✅ |
| 2(a) | 8 | Conceptual class diagram (B/C/E) | Conceptual model | L5 | T3 Q1 | ✅ |
| 2(b) | 8 | Dialog map: car holding | Dialog map | L6 p6–8 | T3 Q2 | ✅ |
| 2(c) | 4 | Waterfall with changing requirements: can customer involvement fix it? | Waterfall limits | L8 p9–10 | — | ⚠ [S] 2.1.1, 2.3 (coping with change), 3.4.1 (customer-involvement problems) |
| 2(d) | 5 | How to estimate progress in Scrum so the team finishes on time | Velocity / burndown | L9 p52–53, p55 | T5 Q2 | ✅ |
| 3(a)(i–ii) | 8/6 | Architecture + class diagram; alternative architecture | Layered / MVC | L12; L15 | T6 Q1 | ⚠ [S] 6.3 |
| 3(b)(i) | 8 | Scenario with more than one pattern + class diagram | Pattern combination | L14 p8–14; L15 p22–24 | T7 Q2 | ✅ |
| 3(b)(ii) | 3 | When can two patterns be combined or merged? Give an example | Pattern combination | L14 p8 (Strategy + Factory), p11–14; L15 p22–24 | T7 Q2 | ✅ |
| 4(a)(i–iii) | 4/4/5 | ECs, BVs and tests: model (ASCII), colour (enum), date 2010–2022, 6-digit price | EC / BV | L17; L18 | T8 | ✅ |
| 4(b)(i) | 4 | Two differences between unit and system testing | Test levels | L16 p14; L17 p4 | — | ⚠ [S] 8.1.1, 8.1.4 |
| 4(b)(ii) | 6 | Why grey-box testing can beat white-box and black-box | Grey-box testing | L16 p13; L17 p7–10; L19 p2–4, p38 | — | ❌ not in slides or [S]. Argue from black-box and white-box pros and cons. |
| 4(b)(iii) | 2 | When should you refactor? | Refactoring | L21 p20–22 ("bad smells" p22); L9 p21–23 | T4 Q5iv | ✅ |

### AY22/23 Sem 2 — *Customer-service Chatbot* · open book · no solution

| Q | Mk | What's asked | Topic | Slides | Tut | Flag / Textbook |
|---|---|---|---|---|---|---|
| 1(a) | 17 | UCD | Use-case diagram | L3 | T2 Q1a | ✅ |
| 1(b) | 8 | UC description: item replacement | Use-case description | L4 | T2 Q1b | ✅ |
| 2(a) | 7 | Conceptual class diagram (B/C/E) | Conceptual model | L5 | T3 Q1 | ✅ |
| 2(b) | 8 | Activity diagram (user, chatbot, web system) | Activity diagram / swimlanes | L6 p10–16 | — | ✅ |
| 2(c) | 4 | Integration-and-configuration: why requirement compromises happen and how to reduce them | Reuse-based process | L8 p14–17 (disadvantages p17) | — | ✅ (extra: [S] 2.1.3) |
| 2(d) | 6 | Scrum Master: a bug found mid-sprint threatens a feature | Scrum events and roles | L9 p40 (SM removes impediments), p43 (unfinished items go back to the product backlog), p46 (sprint goal fixed), p49 (daily scrum) | T5 | ✅ |
| 3(a)(i–ii) | 8/6 | Architecture + class diagram; alternative architecture | Layered / MVC | L12; L15 | T6 Q1 | ⚠ [S] 6.3 |
| 3(b)(i) | 8 | Scenario with more than one pattern + class diagram | Pattern combination | L13; L14; L15 p22–24 | T7 | ✅ |
| 3(b)(ii) | 3 | How to evaluate or compare architectures (hint: structure) | Architecture evaluation | L12 p15 (architecture used to analyse properties), p17; L13 p7 (coupling/cohesion) | — | ⚠ [S] 24.4 (structural / OO metrics: coupling, fan-in/fan-out) |
| 4(a)(i–iii) | 4/4/5 | ECs, BVs and tests: product ID (ASCII), 7-digit quantity, date 2010–2023, shipping (enum) | EC / BV | L17; L18 | T8 | ✅ |
| 4(b)(i) | 3 | ChatGPT reads requirements → how does that help testing? | Requirements-based (black-box) test generation | L17 p6, p9; L16 p15 (test-case ingredients, oracle) | — | ⚠ [S] 8.3.1 requirements-based testing |
| 4(b)(ii) | 3 | ChatGPT summarises code → how does that help testing? | White-box understanding, test oracle | L19 p3 | — | ⚠ reasoning |
| 4(b)(iii) | 6 | Two ways ChatGPT can help maintainability | Maintenance / re-engineering | L21 p14–22 | T4 Q2 | ⚠ [S] 9.3.2 (re-engineering: documentation, restructuring), 9.3.3 |

### AY23/24 Sem 1 — *DevSecOps Platform* · open book · no solution

| Q | Mk | What's asked | Topic | Slides | Tut | Flag / Textbook |
|---|---|---|---|---|---|---|
| 1(a) | 17 | UCD (the "help screen" is a textbook «extend» case) | Use-case diagram | L3 p14–15 | T2 Q1a | ✅ |
| 1(b) | 8 | UC description: security check | Use-case description | L4 | T2 Q1b | ✅ |
| 2(a) | 8 | Conceptual class diagram | Conceptual model | L5 | T3 Q1 | ✅ |
| 2(b) | 8 | Activity diagram with swimlanes: security check | Activity diagram | L6 p13–15 | — | ✅ |
| 2(c) | 4 | "Incremental development can be plan-driven or agile": explain | Incremental model | L8 p5, p11–13 | — | ✅ (the sentence is quoted from [S] 2.1.2) |
| 2(d) | 5 | Why agile may not work with a wide range of skills | Agile limits | L9 p10–11 | T5 Q1 | ⚠ [S] 3.4.1–3.4.2 (practical problems; "how good are the programmers?") |
| 3(a)(i) | 6 | Most important NFRs for the platform | NFRs | L12 p9 (performance, availability, security, scalability, extensibility); L2 p8–10 | T1 Q2 | ✅ |
| 3(a)(ii) | 8 | Architecture that addresses those NFRs + class diagram | NFR-driven architecture | L12 p16, p26, p28; L15 | T6 Q1 | ⚠ [S] 6.1 (architecture and NFRs) |
| 3(b)(i) | 6 | Combined-pattern scenario (e.g. Strategy + Factory for scan engines, Façade) | Pattern combination | L14 p8–20; L13 p11 | T6 Q2, T7 Q2 | ✅ |
| 3(b)(ii) | 5 | Can AI design software architectures? | Opinion | L12 p25 (design is iterative trade-off evaluation), p28 | — | ❌ reasoning (+ [S] 6.1: architecture decisions need judgement) |
| 4(a)(i–iii) | 4/4/5 | ECs, BVs and tests: project ID (ASCII), 6-digit scan limit, date 2000–2023, engine (enum) | EC / BV | L17; L18 | T8 | ✅ |
| 4(b) | 8 | Apply unit, integration, system and acceptance testing to the platform | Test levels | L16 p14; L17 p4, p7 | — | ⚠ [S] 8.1 (unit, component, system), 8.3 release testing, 8.4 user/acceptance testing |
| 4(c) | 4 | Design test projects that exercise SAST/SCA/DAST/IAST | Test design | L17 p12–15 (partition by vulnerability class) | — | ❌ reasoning (seeded-defect projects, one per engine/category) |

### AY23/24 Sem 2 — *CodeAgent (multi-agent code review)* · open book · no solution

| Q | Mk | What's asked | Topic | Slides | Tut | Flag / Textbook |
|---|---|---|---|---|---|---|
| 1(a) | 19 | UCD | Use-case diagram | L3 | T2 Q1a | ✅ |
| 1(b) | 6 | UC description: Reviewer agent | Use-case description | L4 | T2 Q1b | ✅ |
| 2(a) | 9 | Conceptual class diagram | Conceptual model | L5 | T3 Q1 | ✅ |
| 2(b) | 7 | State machine: QA-Checker (retry until appropriate or max rounds) | State machine | L6 p3–9 | T3 Q2 | ✅ |
| 2(c) | 4 | Two ways plan-driven methods can cope with changing requirements | Coping with change | L8 p10–13 | — | ⚠ [S] 2.3 (prototyping, incremental delivery), 4.6 (requirements change management) |
| 2(d) | 5 | Why velocity matters in Scrum | Velocity | L9 p52–53 | T5 Q2 | ✅ (extra: [S] 23.4) |
| 3(a)(i) | 3 | Two agent roles that could be added | Requirements analysis | L2 p5–7 | — | ✅ reasoning |
| 3(a)(ii–iii) | 3/8 | One key NFR; architecture addressing it + class diagram | NFR-driven architecture | L12 p9, p16, p26; L15 | T6 Q1 | ⚠ [S] 6.1 |
| 3(b)(i) | 6 | Combined-pattern scenario + class diagram | Pattern combination | L13; L14; L15 p22–24 | T7 | ✅ |
| 3(b)(ii) | 5 | Can CodeAgent replace development teams? | Opinion | L9 p62 (teamwork); L4 p20–22 (requirements need the client) | — | ❌ reasoning (+ [S] 22.3 teamwork, 1.2 professional responsibility) |
| 4(a)(i–iii) | 4/4/7 | ECs, BVs and tests: description (ASCII), 4-digit minutes, date 2000–2026, app type (enum) | EC / BV | L17; L18 | T8 | ✅ |
| 4(b) | 6 | Design QA-Checker using the course's testing techniques | Applying EC/BV/coverage | L16 p15 (oracle); L17; L18; L19 p16–22 (coverage levels) | T8, T9 | ✅ synthesis |
| 4(c) | 4 | Extend CodeAgent to support maintenance and evolution | Maintenance types | L21 p16–22 | — | ⚠ [S] 9.1 evolution processes, 9.3 |

### AY24/25 Sem 1 — *Web Task Management System* · open book · no solution

| Q | Mk | What's asked | Topic | Slides | Tut | Flag / Textbook |
|---|---|---|---|---|---|---|
| 1(a) | 19 | UCD | Use-case diagram | L3 | T2 Q1a | ✅ |
| 1(b) | 6 | UC description: task assignment | Use-case description | L4 | T2 Q1b | ✅ |
| 2(a) | 9 | Conceptual class diagram | Conceptual model | L5 | T3 Q1 | ✅ |
| 2(b) | 7 | Activity diagram with swimlanes: task created → deleted | Activity diagram | L6 p13–15 | — | ✅ |
| 2(c) | 4 | Waterfall project whose requirements change drastically halfway: what to do | Waterfall + change | L8 p10 | — | ⚠ [S] 2.3, 4.6 |
| 2(d) | 5 | Customer unhappy after Sprint 1: how to improve | Scrum review / retro / PO | L9 p39, p50–51, p56, p60–61 (acceptance criteria) | T5 Q5 | ✅ |
| 3(a)(i) | 8 | Architecture + class diagram | Layered / MVC | L12; L15 | T6 Q1 | ✅ |
| 3(a)(ii) | 8 | One relevant NFR + an alternative architecture for it | NFR-driven architecture | L12 p9, p16, p26 | — | ⚠ [S] 6.1, 17.4 (multi-tier client-server for scalability) |
| 3(b)(i) | 6 | Combined-pattern scenario (notifications via email/in-app) | Observer + Strategy | L13 p38–40; L15 p22 | **T7 Q1 (almost the same scenario)** | ✅ |
| 3(b)(ii) | 3 | Is combining patterns always good? | Pattern trade-offs | L13 p12 (cons: complex if overused); L14 p20 | — | ✅ |
| 4(a)(i–iii) | 4/4/5 | ECs, BVs and tests: description (ASCII), 4-digit resources, deadline 2024–2026, priority (enum) | EC / BV | L17; L18 | T8 | ✅ |
| 4(b) | 4 | Why shift-left testing is good | Test-first / TDD | L9 p24–26 | T4 Q5iii | ⚠ [S] 8.2 TDD, 3.2.3 |
| 4(c) | 8 | Four maintenance challenges and mitigations | Maintenance problems | L21 p14–22 | T4 Q2 | ✅ (extra: [S] 9.2–9.3) |

### AY24/25 Sem 2 — *Disaster Warning System (DWS)* · open book · no solution

| Q | Mk | What's asked | Topic | Slides | Tut | Flag / Textbook |
|---|---|---|---|---|---|---|
| 1(a) | 4 | Four stakeholders and their concerns | Stakeholders | L2 p5–7 | — | ⚠ [S] 4.2–4.3 |
| 1(b) | 6 | Three FRs and three NFRs | FR / NFR | L2 p8–13 | T1 Q1–2 | ✅ |
| 1(c) | 15 | UCD | Use-case diagram | L3 | T2 Q1a | ✅ |
| 2(a) | 6 | State machine: Sensor object | State machine | L6 p3–9 | T3 Q2 | ✅ |
| 2(b) | 7 | Activity diagram: link a sensor to an alert | Activity diagram | L6 p10–16 | — | ✅ |
| 2(c)(i–ii) | 3/3 | Waterfall or Agile for volatile requirements; how to manage changes | Process models | L8 p10; L9 p42, p56 (backlog refinement) | T5 Q1 | ✅ |
| 2(d) | 6 | PO wants a new high-priority feature mid-sprint | Sprint rules | L9 p42–43 (sprint backlog unchanged), p46 (sprint goal fixed; cancellation), p40 | T5 | ✅ |
| 3(a) | 3 | Architecture for DWS, with justification | Event-based / repository | L12 p21 (event systems, implicit invocation), p24 (independent components); L15 | T6 Q1 | ⚠ [S] 21.2 (Observe-and-React pattern for sensor systems), 6.3.2 |
| 3(b)(i–ii) | 3/10 | Pattern for runtime sensor (de)registration and updates + detailed class diagram | Observer | L13 p24–25, p33–40 | T7 Q1 | ✅ |
| 3(c)(i–iii) | 2/4/3 | Third-party sensor sent a string and crashed DWS: blame, other parties, three prevention measures | Professional responsibility, input validation | L17 p25–27 (testing by contract vs defensive testing); SRS p11 (interface requirements) | — | ❌ [S] 1.2 ethics/responsibility, 11.5 programming for reliability ("validate all inputs"), 4.4 interface specification |
| 4(a–c) | 5/4/8 | ECs, BVs and defensive tests: two registered names, signed 5-digit N, unsigned M (16-bit range) | EC / BV | L17 p15–21; L18 p11–15 | T8 | ✅ |
| 4(d) | 4 | Also rejecting N + M overflow: how this complicates ECs and tests | Dependent inputs | L17 p28, p30–32 ("real world is messy") | — | ⚠ reasoning |
| 4(e)(i–ii) | 2/2 | One generic test suite for every deployment: the challenge and a fix (parameterised tests) | Test design | L16 p15; L17 p30–32 | — | ⚠ reasoning |

### AY25/26 Sem 1 — *Smart Home Control System (SHCS) with LLM voice* · open book · no solution

| Q | Mk | What's asked | Topic | Slides | Tut | Flag / Textbook |
|---|---|---|---|---|---|---|
| 1(a) | 18 | UCD | Use-case diagram | L3 | T2 Q1a | ✅ |
| 1(b) | 7 | UC description: guest door access | Use-case description | L4 | T2 Q1b | ✅ |
| 2(a) | 4 | State machine: temporary guest-access controller | State machine | L6 p3–9 | T3 Q2 | ✅ |
| 2(b) | 8 | Activity diagram: guest unlocks door by voice | Activity diagram | L6 p13–15 | — | ✅ |
| 2(c) | 5 | Waterfall vs Agile on flexibility, customer involvement and delivery; one advantage each | Process models | L8 p7–10; L9 p4–6 | — | ✅ |
| 2(d) | 8 | Two advantages and two challenges of sprints, with examples | Sprints | L9 p46, p63 (Scrum benefits), p43 | T5 Q5 | ⚠ [S] 3.3 (benefits), 3.4.1 (practical problems) |
| 3(a)(i) | 8 | Architecture + class diagram | Layered / MVC | L12; L15 | T6 Q1 | ✅ |
| 3(a)(ii) | 8 | One NFR (security, latency, availability) + alternative architecture | NFR-driven architecture | L12 p9, p16 | — | ⚠ [S] 6.1, 17.4 |
| 3(b)(i) | 6 | Combined-pattern scenario (e.g. Strategy for app vs voice + Factory; Observer for logs; Façade over devices) | Pattern combination | L13; L14; L15 p22 | T7 | ✅ |
| 3(b)(ii) | 3 | "Overusing design patterns makes code complex": agree? | Pattern trade-offs | L13 p12; L14 p20 | — | ✅ |
| 4(a)(i–iii) | 4/4/5 | ECs, BVs and tests: name (ASCII), phone 10000000–99999999, expiry 2025–2030, user type (enum) | EC / BV | L17; L18 | T8 | ✅ |
| 4(b) | 4 | Using LLMs for automated testing | AI for testing | L16 p15–17 (test cases, JUnit-style); L17 p6 | — | ❌ reasoning (+ [S] 8.1 automated testing, 3.2.3) |
| 4(c) | 8 | Four challenges of fully automated software development | Opinion | SRS p13–16 (ambiguous requirements); L12 p25; L16 p14; L21 | — | ❌ reasoning |

### AY25/26 Sem 2 — *Restaurant Recommendation System (LLM chat)* · open book · no solution

| Q | Mk | What's asked | Topic | Slides | Tut | Flag / Textbook |
|---|---|---|---|---|---|---|
| 1(a) | 18 | UCD | Use-case diagram | L3 | T2 Q1a | ✅ |
| 1(b) | 7 | Activity diagram: checking the JSON output | Activity diagram | L6 p10–16 | — | ✅ |
| 2(a) | 8 | Conceptual class diagram: recommendation generation | Conceptual model | L5 | T3 Q1 | ✅ |
| 2(b) | 6 | State machine: freeform conversation (10 messages, or "finished") | State machine | L6 p3–9 | T3 Q2 | ✅ |
| 2(c) | 5 | Waterfall vs Agile handling a tag-set change | Process models | L8 p10; L9 p42, p56 | — | ✅ |
| 2(d) | 6 | Sprints keep overrunning: two causes and fixes | Sprint planning / estimation | L9 p44 (split tasks > 16 h), p47–48, p51 (retro), p52–53 (burndown, velocity), p55–56 | T5 Q2 | ✅ |
| 3(a) | 3 | Architecture | Layered / MVC / client-server | L12; L15 | T6 Q1 | ✅ |
| 3(b) | 12 | Detailed class diagram for that architecture | Design class diagram | L12 p22; L15 p23 | — | ✅ |
| 3(c)(i) | 4 | Self-hosting the LLM: two upsides, two downsides | Build vs buy / reuse | L8 p15–17 (reuse pros and cons) | — | ⚠ [S] 15.4 (application-system reuse), 17.5 (SaaS), Ch 18 (services) |
| 3(c)(ii) | 6 | The external LLM injects competitor ads: two remedies | Design for replaceability | L13 p11 (Strategy to swap provider); L14 p15–20 (Façade/wrapper that filters output) | T6 Q2 | ⚠ reasoning |
| 4(a–c) | 4/4/8 | ECs, BVs and defensive tests: 6-digit postcode string; distance 0–100 km | EC / BV | L17 p21 (string-format classes); L18 | T8 | ✅ |
| 4(d)(i) | 3 | Validating the postcode via an online API: how the ECs change | EC refinement | L17 p12–15 | — | ✅ reasoning (valid format splits into exists / doesn't exist) |
| 4(d)(ii) | 4 | Two ways the external API complicates testing | External dependencies | L16 p18 (test independence) | — | ⚠ [S] 8.1.1 (mock objects) |
| 4(e) | 2 | Multi-country postcode formats | Extensibility | L13 p11 (Strategy per country) | T6 Q2 | ✅ |

---

## 3. Where the lectures fall short → what to read in Sommerville

| Gap | Asked in | Read | Note |
|---|---|---|---|
| **Sequence diagrams** | AY17/18, AY19/20, AY21/22 S1, CZ3003 | [S] **5.2.2**, 7.1.4 | Not on current slides. 13–17 marks when asked. |
| **Communication diagrams** | AY18/19 S2 | — ([F] Ch 12) | Not in Sommerville |
| **Project scheduling / CPM / slack / WBS** | AY16/17 S1, AY16/17 S2, AY18/19 S2, AY19/20, AY20/21 S2 | [S] **23.2, 23.3** | Do forward/backward-pass practice. Dropped since 2021. |
| **Effort / time estimation methods** | AY15/16, AY16/17 S1, AY16/17 S2 | [S] **23.5, 23.6** (experience-based, algorithmic, COCOMO II) | |
| Use-case extension points | AY18/19 S2 | — ([F] Ch 9) | Not in Sommerville |
| Architecture pros/cons tables | ~10 papers ("three benefits, one drawback", "alternative architecture") | [S] **6.3** (MVC, 6.3.1 layered, 6.3.2 repository, 6.3.3 client-server, 6.3.4 pipe-and-filter), **6.1**, 17.4 | Slides give styles but few pro/con lists |
| Architecture driven by NFRs | AY23/24 S1 → AY25/26 S1 | [S] **6.1** (performance, security, safety, availability, maintainability → architecture) | Asked every year now |
| Sensor / event-driven architecture | AY24/25 S2 | [S] **21.2** (Observe-and-React, Environmental Control) | |
| Coping with changing requirements in plan-driven processes | AY22/23 S1, AY23/24 S2, AY24/25 S1 | [S] **2.3**, **4.6** | Very common since 2022 |
| Agile limits / scaling | AY23/24 S1, AY25/26 S1 | [S] **3.4.1, 3.4.2** | |
| Test levels (unit / integration / system / acceptance) | AY22/23 S1, AY23/24 S1 | [S] **8.1, 8.3, 8.4** | Slides give a one-line definition each |
| Stubs / mocks for external dependencies | AY15/16, AY25/26 S2 | [S] **8.1.1** | |
| Shift-left / TDD | AY24/25 S1 | [S] **8.2**, 3.2.3 | |
| Maintenance prediction, CC as a metric | AY21/22 S2 | [S] **9.3.1**, **24.4** | |
| Re-engineering / legacy | AY22/23 S2, AY23/24 S2 | [S] **9.2, 9.3.2** | |
| Reuse / build-vs-buy (LLM hosting) | AY25/26 S2 | [S] **15.4**, 17.5 | |
| Ethics, blame, input validation | AY24/25 S2, CZ3003 | [S] **1.2**, **11.5** | |
| Grey-box testing, data-flow testing | AY22/23 S1, AY21/22 S2 | — | In neither source. Answer from the definitions given in the question. |
| LLM / AI-for-SE opinion questions | 5 papers since AY22/23 S2 | — | No source. Anchor each argument to a course concept (requirements ambiguity, test oracle, NFR trade-offs, maintenance, accountability). |
| Decision tables, analyst skills, meta-design principles, component diagrams, Composite | CZ3003 only | — | Out of SC2006 syllabus. Skip. |

---

## 4. Tutorial → exam question cross-reference

| Tutorial | Reappears as |
|---|---|
| **T1** FR/NFR | AY24/25 S2 Q1(b); AY23/24 S1 Q3(a)(i); AY23/24 S2 Q3(a)(ii); every "identify one NFR" part |
| **T2** UCD + UC description | Q1 of every paper |
| **T3 Q1** conceptual class model | Q2(a) of nearly every paper |
| **T3 Q2** projector state machine / dialog map | Every state-machine / dialog-map part (AY15/16 → AY25/26) |
| **T4 Q1–4** software characteristics, maintenance cost | AY24/25 S1 Q4(c); AY21/22 S2 Q4(b)(iii) |
| **T4 Q5** XP (pair programming, TDD, refactoring) | AY21/22 S2 Q2(c); AY22/23 S1 Q4(b)(iii); AY24/25 S1 Q4(b) |
| **T5 Q1** adopting Agile/Scrum | All Waterfall-vs-Agile parts |
| **T5 Q2** estimating velocity | AY22/23 S1 Q2(d); AY23/24 S2 Q2(d); AY25/26 S2 Q2(d) |
| **T5 Q3** good product backlog | AY21/22 S1 Q2(c) (16 marks) |
| **T5 Q6** velocity and cost calculation | **AY21/22 S1 Q2(d): same question with new numbers** |
| **T6 Q1** layered B/C/E architecture | Q3(a) of every paper |
| **T6 Q2** Strategy for interchangeable protocols | AY15/16 Q3(c); AY16/17 S2 Q3(b); AY17/18 Q3(b) |
| **T7 Q1** Observer + interest subscription + Strategy for channels | AY15/16 & AY16/17 S1 Q3(b); AY18/19 S2 Q3(b); **AY24/25 S1 Q3(b)(i)**; AY24/25 S2 Q3(b) |
| **T7 Q2** add Factory to Strategy | AY19/20 Q3(b)(ii); every "combine patterns" part since AY22/23 |
| **T8** EC/BV for silo humidity × temperature | Q4(a) of every paper |
| **T9** CFG / CC / coverage / basis paths for `sum()` | Q4(b) of AY15/16 → AY20/21 S2 |

---

## 5. Study priority (marks per hour)

1. **UCD + UC description**: about 25 marks every paper. Master «include» vs «extend» (L3 p12–15) and the L4 p17 template.
2. **EC → BV → defensive test table**: 13–17 marks every paper. The 4-input template (ASCII string / N-digit int / date range / enum) has repeated in six papers in a row. Know L17 p25–27: test **one** invalid input per test case.
3. **Architecture + class diagram + alternative/NFR**: 14–16 marks every paper. Learn the layered vs MVC vs client-server trade-offs from L12, L15 and [S] 6.3.
4. **Combine patterns**: 6–8 marks. Have one ready-made Observer + Strategy + Factory example (T7) and one Façade example (L14).
5. **Waterfall vs Agile + Scrum scenario**: 9–11 marks. Scenario answers hinge on L9 p43 & p46: the sprint backlog and sprint goal don't change mid-sprint.
6. **State-machine / activity diagram**: 6–8 marks.
7. **Testing / maintenance / AI theory**: 8–12 marks. L16 p13–14, L21 p14–22, plus [S] 8.1–8.4 and 9.3.
8. **CFG / CC / basis paths (T9)** and **CPM ([S] 23.3)**: absent since 2021, but cheap insurance. Do one of each.
