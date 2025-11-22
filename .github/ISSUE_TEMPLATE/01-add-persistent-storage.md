---
name: Add persistent storage (SQLite + ORM)
about: Replace in-memory activities with a persistent database
---

**Goal**

Replace in-memory `activities` with a persistent database to survive restarts and support relations (users, clubs, events).

**Tasks**

- Add SQLite and an ORM (SQLModel or SQLAlchemy + Pydantic models).
- Create migrations or a simple init script.
- Migrate `activities` data to a database model with fields: id, name, description, schedule, max_participants.
- Update endpoints to use the database.

**Acceptance criteria**

- Data persists after server restart.
- Existing endpoints `/activities`, signup/unregister work against DB.
