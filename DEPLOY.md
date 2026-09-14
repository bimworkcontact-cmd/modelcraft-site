# FrameBIM — Go Live Guide

Everything in this folder is ready to deploy. No build step, no dependencies.

---

## Fastest way live (5 minutes, free)

1. Go to **https://app.netlify.com/drop**
2. Drag this **entire folder** onto the page (the folder, not individual files)
3. You get a live URL instantly, e.g. `random-name-123.netlify.app`
4. Create a free Netlify account when prompted, so the site stays permanent

That's it — the site is live and shareable.

---

## Before you share it with clients

### 1. Replace the domain placeholder
Three files contain `REPLACE-WITH-YOUR-DOMAIN.com`. Update them once you have a domain:
- `index.html` (canonical + og:url tags, near the top)
- `robots.txt`
- `sitemap.xml`

If you're staying on the free `.netlify.app` URL, use that URL instead.

### 2. Turn on form notifications
The enquiry form is already wired for Netlify — submissions are captured automatically.
To get emailed when someone submits:

**Netlify dashboard → Forms → Form notifications → Add notification → Email notification**
→ send to `bimwork.contact@gmail.com`

Without this step, submissions are still saved, but you won't be alerted.

### 3. Test the form
Submit a test enquiry on the live site. You should land on the thank-you page,
and the entry should appear under **Forms** in Netlify.

---

## Custom domain (optional, ~$10–15/year)

1. Buy a domain (Namecheap, Cloudflare, GoDaddy)
2. Netlify → **Domain settings** → **Add a custom domain**
3. Follow the DNS instructions Netlify gives you
4. HTTPS is issued automatically and free — no action needed

---

## What's in this folder

| File | Purpose |
|---|---|
| `index.html` | The website (fully self-contained — all graphics embedded) |
| `thanks.html` | Confirmation page after form submission |
| `robots.txt` | Tells search engines they may index the site |
| `sitemap.xml` | Helps Google find your pages |
| `netlify.toml` | Hosting config + basic security headers |

---

## Getting found on Google

After going live:
1. Go to **https://search.google.com/search-console**
2. Add your site, verify ownership (Netlify DNS makes this easy)
3. Submit `https://yourdomain.com/sitemap.xml`

Indexing typically takes a few days to a couple of weeks.

---

## Worth doing soon

- **Add real project work.** The Projects section currently uses generated technical
  graphics. Real screenshots from projects you've delivered will convert far better
  than illustrations — this is the single highest-impact change you can make.
- **Consider a domain-based email.** `bimwork.contact@gmail.com` works fine, but
  `info@yourdomain.com` reads as more established to US contractors evaluating an
  overseas partner. Most domain registrars offer email forwarding cheaply.
