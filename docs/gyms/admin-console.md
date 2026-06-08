# Operator console

The console is a single web app (Flutter, web-first) where **Super Admins**,
**Branch Admins** and **Trainers** run the gym. Each role sees a different set of
sections — the navigation itself is gated.

## Dashboard <span class="bz-badge live">Live</span>

A KPI overview computed live from the API: **members, trainers, branches, bookings,
plans** — and **tenants** for Super Admins — plus a recent-bookings feed with
colour-coded statuses.

## Branches <span class="bz-badge live">Live</span>

Create and manage branches (name, address). Assign trainers and members to a branch;
every booking and schedule is branch-scoped. Branch Admins are limited to the
branches they manage.

## Bookings <span class="bz-badge live">Live</span>

See the booking pipeline across the gym: who booked which trainer, at which branch,
and when — with statuses (`confirmed`, `completed`, `cancelled`, `no_show`). Admins
can complete, cancel, mark no-shows, or override a booking to a new slot.

## Users <span class="bz-badge live">Live</span>

List everyone in the tenant with their role and status. Invite new staff or members,
change a user's role, and activate/suspend accounts.

## Plans <span class="bz-badge live">Live</span>

Super Admins manage the SaaS tiers (Free / Premium / Pro) and their per-tenant
limits — branches, trainers, members — and feature flags. See
**[Plans & pricing](pricing.md)**.

## Tenants <span class="bz-badge live">Live</span>

Super-Admin-only: provision new gyms, set branding, suspend/activate tenants, and
view per-tenant usage against plan limits.

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
