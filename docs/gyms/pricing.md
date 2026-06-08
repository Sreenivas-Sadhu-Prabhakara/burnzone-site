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

## How limits are enforced

When a tenant approaches a plan limit (e.g. adding the 4th branch on Premium), the
backend checks usage against the plan and returns a clear, actionable response. Usage
is visible to Super Admins per tenant.

## Billing <span class="bz-badge planned">Planned</span>

Plan definitions, limits and per-tenant assignment are live today. **Payment
collection** (card capture, invoicing, dunning) is on the roadmap — the plan model is
already shaped to plug a payment provider in.

---

Back to **[For gyms overview](index.md)** · or see **[What's available](../whats-available.md)**.
