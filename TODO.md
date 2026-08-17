# PrePa vNext Migration TODO

## Phase 1 — Backend setup + DB + Auth + API + env + folder restructuring
- [ ] Add MongoDB + Mongoose dependency wiring (backend package) and env config template
- [ ] Create `backend/` folder structure (config/controllers/middleware/models/routes/services/utils)
- [ ] Implement DB connection module
- [ ] Implement User model (Mongoose) matching required fields
- [ ] Implement auth service with bcrypt + JWT
- [ ] Implement auth routes/controllers: signup/login/logout/me
- [ ] Add JWT middleware for protected routes
- [ ] Implement error handling + request validation utilities
- [ ] Maintain existing `GET/POST /api/classroom` compatibility

## Phase 2 — Connect signup/login to backend + store users in MongoDB
- [ ] Update frontend `public/scripts/core/auth.js` to call backend auth endpoints
- [ ] Preserve current login/signup UI and UX messages/redirects
- [ ] Keep localStorage session behavior for UI, but source user records from MongoDB
- [ ] Backward compatibility: tolerate existing `allUsers`/`userData` until full switch

## Phase 3 — Classroom AI backend hardening + secure Gemini layer
- [ ] Add AI service layer that wraps Gemini calls (reuse existing normalization)
- [ ] Add AI endpoint(s) for classroom history persistence (Mongoose model)
- [ ] Ensure API keys stay server-side only
- [ ] Add loading/error response contracts compatible with existing frontend

## Phase 4 — CBT exam/results migration + history + analytics
- [ ] Extract scoring rules from frontend `results.js` into backend `resultService.js`
- [ ] Implement endpoints for exam session creation + result submission
- [ ] Ensure backend outputs match frontend exactly (byte-for-byte structure)
- [ ] Migrate admin dashboard from localStorage to backend fetch (phased)
- [ ] Add analytics capability (aggregate stats endpoints)

## Completion checklist
- [ ] All current UX flows (CBT, results, classroom, navigation, dashboards) tested
- [ ] No API key leakage in frontend
- [ ] Documentation updated: README + .env.example + docs/API.md + docs/ARCHITECTURE.md

