---
name: Extract Pydantic models and utilities
about: Cleanly separate data models and helper utilities for maintainability
---

**Goal**

Cleanly separate data models and helper utilities for maintainability.

**Tasks**

- Move data structures into `models.py` / package with Pydantic models.
- Add utility module for UUIDs, config loading, and common responses.

**Acceptance criteria**

- Clear separation of concerns and reusability across endpoints.
