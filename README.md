# TheGamingRoom
Client and software requirements

The client was The Gaming Room, creators of Draw It or Lose It (a team-based guessing game inspired by Win, Lose or Draw). They asked me to design a cloud-ready, multi-platform version that supports multiple concurrent games, unique teams and players, timed rounds, and synchronized state across clients. Key requirements included: a single authoritative game instance per game code, unique names for teams/players across the system, a clean separation between game logic and presentation, and scalability to web and mobile clients without duplicating business logic.

What I did particularly well

I documented a clear domain model and service boundaries that separated core game rules from UI concerns. I also chose patterns (notably Singleton for the game registry and Iterator for round progression) that simplified concurrency and state management. My architecture section mapped each requirement to specific design decisions, which made the traceability from need → design → implementation easy for both the client and developers.

What in the design-document process helped the coding

Writing out constraints, assumptions, and non-functional requirements up front removed guesswork during implementation. Capturing API contracts, data models, and state diagrams early let me stub endpoints and test logic before the UI was finished. The decision log (with rejected alternatives) saved time later when questions resurfaced, because I could point to the trade-offs we had already evaluated.

What I would revise and how

I would expand the scalability and deployment section with concrete load expectations, autoscaling policies, and failure scenarios (e.g., what happens if the match service restarts mid-round). I’d add sequence diagrams for lobby creation and join flows, plus more explicit rate limits and idempotency rules for APIs to harden the design against double-clicks and flaky networks.

Interpreting and implementing user needs

User needs centered on fast matchmaking, fair play, zero name conflicts, and smooth cross-device play. I translated those into requirements like globally unique team/player names, atomic lobby joins, a single source of truth for game state, and stateless APIs with WebSocket updates for low-latency round timers. Considering user needs is critical because it shapes the architecture toward reliability and clarity—if the experience stutters, allows duplicate names, or desyncs timers, users will churn regardless of feature count.

My approach to designing the software (techniques and future use)

I followed a lightweight, iterative approach:
	•	Clarify constraints and success metrics.
	•	Model the domain (entities like Game, Team, Player, Round; invariants like uniqueness and one-active-round).
	•	Define service boundaries and data contracts before UI.
	•	Choose patterns intentionally (Singleton for registries, Iterator/State for rounds, Repository for persistence).
	•	Document non-functionals (scalability, security, availability) and map them to concrete tactics (stateless services, centralized cache, optimistic concurrency).
	•	Maintain a decision log.

In future, I’d repeat this flow but add earlier load testing targets and chaos scenarios to pressure-test the game loop and real-time updates before feature expansion.

