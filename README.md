# Tap & Take LLC — website

Single-file marketing site for Tap & Take LLC (cashless vending machines, Long Island NY, serving NY/NJ, CT coming soon).

## What's here
- `index.html` — the entire site. Six pages (Home / Services / About / Locations / FAQ / Contact), inline SVG logo, vanilla JS page router, FAQ accordion, contact form.
- `netlify.toml` — Netlify deploy config (publish from repo root).
- `.gitignore` — standard ignores.

## Local preview
Open `index.html` in any browser. No build, no dependencies.

## Deploy to Netlify
1. Push this folder to your GitHub repo (e.g. `tapandtakellc`).
2. Go to https://netlify.com → sign up / log in with GitHub.
3. Click **Add new site → Import an existing project → GitHub**, authorize, pick the `tapandtakellc` repo.
4. Settings: Branch = `main`, Build command = blank, Publish directory = `.`
5. Click **Deploy site**. ~30s later you'll get a `*.netlify.app` URL.

## Connect tapandtakellc.com (Squarespace-registered)
1. In Netlify: **Site Settings → Domain Management → Add custom domain → `tapandtakellc.com`**.
2. Netlify will show DNS records (usually an `A` record + a `CNAME` for `www`).
3. In Squarespace: **Domains → tapandtakellc.com → DNS Settings → Add Record** for each Netlify record exactly.
4. DNS propagation: 15 min – 48 hr. Netlify shows a green check when ready.
5. In Netlify: **Domain Management → HTTPS → Verify DNS configuration → Provision certificate**.

## To-do before launch
- [ ] Replace `info@tapandtakellc.com` if a different inbox is preferred.
- [ ] Wire the contact form to a real backend (Netlify Forms is one-line — add `netlify` attribute to the `<form>` element).
- [ ] Drop real photos into the Locations page (currently placeholders).
- [ ] Add real headshots to the About page (currently initials).

## Future updates
Edit `index.html` locally, then:
```
git add index.html
git commit -m "Update copy"
git push
```
Netlify auto-deploys within ~30s.
