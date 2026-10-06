# Local Business Accessibility & Booking Hub

Copyright © 2026 Bibas Gautam. All rights reserved.

A WordPress project that helps visitors understand services and request appointments without confusion.

- `lbah-booking/` – plugin: Services post type, Service Categories, accessible booking form, spam controls
- `lbah-theme/` – lightweight block theme (skip link, mobile call bar, FAQ and contact patterns)
- `docs/` – page map, accessibility checklist, form test cases

## Setup (staging)
1. Copy both folders into `wp-content/plugins/` and `wp-content/themes/`. Activate the plugin and the theme.
2. Settings → Permalinks → Save (refreshes the `/services/` URLs).
3. Add services under Services, with categories.
4. Create pages: Home (front page), Booking (contains `[lbah_booking_form]`), FAQ (insert pattern "LBAH FAQ"), Contact (insert pattern "LBAH Contact & Hours"), Privacy Policy (Settings → Privacy).
5. Build the menu: Home, Services, Booking, FAQ, Contact. Replace the placeholder phone, email and address.
6. Confirm the server can send email (use an SMTP plugin on staging).

## Limitations
- The form re-renders on submit (no redirect), so a refresh on the confirmation page may prompt resubmission.
- Preferred date only; no live availability or calendar sync.
- The rate limit uses IP address (shared IPs and proxies can affect it).
- Placeholder contact details and hours must be edited.
- Not yet tested on a live site: run `docs/TEST-CASES.md` before launch.
