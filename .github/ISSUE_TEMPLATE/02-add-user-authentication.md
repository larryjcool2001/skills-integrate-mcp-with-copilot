---
name: Add user model and authentication (OAuth2 / JWT)
about: Introduce user accounts and protect actions with authentication
---

**Goal**

Introduce user accounts and protect actions with authentication.

**Tasks**

- Create `User` model (email, name, password hash, role).
- Implement registration (`POST /users`) and token-based login (`POST /token`) using FastAPI OAuth2/JWT.
- Protect signup/unregister and new endpoints with dependency injection for `current_user`.

**Acceptance criteria**

- Users can register and receive a token.
- Protected endpoints require valid token.
