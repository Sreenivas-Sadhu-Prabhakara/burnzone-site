# White-label & multi-tenant

BurnZone is **multi-tenant**: a single backend and a single app build serve every
gym. Each gym is a **tenant** with isolated data and its own branding.

## One build, many brands

The apps don't hard-code a gym. The API base URL and tenant are supplied at runtime,
and branding is fetched from the backend — so the same binary becomes *your* app:

- **App name & display name** — what members see in the app and on their home screen
- **Brand colours** — a primary/secondary palette themes the whole UI
- **Logo** — shown in-app and on the console

!!! note "How a member's app knows which gym it is"
    The tenant is resolved at runtime (a gym code / subdomain or a build-time
    define). The app then loads that tenant's branding and shows only that gym's
    content. No rebuild per gym.

## Data isolation

Every record — users, branches, workouts, bookings, nutrition logs — is keyed to a
`tenant_id`. Queries are tenant-scoped end-to-end, so one gym can never see
another's data. Roles and branch scope narrow access *further* within a tenant.

```
Tenant: "BurnZone Demo Gym"          Tenant: "Iron Republic"
 ├─ Branches: Downtown, Riverside      ├─ Branches: …
 ├─ Staff: admins, trainers            ├─ Staff: …
 ├─ Members                            ├─ Members
 └─ Workouts, bookings, nutrition      └─ … (fully separate)
```

## Custom domains <span class="bz-badge beta">Beta</span>

Tenants can register a custom domain (e.g. `app.yourgym.com`) so the member web app
and console live under your own URL. Domain records and verification are modelled in
the backend; automated certificate provisioning is being finalised.

## Settings per tenant

Each tenant carries operational defaults that the apps respect:

- Booking duration & cancellation policy window
- Timezone, currency and language
- Notification preferences

---

Next: **[Operator console →](admin-console.md)**
