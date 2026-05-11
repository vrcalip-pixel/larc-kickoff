# LARC Kick-Off Event Page

Public-facing landing page for the **LA-25 LARC AI Literacy & Innovation — Regional Kick-Off Convening** (Friday, May 22, 2026).

Single self-contained `index.html` — drop it into a GitHub repo, enable Pages, done.

---

## Deploy to GitHub Pages

1. Create a new public repo named `larc-kickoff` under your `vrcalip-pixel` account
2. Upload `index.html` to the repo root
3. Go to **Settings → Pages**
4. Under **Build and deployment**, set **Source** to **Deploy from a branch**, pick **main** / **/ (root)**, and click **Save**
5. Wait ~60 seconds — your page will be live at:

   **https://vrcalip-pixel.github.io/larc-kickoff/**

To use a custom domain later, add a `CNAME` file and configure DNS — but the default URL is the existing pattern matching the AI Readiness Assessment.

---

## Editing content

Everything is in `index.html`. Search for these comment blocks:

| To change… | Find this comment |
|---|---|
| Page title / social-share preview | `PAGE METADATA` |
| Announcement banner (parking changes, etc.) | `ANNOUNCEMENT BANNER` |
| Event date, time, or location | `EVENT CONFIG` (in the `<script>` near the bottom) — also update the visible "Hero Meta" section |
| Countdown target | Change `startISO` inside `EVENT CONFIG` |
| Agenda items | `AGENDA` section |
| Speaker names / contacts | `CONTACT` section |

### Showing the announcement banner

Find this near the top of `<body>`:

```html
<div class="announcement" hidden>
  <strong>Update</strong> ...
</div>
```

**To show:** delete the word `hidden`. **To hide again:** add `hidden` back.
Edit the text inside the `<div>` to change the message.

### Post-event mode

The countdown will automatically switch to **"We're here. Welcome."** when the start time arrives, and to a **"Thank you for joining us"** message after the end time. No manual action needed — but you can edit those messages in the JavaScript at the bottom of the file (search for `live-headline`).

---

## What's included

- Sticky top navigation with smooth scroll
- Hero with live countdown timer (days / hours / minutes / seconds)
- Auto-flips to "live" / "thank you" states on event day
- Vision quote + program overview + stats strip
- Full three-arc agenda (Morning / Late Morning / Afternoon)
- Four track cards in program colors
- Logistics grid (venue, parking, what to expect, accessibility)
- Collapsible FAQ
- Three-person contact section
- "Add to Calendar" button — generates an `.ics` file
- Responsive mobile layout with hamburger nav
- Open Graph tags for Slack / email / social previews
- Subtle reveal-on-scroll animations (respects `prefers-reduced-motion`)

---

## Tech notes

- Pure HTML / CSS / vanilla JS — no build step, no dependencies
- Google Fonts (Fraunces + Manrope) loaded via CDN
- WCAG-conscious: keyboard-accessible, semantic markup, color-contrast tested
- Works offline once cached
- ~50 KB total (uncached)
