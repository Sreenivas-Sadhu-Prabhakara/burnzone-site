# Operator console

The console is a single web app (Flutter, web-first) where **Super Admins**,
**Branch Admins** and **Trainers** run the gym. Each role sees a different set of
sections — the navigation itself is gated.

Today the console delivers **live operational visibility** plus branch creation. The
remaining management *actions* are already built in the API and are landing in the
console as dedicated screens — marked <span class="bz-badge beta">Beta</span> below.

## Dashboard <span class="bz-badge live">Live</span>

A KPI overview computed live from the API: **members, trainers, branches, bookings,
plans** — and **tenants** for Super Admins — plus a recent-bookings feed with
colour-coded statuses.

## Branches <span class="bz-badge live">Live</span>

**List and create** branches (name, address); every booking and schedule is
branch-scoped, and Branch Admins are limited to the branches they manage. Assigning
trainers and members to a branch is supported by the API and surfacing in the console
next <span class="bz-badge beta">Beta</span>.

## Bookings <span class="bz-badge live">Live</span>

A **live overview** of the booking pipeline across the gym: who booked which trainer,
at which branch, and when — with colour-coded statuses (`confirmed`, `completed`,
`cancelled`, `no_show`). The actions behind those statuses — complete, cancel,
no-show, override to a new slot — are **live in the API** and being wired into the
console <span class="bz-badge beta">Beta</span>.

## Users <span class="bz-badge live">Live</span>

A **live directory** of everyone in the tenant with their role and status. Inviting
new staff/members and changing roles or account status are API-backed and rolling into
the console <span class="bz-badge beta">Beta</span>.

## Plans <span class="bz-badge live">Live</span>

**View** the SaaS tiers (Free / Premium / Pro), their per-tenant limits — branches,
trainers, members — and feature flags. In-console editing of plans is next
<span class="bz-badge beta">Beta</span>. See **[Plans & pricing](pricing.md)**.

## Tenants <span class="bz-badge live">Live</span>

Super-Admin-only: a **live list** of provisioned gyms with status. Provisioning new
gyms, setting branding, and suspending/activating tenants are API-backed and surfacing
in the console <span class="bz-badge beta">Beta</span>.

## Trainer tools <span class="bz-badge beta">Beta</span>

Trainers get their own sections — **My availability** (set recurring hours and
blocked dates, which generate bookable slots) and **My sessions** (upcoming &
completed). The booking engine behind these is live; the trainer-facing screens are
maturing.

## Compliance <span class="bz-badge planned">Planned</span>

Privacy requests, consent management and audit review surfaces are planned on top of
the audit logging the backend already records.

---

Next: **[Roles & access →](roles-access.md)**
