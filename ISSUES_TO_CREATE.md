# Issues to Create for Mergington High School Activities API

Below are ready-to-copy GitHub issue drafts. Paste each **Title** into the issue title field and the matching **Body** into the issue description when creating issues in your repository.

---

## 1) Title: Add persistent storage (SQLite + ORM)

**Body**

Goal: Replace in-memory `activities` with a persistent database to survive restarts and support relations (users, clubs, events).

Tasks:
- Add SQLite and an ORM (SQLModel or SQLAlchemy + Pydantic models).
- Create migrations or a simple init script.
- Migrate `activities` data to a database model with fields: id, name, description, schedule, max_participants.
- Update endpoints to use the database.

Acceptance criteria:
- Data persists after server restart.
- Existing endpoints `/activities`, signup/unregister work against DB.

---

## 2) Title: Add user model and authentication (OAuth2 / JWT)

**Body**

Goal: Introduce user accounts and protect actions with authentication.

Tasks:
- Create `User` model (email, name, password hash, role).
- Implement registration (`POST /users`) and token-based login (`POST /token`) using FastAPI OAuth2/JWT.
- Protect signup/unregister and new endpoints with dependency injection for `current_user`.

Acceptance criteria:
- Users can register and receive a token.
- Protected endpoints require valid token.

---

## 3) Title: Add user profile endpoints and UI

**Body**

Goal: Allow users to view and edit their profile information.

Tasks:
- Add endpoints: `GET /users/{id}`, `PUT /users/{id}` (authenticated).
- Add a profile page in the static UI (profile view + edit form).

Acceptance criteria:
- Profile data saved in DB and editable by owner.

---

## 4) Title: Add event creation & RSVP endpoints

**Body**

Goal: Support creating events (club and non-club), listing by date, and RSVPs.

Tasks:
- Add `Event` model with organizer_id, title, description, start_time, end_time, location, capacity.
- Endpoints: `POST /events`, `GET /events`, `GET /events/{id}`, `POST /events/{id}/rsvp`, `DELETE /events/{id}/rsvp`.
- Update UI to list events and allow RSVPing.

Acceptance criteria:
- Events can be created and RSVPed; capacity enforced.

---

## 5) Title: Add club membership roles and approval workflow

**Body**

Goal: Support roles (member, admin) and join-request approval for clubs.

Tasks:
- Add membership model with role and status (pending/approved).
- Endpoints for join requests, approval by admins, and role management.

Acceptance criteria:
- Admins can approve join requests; roles enforced on protected actions.

---

## 6) Title: Extract Pydantic models and utilities

**Body**

Goal: Cleanly separate data models and helper utilities for maintainability.

Tasks:
- Move data structures into `models.py` / package with Pydantic models.
- Add utility module for UUIDs, config loading, and common responses.

Acceptance criteria:
- Clear separation of concerns and reusability across endpoints.

---

## 7) Title: Improve web UI to multi-page SPA or add mobile client plan

**Body**

Goal: Expand the static UI into a multi-screen app or plan a mobile client.

Tasks:
- Convert static frontend into a small SPA (React/Vue) with routes for Activities, Events, Profile, Admin.
- Or produce an API spec (OpenAPI) and a plan for a mobile client.

Acceptance criteria:
- UI supports profile, activity details, and event pages.

---

## 8) Title: Add tests and CI

**Body**

Goal: Add automated tests and CI to maintain reliability.

Tasks:
- Add pytest tests for endpoints and core logic.
- Add GitHub Actions workflow to run tests on push/PR.

Acceptance criteria:
- Tests run in CI and fail on regressions.

---

## Instructions

- To create issues quickly: open the repository Issues tab, click "New issue", paste each title and body from this file.
- If you want me to create the issues directly on GitHub, choose option C and provide a short-lived token (store securely) or let me guide you through creating a token.

