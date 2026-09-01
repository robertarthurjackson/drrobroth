# Dr. Rob Roth, ND — Landing Page

**Live site: [drrobroth.com](https://drrobroth.com)**

A static, single-page landing site for Dr. Rob Roth, ND (Naturopathic Doctor)
practicing at Marda Loop Naturopathic & Wellness Clinic (MLNWC) on Mondays and
Tuesdays in-person, and offering virtual consultations on Wednesdays.

```
mlnwc-landing/
├── index.html       # Page markup
├── styles.css       # Styles (calming green/blue/white palette)
├── script.js        # Mobile nav + virtual-booking placeholder handler
├── assets/          # Drop images / favicon here
└── README.md        # You are here
```

The site is **pure static** — no build step, no backend, no dependencies.

## Run locally on http://localhost:8002

Pick whichever you have installed:

### Python 3 (recommended — preinstalled on macOS)
```bash
cd /Users/robroth/projects/mlnwc-landing
python3 -m http.server 8002
```

### Node (if you'd rather)
```bash
cd /Users/robroth/projects/mlnwc-landing
npx serve -l 8002 .
```

Then open <http://localhost:8002>.

> Ports 8000 and 8001 are in use on this machine — this project standardizes on **8002**.

## Things to update before going live

1. **Booking URL** — confirm `https://mlnwc.janeapp.com` is the correct Jane
   App URL for Marda Loop Naturopathic and Wellness Clinic. All four booking
   buttons (two in the hero, two in the booking section) point at this URL,
   plus one reference in the Contact card. Search the file for
   `mlnwc.janeapp.com` to update everything.
2. **Copy review** — confirm bio language, services, and disclaimer.
3. **Favicon / OG image** — drop assets in `assets/` and reference them in
   `<head>` of `index.html` if desired.

## Deploying online (free options)

All three options below host static sites for free and give you HTTPS out of
the box. **Netlify drop** is the fastest if you just want a URL today.

### Option A — Netlify (drag & drop, ~2 minutes)
1. Sign up at <https://app.netlify.com> (free).
2. Go to **Sites → Add new site → Deploy manually**.
3. Drag the entire `mlnwc-landing` folder into the drop zone.
4. You'll get a URL like `https://random-name.netlify.app`. Rename it under
   **Site settings → Change site name**.
5. To use a custom domain (e.g. `drrobroth.com`), go to **Domain management →
   Add custom domain** and follow the DNS instructions.

To update after the first deploy: drag the folder onto the site again, or
connect a Git repo (see below).

### Option B — GitHub Pages
1. Create a new GitHub repository (e.g. `drrobroth-landing`).
2. From the project folder:
   ```bash
   git init
   git add .
   git commit -m "Initial landing page"
   git branch -M main
   git remote add origin https://github.com/<your-user>/drrobroth-landing.git
   git push -u origin main
   ```
3. On GitHub: **Settings → Pages → Source: `Deploy from branch` → `main` / `(root)`**.
4. Your site will publish at `https://<your-user>.github.io/drrobroth-landing/`.
5. Custom domain: add a `CNAME` file containing your domain, then point a
   `CNAME` DNS record at `<your-user>.github.io`.

### Option C — Cloudflare Pages
1. Push the repo to GitHub (steps above).
2. In Cloudflare dashboard → **Workers & Pages → Create application → Pages →
   Connect to Git**.
3. Pick the repo. **Build command**: leave blank. **Output directory**: `/`.
4. Deploy. You'll get a `*.pages.dev` URL and can attach a custom domain
   under **Custom domains**.

### Custom domain notes
- For all three providers, you'll add either an `A`/`AAAA` record (apex/root
  domain) or a `CNAME` (subdomain like `www.`) at your registrar.
- HTTPS certificates are issued automatically once DNS resolves.

## Accessibility & performance notes

- Smooth scroll, mobile nav, and the booking-placeholder alert work without
  any framework.
- Color contrast on all text/background pairs meets WCAG AA.
- `prefers-reduced-motion` disables the hero background animation.
- No tracking scripts, no third-party fonts beyond Google Fonts (which can
  be self-hosted later if desired).

## License / authorship

Content © Dr. Rob Roth. Code released for the project's own use; reuse
elsewhere is fine for personal / educational purposes.
