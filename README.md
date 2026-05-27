# Tap and Take LLC — website

Single-page marketing site for Tap and Take LLC (cashless vending machines — Long Island, NY; serving NY & NJ).

**Live:** https://tapandtakellc.com  
**Repo:** https://github.com/edr9090/tapandtakellc  
**Host:** Netlify (project `incredible-zabaione-ea467d`)

## What's here
- `index.html` — entire site (~57 KB). Six in-page "pages" (Home / Services / About / Locations / FAQ / Contact) toggled by a vanilla-JS router. FAQ accordion + mobile hamburger nav.
- `assets/logo.png` — the brand logo (822×827). Referenced from the nav and the hero.
- `netlify.toml` — deploy config + security headers (CSP, HSTS, Permissions-Policy, etc.).
- `robots.txt` — search-engine policy. Allows mainstream crawlers, blocks AI training bots (GPTBot, ClaudeBot, etc.).
- `sitemap.xml` — single-URL sitemap (the site is one HTML file).
- `.gitignore` — standard ignores.

## Local preview
Open `index.html` in any browser. No build, no dependencies.

## How edits go live
```
git add <file>
git commit -m "describe change"
git push
```
Netlify auto-redeploys within ~30s of the push.

## Contact form
The form on the Contact page is a **Netlify Form**:
- Submissions are captured by Netlify (visible at https://app.netlify.com/projects/incredible-zabaione-ea467d/forms)
- To email notifications: add a recipient under **Forms → contact → Form notifications → Add notification → Email** (current target: `info@tapandtakellc.com`).
- Honeypot field `bot-field` filters basic bot spam.

## Custom domain (Squarespace registrar)
DNS is managed at Squarespace; nameservers point at Squarespace. Two records direct `tapandtakellc.com` at Netlify:
- `A` record on `@` → `75.2.60.5`
- `CNAME` record on `www` → `incredible-zabaione-ea467d.netlify.app`

Google Workspace MX records (smtp.google.com) are untouched and continue to handle email.

## To-do (suggested)
- [ ] Verify `info@tapandtakellc.com` is a real inbox / alias in Google Workspace before relying on it for inquiries.
- [ ] Set up the email notification in Netlify Forms (one-time, ~30 sec in the dashboard).
- [ ] Drop real photos into the Locations page (currently placeholders).
- [ ] Add real headshots to the About page (currently initials).
- [ ] Revoke the GitHub Personal Access Token at https://github.com/settings/tokens — the original one was exposed in chat.

## Security headers (applied via `netlify.toml`)
HSTS (1y + preload), CSP, X-Frame-Options DENY, X-Content-Type-Options nosniff, Referrer-Policy strict-origin-when-cross-origin, Permissions-Policy (locks down geo/mic/camera/etc.), and long-cache for `/assets/*`.
