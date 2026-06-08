# Plans & pricing

BurnZone ships with tiered SaaS plans. Each plan sets **limits** (branches,
trainers, members) and toggles **features**, enforced per tenant by the backend.

> Prices below are the demo configuration — fully editable by a Super Admin in the
> console. Plans, limits and feature flags are data, not code.

<div class="bz-grid" markdown>

<div class="bz-feature" markdown>
### Free
**$0** / month
A starter tier for a single location.

- 1 branch
- Up to 3 trainers
- Up to 50 members
- Core member app + console
</div>

<div class="bz-feature" markdown>
### Premium
**$29.99** / month · *$299/yr*
For growing multi-branch gyms.

- Up to 3 branches
- Up to 15 trainers
- Up to 500 members
- Programs, bookings, dashboards
</div>

<div class="bz-feature" markdown>
### Pro
**$59.99** / month · *$599/yr*
For chains and franchises.

- Up to 25 branches
- Up to 100 trainers
- Up to 5,000 members
- Everything in Premium + custom domain <span class="bz-badge beta">Beta</span>
</div>

</div>

## How limits work

Each plan **defines** its limits (branches, trainers, members) and **feature flags**,
and the backend **computes usage** against them — so a Super Admin can see, per tenant,
how close it is to each ceiling.

**Hard enforcement at creation** — blocking the 4th branch on a 3-branch plan, for
example — is being rolled out <span class="bz-badge beta">Beta</span>; today the limits
are tracked and visible rather than blocking. The plan model is already shaped for
enforcement, so turning it on is a contained change.

## Billing <span class="bz-badge planned">Planned</span>

Plan definitions, limits and per-tenant assignment are live today. **Payment
collection** (card capture, invoicing, dunning) is on the roadmap — the plan model is
already shaped to plug a payment provider in.

---

Back to **[For gyms overview](index.md)** · or see **[What's available](../whats-available.md)**.
