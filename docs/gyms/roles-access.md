# Roles & access

BurnZone segregates features by **identity, role, scope and consent** — so the same
console and the same API serve very different people safely.

## The four roles

| Role | Lives in | Sees / can do |
|---|---|---|
| **Super Admin** | Console | Everything in the tenant: tenants, plans, branches, bookings, users, dashboard |
| **Branch Admin** | Console | Their branch(es): dashboard, branches, bookings, users — not platform-wide settings |
| **Trainer** | Console | Their own availability & sessions |
| **Member** | Member app | Train, eat, book, track — only their own data |

## How access is enforced

Access is checked in **two places**, so the UI and the data agree:

1. **In the apps** — navigation and actions are gated by role. A Branch Admin never
   sees the Tenants or Plans sections; a Trainer only sees their own tools.
2. **On the backend** — every route re-checks the caller's role *and* tenant *and*
   branch scope. Hiding a button is never the only defence.

!!! example "Scope in practice"
    A Branch Admin requesting trainers for a branch they don't manage is rejected by
    the API (`403`), even if they craft the request by hand. Members can list
    *bookable* trainers at **their own** branch, but not the admin-only staff roster.

## Consent-aware features

Sensitive or AI-assisted features can require an explicit **consent** grant in
addition to a plan flag — the access layer combines *flag-enabled* **and**
*consented* before a feature is usable. This keeps privacy-sensitive capabilities
opt-in.

## Why it matters for operators

- **Delegate safely** — give branch managers real power, bounded to their branch.
- **Least privilege** — trainers and members can't reach operator surfaces.
- **One console** — no separate apps to maintain per role; the experience adapts.

---

Next: **[Plans & pricing →](pricing.md)**
