# Piyush Dubey — Comedian Website

Next.js website with a built-in admin panel. No external database required — all data is
stored in JSON files in the `data/` folder and uploads in `public/uploads/`.

## Run locally (Windows)

```bash
npm install
npm run dev
```

Open http://localhost:3000

## Admin panel

Open http://localhost:3000/admin

- Default password: `piyush123`
- To change it, copy `.env.example` to `.env.local` and set `ADMIN_PASSWORD` (and `ADMIN_SECRET`).

**Session behavior:** the login only lasts while the browser is open (maximum 8 hours).
Closing the browser (or restarting the server without `ADMIN_SECRET` set) always asks
for the password again on the next visit to `/admin`. Click **Logout** in the admin panel
to lock it immediately on a shared computer.

From the admin panel you can:

- **Events** — add, edit, delete upcoming shows with a date picker and time dropdown
  (homepage updates instantly)
- **Gallery** — upload photos/videos (JPG, PNG, WEBP, GIF, MP4, WEBM up to 100 MB) or paste a
  YouTube link to embed it
- **Services** — edit the "What I Do" titles, descriptions and card images
- **Sponsors** — add, edit, delete sponsors with a tier, logo upload, an "about" text and
  page photos. Each sponsor gets its own page (linked from the homepage card) at
  `/sponsors/<id>` showing that content. Use "View page" in the list to open it.
- **Content** — edit every piece of website copy: hero, showreel video, about bio, quote,
  credentials, fun facts, booking section, section headings and footer
- **Inquiries** — see messages sent through the contact form, with quick WhatsApp/Email reply
- **Settings** — WhatsApp number, email, Instagram/YouTube links and SEO title/description
- Everything is stored in `data/*.json`; uploads go to `public/uploads/`

## Contact form

The form on the homepage saves every inquiry to the admin panel, then lets the visitor send
the same message to you via WhatsApp or email with one click (pre-filled).

## Production build

```bash
npm run build
npm start
```

## Notes

- `data/` and `public/uploads/` are created automatically on first use.
- Keep the `data/` folder backed up — it holds your events, gallery index and inquiries.
