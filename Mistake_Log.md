# SC2006 Mistake Log

Running log of tutorial/practice questions attempted, question type, and mistakes made.
Add new entries at the bottom.

---

## Entry 1 — 2026-11-18

**Question:** Tutorial 2, Q1(a) — Grain Elevator System (GES): identify the actors and their main use cases, then draw a complete use case diagram (use generalization, include and extend where appropriate).

**Question type:** Requirements elicitation — use case model (actors, use cases, UML use case diagram).

**My attempt:** Actors listed as: Elevator, Silo, elevator sensors for temp/humidity, conductor, transaction log, elevator manager. Diagram drew "System" as an actor too.

### Mistakes
1. **Treated things inside the system as actors.** "System", "Silo" and "Transaction log" are stored data or the system itself, not actors. Actor = something outside the system boundary that interacts with it.
2. **"Elevator" listed twice and as an actor.** The elevator is the whole domain, not an actor. The person operating it is the Elevator Manager.
3. **Conductor (and driver, seller, buyer) listed as an actor.** They never touch the system. They are only data fields the Elevator Manager types in.
4. **No system boundary box.** Use cases must sit inside a box labelled with the system name; actors sit outside.
5. **Drew a flow, not a use case diagram.** Used arrows between actors and use cases like a flowchart (Inform System, Acknowledge Data, Locate Silo, Inform Manager). Those are steps of one use case (belong in the use case description), not separate goals. Actor to use case should be a plain association line.
6. **No include / extend / generalization.** The question asks for them explicitly (e.g. Receive Shipment include Allocate Silo; Override extend Receive Shipment; alert extend Monitor).
7. **Missing use cases:** Ship grain out (departure), request report, request transaction log, monitor silo / send alert.

### Correct approach (summary)
- Actors: Elevator Manager (primary), Sensor (secondary, external). Grain Dryer optional, justified by requirement E.
- Use cases: Enter Arrival Shipment (include Allocate Silo, extended by Manual Allocate/Override), Enter Departure Shipment, Request Report, Request Transaction Log, Update Silo Status (extended by Send Alert when exceeding normal level).

### Rule to remember
Actor test: outside the boundary, directly talks to the system, has its own behaviour. Nouns the system stores or manages (silo, grain, truck, shipment, log) are entities for the class diagram, not actors.

---

## Entry 2 — 2026-11-20

**Question:** AY24/25 S2, Q4(b): Disaster Warning System (DWS) sensor–alert link. Determine the boundaries of the equivalence classes from 4(a). For each boundary, give a value on it, just below it, and just above it.

**Question type:** Black-box testing: equivalence classes and boundary value analysis.

**My attempt:** Wasn't sure equivalence classes have boundaries at all, because I thought ECs could only be discrete. For M's lower boundary I put `-0001`.

### Mistakes
1. **Thought every EC was discrete, with no boundaries.** ECs can be either kind. A **range** EC (N, M) has boundaries. A **discrete-set** EC (sensor name, alert name) has none.
2. **Didn't treat discrete inputs as a point to state.** The answer should say explicitly that the names have no BVs, so the examiner can see the distinction was understood.

### Note on `-0001` (not a mistake)
`-0001` is the right "just below 0" value for M. M is unsigned, so −1 can't be written in a valid format. `-0001` is invalid because of its format, not just its range, and that's fine.

### Correct approach (summary)
- 4 boundaries for 4 marks: N lower (−32769 / −32768 / −32767), N upper (+32766 / +32767 / +32768), M lower (−0001 / 00000 / 00001), M upper (32766 / 32767 / 32768).
- Names: discrete, so no boundaries.
- Optional: digit-count boundary (4 / 5 / 6 digits).

### Rule to remember
Boundaries need **order**. Range EC: on / below / above each end. Discrete EC: 1 valid + 1 invalid, no BVs. If a "just outside" value can't be written in the input format, use the closest format-violating value and say it's invalid because of its format.

---

## Entry 3 — 2026-11-20

**Question:** AY24/25 S2, Q4(c): Design a set of defensive test cases for the DWS link function covering the FOUR inputs, based on the ECs and BVs from Q4(a) and Q4(b). (8 marks)

**Question type:** Black-box testing: defensive test suite design (EC + BV).

**My attempt:** Planned to just create numbers outside the valid ranges of inputs 3 and 4 (N and M) and pass them into the system.

### Mistakes
1. **Only invalid tests.** Defensive testing means **valid + invalid** inputs. Without valid cases (e.g. on-boundary values that should succeed), I never show that a correct link works.
2. **Only N and M.** The question says FOUR inputs. The sensor name and alert name each need an invalid case too (e.g. `"rain"`, `"flood"`).
3. **Didn't hold the other inputs valid.** Each test case should have **only one invalid input**, so a rejection points to exactly one check.
4. **No expected output.** Every test case needs an oracle (Link created / Rejected: reason).
5. **Missed the format classes.** No sign on N (`12345`) and the wrong digit count on M (`1234`) are invalid ECs from 4(a) that have no boundary.

### Correct approach (summary)
- Valid: TC1 (N=−32768, M=00000), TC2 (N=+32767, M=32767), both with the valid names. Valid boundary values combine into a few cases.
- Invalid (one per case, rest default): bad sensor, bad alert, N=−32769, N=+32768, N=`12345`, M=−0001, M=32768, M=`1234`.
- See the Ch 14 table in the cheatsheet.

### Rule to remember
Defensive suite = **valid cases (combine valid BVs)** + **one case per invalid EC/BV (only one invalid input each)**, for **every** input, each with an **expected output**.

---

## Entry 4 — 2026-11-20

**Question:** AY24/25 S2, Q3(c): A third-party sensor sent a string instead of an integer and crashed the DWS. (i) Should your company be blamed? Give one reason for and one against. (ii) Name two other parties to blame, with reasons. (iii) Give three ways your company could have prevented the outage or reduced its blame.

**Question type:** Professional responsibility / ethics + input validation / robustness.

**My attempt:**
- (i) Should: we should have covered these tests, and the system should handle this edge case in black-box testing. Should not: it wasn't specified in the requirements.
- (ii) The other (sensor) company, and the client's own company for not following protocol when connecting to their DWS.
- (iii) Didn't know.

### Mistakes
1. **Didn't recognise what the question tests.** It's about **professional responsibility + input validation / robustness**: untrusted external input must be validated at the system boundary, and a crash on bad input is a fault in our system too.
2. **(i) Answers were right but didn't name the concept.** Say **"robustness / input validation"**, and point out that the system is safety-critical. For "should not", say the sensor **broke the interface contract** (the spec says integer).
3. **(ii) Correct parties, but the "why" needs to be stated clearly.** Each party is worth 2 marks: 1 for the name, 1 for the reason.
4. **(iii) Blank.** The trick is "at any stage", so give **one way per lifecycle stage**: requirements, design/implementation, testing, deployment/maintenance.

### Correct approach (summary)
- (i) Yes: robustness is expected from a safety-critical system, even when the spec doesn't mention it. No: we met the spec, and the sensor broke the interface contract.
- (ii) Sensor manufacturer (broke the spec) · client / DWS manager (no compatibility or integration testing before going live).
- (iii) Robustness NFR + supported interface in the SRS or contract · input validation + fault isolation · defensive / robustness testing with wrong types · compatibility check at registration + documentation.

### Rule to remember
Blame / ethics questions: name the **concept** (robustness, input validation, interface contract, professional responsibility). For "N ways at any stage", walk the **lifecycle**: requirements → design → testing → deployment/maintenance.

---

## Entry 5 — 2026-11-20

**Question:** AY24/25 S2, Q3(a) and Q3(b)(i): (a) Propose an architecture for the DWS and justify it. (b)(i) Name the most applicable design pattern for registering and de-registering sensors at runtime, where sensors send measurements at any time.

**Question type:** System design: architecture vs design pattern.

**My attempt:** Didn't know the difference between an architecture and a design pattern.

### Mistakes
1. **Mixed up the two levels.** **Architecture** (Ch 11) = the **whole system** as components + connectors (layered, client–server, event-based, repository), driven by **NFRs**. **Design pattern** (Ch 12) = a proven fix for **one problem among a few classes** (Observer, Strategy, Factory, Façade), driven by **what varies**.

### Correct approach (summary)
- 3(a): **Event-based (publish–subscribe)**. Sensors push updates at any time, and the DWS reacts. This is easy to extend (modifiability, integration) and handles many sensors (scalability). Optional: a layered manager side.
- 3(b)(i): **Observer**. The DWS is the Subject with register / deregister / notify at runtime. Sensors push `update(value)`. What varies is **who** gets told.

### Rule to remember
Architecture = the shape of the **system** (boxes + lines). Pattern = a fix for a **class-level** problem (UML roles). Event-based architecture and Observer are the same idea at two zoom levels; MVC is an architecture built from patterns.
