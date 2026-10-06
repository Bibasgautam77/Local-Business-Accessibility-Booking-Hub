# Local Business Accessibility & Booking Hub

A WordPress site for a small local business that helps visitors understand services and request appointments without confusion. Built as a custom block theme plus a custom plugin, with accessibility and spam prevention designed in from the start.

**Live demo:** https://YOUR-DEMO-LINK-HERE
**Author:** Bibas Gautam

![Home page](docs/screenshots/home.png)

## The problem
Small business sites often hide prices, hours and contact options, and their booking forms are hard to use with a keyboard, a screen reader or a phone. This project tackles those problems directly.

## Who it is for
| User | Top tasks |
|---|---|
| First-time mobile visitor | Understand a service, tap to call, find hours |
| Keyboard / screen-reader user | Complete the form and fix errors without guessing |
| Busy returning customer | Request a slot quickly, check hours and location |

## Features
- **Services** custom post type with **Service Categories**
- **Accessible booking form** (`[lbah_booking_form]`) with visible labels, an error summary that receives focus, field-level messages, and a focused confirmation
- **Spam prevention:** nonce, hidden honeypot, minimum fill time, per-IP rate limit
- **Privacy:** required consent checkbox linked to the privacy notice; requests stored privately for admins only
- **Mobile-first contact actions:** call and email buttons, opening-hours table, FAQ with details/summary
- **Block theme:** skip link, visible focus, reduced-motion support, responsive layout

## Architecture
Booking logic lives in the plugin (`lbah-booking/`), not the theme, so the design can change without losing functionality.

```
lbah-booking/   plugin: post types, taxonomy, form, validation, spam controls
lbah-theme/     block theme: templates, parts, patterns
docs/           page map, accessibility checklist, test cases, screenshots
```

Page map: Home → Services → Service Detail → Booking, plus FAQ and Contact. See [docs/PAGE-MAP.md](docs/PAGE-MAP.md).

## Testing
- 16 form test cases (invalid input, tampering, spam controls): [docs/TEST-CASES.md](docs/TEST-CASES.md)
- Accessibility checklist (WCAG 2.2 AA target): [docs/ACCESSIBILITY-CHECKLIST.md](docs/ACCESSIBILITY-CHECKLIST.md)
- Lighthouse accessibility scores: Home __ / Services __ / Booking __ / Contact __
- Manual checks: keyboard-only, mobile at 320px and 375px, screen reader

## Screenshots
| Booking form | Error state | Mobile |
|---|---|---|
| ![](docs/screenshots/booking.png) | ![](docs/screenshots/errors.png) | ![](docs/screenshots/mobile.png) |

## Setup
1. Copy `lbah-booking` to `wp-content/plugins/` and `lbah-theme` to `wp-content/themes/`, then activate both.
2. Settings → Permalinks → Save.
3. Add services and categories, then create the pages: Booking (`[lbah_booking_form]`), FAQ and Contact (use the theme patterns), and Privacy Policy.
4. Replace the placeholder phone, email, address and hours.

## Limitations
- The form re-renders on submit rather than redirecting.
- Preferred date only; no live availability or calendar sync.
- The rate limit is IP-based and can be affected by shared networks.
- Email delivery needs an SMTP plugin on most hosts.

## What I learned
(Write 3–4 sentences: what was hardest, such as focus management for errors, and what you would improve next.)

## License
Copyright © 2026 Bibas Gautam. All rights reserved. See [LICENSE](LICENSE).
