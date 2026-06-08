# How it works

BurnZone is **one backend and a shared core**, with two thin apps on top. That's what
lets a member app and an operator console stay consistent, secure and cheap to evolve.

## The architecture

```
        ┌─────────────────────────────┐     ┌─────────────────────────────┐
        │   Member app (Flutter)      │     │   Operator console (Flutter)│
        │   iOS · Android · Web       │     │   Web-first                 │
        │   Train · Eat · Book · Track│     │   Dashboard · Branches ·    │
        │                             │     │   Bookings · Users · Plans  │
        └──────────────┬──────────────┘     └──────────────┬──────────────┘
                       │                                    │
                       └───────────────┬────────────────────┘
                                       │   shared Dart core
                                       │   (API client · models · auth/session
                                       │    · theme · role & scope gating)
                                       ▼
                        ┌───────────────────────────────────┐
                        │   Backend API (Express + TS)      │
                        │   JWT auth · RBAC · multi-tenant  │
                        │   ~200 endpoints                  │
                        └───────────────┬───────────────────┘
                                        ▼
                        ┌───────────────────────────────────┐
                        │   PostgreSQL (tenant-scoped)      │
                        └───────────────────────────────────┘
```

## The pieces

| Component | What it is |
|---|---|
| **Member app** | A Flutter app (one codebase → iOS, Android, web) for members. |
| **Operator console** | A Flutter web app for staff, with role- and branch-gated sections. |
| **Shared core** | A Dart package both apps depend on: typed API client, data models, session/auth, the design system, and the role/scope gating logic — so the apps stay thin and identical in behaviour. |
| **Backend** | An Express + TypeScript API over PostgreSQL: authentication, RBAC, multi-tenancy, bookings, nutrition, workouts, SaaS plans. |

## How a request stays safe

1. A user signs in → the backend issues a short-lived **access token** and a
   **refresh token** (JWT).
2. The app stores them and **silently refreshes** the access token when it expires —
   so sessions don't drop mid-use, and they survive reloads.
3. Every API call carries the token; the backend re-derives the caller's **tenant,
   role and branch scope** and authorises *each* route. The UI gating is a
   convenience, never the only check.

## One experience, every channel

Because the member and admin apps are **Flutter over a shared Dart core**, the same
logic ships to iOS, Android and the web. Branding is applied at runtime per tenant, so
one build becomes any gym's app. Fixing a bug or adding a model in the core improves
both apps at once.

## Built to operate

- **Multi-tenant** data isolation keyed on `tenant_id`
- **RBAC** on every route; **branch scope** narrows it further
- **Audit logging** of sensitive actions
- **CORS allow-listing**, security headers, and JWT refresh
- Deployable to managed cloud (the API runs on Cloud Run + Cloud SQL)

---

See exactly what's shipped on **[What's available →](whats-available.md)**.
