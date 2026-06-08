# Test it

Thanks for helping test **BurnZone**! It should take about **10–15 minutes**. When
you're done (or as you go), please fill in the **[feedback form](feedback.md)**.

!!! tip "One login for everything"
    Password for **every** demo account is **`Test123!`**. The **Tenant ID is already
    filled in** on the sign-in screen — just choose the email below and press **Sign in**.

## Where to go & what to try

| # | App | Sign in as | What to try |
|---|-----|-----------|-------------|
| 1 | **[Member app](https://burnzone-member-55770.web.app)** | `member@demo.burnzone.in` | **Home** — streak, calories-vs-target, goal progress. **Train** — workouts + programs. **Eat** — log a meal, watch today's total update. **Book** — tap *Book a session* → pick a trainer → pick a day → tap a slot → confirm → find it under *My bookings* → cancel it. **More** — log a weigh-in; sign out & back in. |
| 2 | **[Admin console](https://burnzone-admin-55770.web.app)** | `admin@demo.burnzone.in`<br>(Super Admin) | The full console: **Dashboard** KPIs + recent bookings, **Tenants**, **Plans**, **Branches** (try creating one), **Bookings**, **Users**. Check each section loads. |
| 3 | Admin console | `branch@demo.burnzone.in`<br>(Branch Admin) | **Role gating** — you should see Dashboard / Branches / Bookings / Users, **but not** Tenants or Plans. |
| 4 | Admin console | `trainer@demo.burnzone.in`<br>(Trainer) | You should see only the **trainer** sections — no admin areas. |
| 5 | Member app | `member2@demo.burnzone.in`<br>`member3@demo.burnzone.in` | Extra member accounts — handy for first-run/empty states. |

## Please also check

- **Reload the page** — you should stay signed in (sessions persist).
- Try it on **both phone and desktop** widths.
- Note anything **slow, broken, confusing, or visually off**.

## What's intentionally not finished yet

So you don't report these as bugs — see **[What's available](whats-available.md)**.
In short: social/OAuth sign-in, in-app goal creation, playlists, and several admin
*write* actions (invite, role changes, booking actions, provisioning) are still
rolling out. Reading/booking/logging all work today.

<div style="margin:1.5rem 0">
  <a class="bz-btn bz-btn--primary" href="../feedback/">Give feedback →</a>
</div>
