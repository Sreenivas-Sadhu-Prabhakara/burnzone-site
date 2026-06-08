# What's available

An honest, current snapshot of what BurnZone does today. We'd rather under-promise
here than oversell.

<span class="bz-badge live">Live</span> usable in the product today &nbsp; · &nbsp;
<span class="bz-badge beta">Beta</span> backend/API built; dedicated screen rolling out &nbsp; · &nbsp;
<span class="bz-badge planned">Planned</span> on the roadmap

!!! note "How we read these badges"
    A capability is only **Live** if you can actually *use it in an app today*. Where
    the backend fully supports something but its dedicated **screen** is still being
    built, we mark it **Beta** — not Live — even though the platform can already do it.

## Platform & accounts

| Capability | Status |
|---|---|
| Multi-tenant backend with per-tenant data isolation | <span class="bz-badge live">Live</span> |
| White-label branding (name, colours, logo, display name) | <span class="bz-badge live">Live</span> |
| Email/password auth, JWT with silent refresh, persisted sessions | <span class="bz-badge live">Live</span> |
| Role-based access control (Super Admin / Branch Admin / Trainer / Member) | <span class="bz-badge live">Live</span> |
| Branch scope enforced on the backend | <span class="bz-badge live">Live</span> |
| Audit logging of sensitive actions | <span class="bz-badge live">Live</span> |
| Email notifications on booking confirm / cancel | <span class="bz-badge live">Live</span> |
| Social / OAuth sign-in (Google, Facebook, Instagram) | <span class="bz-badge planned">Planned</span> |
| Custom domains per tenant | <span class="bz-badge beta">Beta</span> |

> Social sign-in has scaffolded backend endpoints but is **not yet integrated with
> live providers**, and there's no in-app button yet — so we call it Planned.

## Member app

| Capability | Status |
|---|---|
| Sign in; stay signed in across reloads & restarts | <span class="bz-badge live">Live</span> |
| Home dashboard (calories vs target, streak, goal progress) | <span class="bz-badge live">Live</span> |
| Workout library | <span class="bz-badge live">Live</span> |
| Curated programs | <span class="bz-badge live">Live</span> |
| Log meals; daily calorie & macro summary | <span class="bz-badge live">Live</span> |
| View your goal & its automatic daily calorie target | <span class="bz-badge live">Live</span> |
| Record weigh-ins; see your latest weight | <span class="bz-badge live">Live</span> |
| Consistency streaks | <span class="bz-badge live">Live</span> |
| Book & cancel trainer sessions | <span class="bz-badge live">Live</span> |
| Create / edit a goal in-app | <span class="bz-badge beta">Beta</span> |
| Personal workout playlists (with review) | <span class="bz-badge beta">Beta</span> |
| AI photo calorie estimation | <span class="bz-badge planned">Planned</span> |
| Wearable / health sync | <span class="bz-badge planned">Planned</span> |
| Push notifications | <span class="bz-badge planned">Planned</span> |

> Goals, playlists and the booking lifecycle are **fully built in the API**; the
> member app reads goals today and the dedicated create/edit and playlist screens are
> the next surfaces to land — hence Beta.

## Operator console

The console gives operators **live operational visibility** across the gym today, plus
branch creation. Deeper write actions are supported by the API and are landing in the
console next.

| Capability | Status |
|---|---|
| Dashboard with live KPIs + recent bookings | <span class="bz-badge live">Live</span> |
| Branches — list & create | <span class="bz-badge live">Live</span> |
| Users — live directory (roles & status) | <span class="bz-badge live">Live</span> |
| Bookings — live overview with colour-coded statuses | <span class="bz-badge live">Live</span> |
| Plans — view tiers, limits & feature flags | <span class="bz-badge live">Live</span> |
| Tenants — view provisioned gyms (Super Admin) | <span class="bz-badge live">Live</span> |
| Booking actions in console (complete / cancel / no-show / override) | <span class="bz-badge beta">Beta</span> |
| User actions in console (invite, change role / status) | <span class="bz-badge beta">Beta</span> |
| Branch ↔ user / trainer assignment in console | <span class="bz-badge beta">Beta</span> |
| Plan & tenant editing in console (provision / suspend) | <span class="bz-badge beta">Beta</span> |
| Trainer availability & sessions screens | <span class="bz-badge beta">Beta</span> |
| Branch calendar view | <span class="bz-badge beta">Beta</span> |
| Plan-limit enforcement at creation time | <span class="bz-badge beta">Beta</span> |
| Compliance / privacy-request console | <span class="bz-badge planned">Planned</span> |
| Billing & payment collection | <span class="bz-badge planned">Planned</span> |

> Every Beta row above is **already supported by the backend API** (e.g. completing a
> booking, inviting a user, provisioning a tenant) — what's rolling out is the console
> screen that drives it.

## Quality & delivery

| | Status |
|---|---|
| Backend test suites (unit · BDD · white-box · black-box · data-driven) | <span class="bz-badge live">Live</span> |
| App widget/smoke tests for member & admin screens | <span class="bz-badge live">Live</span> |
| Production web builds for both apps | <span class="bz-badge live">Live</span> |
| API deployed on managed cloud (Cloud Run + Cloud SQL) | <span class="bz-badge live">Live</span> |
| iOS / Android store packaging | <span class="bz-badge planned">Planned</span> |

---

Questions about a specific capability? The **[For gyms](gyms/index.md)** and
**[For members](members/index.md)** sections go a level deeper.
