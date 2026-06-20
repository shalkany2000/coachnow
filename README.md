# CoachNow

Mobile-first marketplace connecting people in Dubai with sports coaches —
swimming, personal training, tennis, padel, football, kids sport, boxing and
yoga. Booking happens through WhatsApp, no accounts needed.

## Before you launch — 2 things to do

1. **Set your real WhatsApp number.**
   Open `src/config.js` and replace the placeholder:
   ```js
   whatsappNumber: '971500000000', // ⚠️ replace with your real number
   ```
   Use the format: country code + number, no `+`, no spaces, no leading 0.
   Example: `971501234567`.

2. **Swap in real coaches (when ready).**
   Mock coaches live in `src/data/coaches.js` — 10 are included so the site
   looks fully populated from day one. Replace them with real coaches as you
   onboard them, following the same field structure.

Everything else — homepage, listing page, profile pages, booking flow, the
"Become a Coach" form — is fully wired and works out of the box.

## Run it locally

```bash
npm install
npm run dev
```

Opens at `http://localhost:5173`.

## Deploy

### Vercel
1. Push this folder to a GitHub repo.
2. Import the repo at vercel.com → New Project.
3. Framework preset: Vite (auto-detected). No config needed — `vercel.json`
   is already set up for client-side routing.

### Netlify
1. Push this folder to a GitHub repo, or drag-and-drop the `dist/` folder
   (after running `npm run build`) into Netlify's deploy UI.
2. Build command: `npm run build`. Publish directory: `dist`.
   The `public/_redirects` file already handles client-side routing.

## What's in here

- **Homepage** — conversion-focused hero, trust stats, sport categories,
  how-it-works, featured coaches, testimonials, coach recruitment banner.
- **Coaches listing** (`/coaches`) — filter by sport, search by name/area,
  sort by rating or price.
- **Coach profile** (`/coaches/:id`) — bio, experience, pricing, highlights,
  and a "Book via WhatsApp" CTA that pre-fills a message with the coach's
  name and sport.
- **Become a Coach** (`/become-a-coach`) — application form that opens
  WhatsApp with the applicant's details pre-filled, then shows a success
  screen.
- A floating WhatsApp button appears site-wide for quick questions.

## Stack

React 18 + Vite + React Router. No backend, no database, no build step
beyond Vite — intentionally simple so it's easy to hand off, extend, or wire
up to a real backend later without untangling unnecessary complexity.
