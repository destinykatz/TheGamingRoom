# The Gaming Room — Draw It or Lose It

The Gaming Room project designs a scalable, cloud-ready version of *Draw It or Lose It*, a multiplayer guessing game inspired by *Win, Lose or Draw*. This repository contains the completed Software Design Document (SDD), which outlines the requirements, architecture, and design patterns to support multiple teams, unique players, and synchronized gameplay across platforms.

---

## Client and Software Requirements
The client, **The Gaming Room**, wanted a cloud-based, multi-platform version of their game *Draw It or Lose It*. The system needed to:
- Support multiple concurrent games.
- Enforce unique team and player names.
- Provide synchronized state across all devices.
- Scale to web and mobile clients.
- Separate game logic from presentation.

---

## Reflection

### What I Did Well
I clearly documented the domain model and used appropriate design patterns, such as Singleton for the game registry and Iterator for round progression. Each requirement was mapped directly to design decisions, making the document easy to follow for both the client and developers.

### What Helped During Development
Writing the design document forced me to clarify constraints and assumptions early. Defining API contracts and state diagrams ahead of time streamlined implementation and reduced guesswork.

### What I Would Revise
I would expand the scalability and deployment section with concrete load expectations, autoscaling policies, and failure recovery scenarios. Adding sequence diagrams for lobby creation and join flows would also strengthen the document.

### Interpreting User Needs
User needs focused on fast matchmaking, fair play, and smooth cross-device experiences. I translated these into features like globally unique names, atomic lobby joins, and stateless APIs with WebSocket updates. Meeting user needs is critical to ensure reliability and engagement.

### My Design Approach
I used an iterative approach:
1. Define constraints and success metrics.  
2. Model the domain (Game, Team, Player, Round).  
3. Establish service boundaries and APIs.  
4. Select design patterns intentionally.  
5. Document non-functional requirements and map them to technical tactics.  
6. Maintain a decision log.  

In future projects, I would continue this process but add load testing targets and failure scenarios earlier in the design phase.

---

## Repository Contents
- `SoftwareDesignDocument.pdf` – The completed design document for The Gaming Room.
- `README.md` – This file, with reflection on the project.

---

## About
This project was created as part of my coursework to demonstrate software design, documentation, and communication skills with clients and development teams.
