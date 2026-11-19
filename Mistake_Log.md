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
