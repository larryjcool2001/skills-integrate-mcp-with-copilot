---
name: Add event creation & RSVP endpoints
about: Support creating events (club and non-club), listing by date, and RSVPs
---

**Goal**

Support creating events (club and non-club), listing by date, and RSVPs.

**Tasks**

- Add `Event` model with organizer_id, title, description, start_time, end_time, location, capacity.
- Endpoints: `POST /events`, `GET /events`, `GET /events/{id}`, `POST /events/{id}/rsvp`, `DELETE /events/{id}/rsvp`.
- Update UI to list events and allow RSVPing.

**Acceptance criteria**

- Events can be created and RSVPed; capacity enforced.
