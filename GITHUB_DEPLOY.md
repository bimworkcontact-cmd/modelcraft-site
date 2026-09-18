# Deploying Modelcraft via GitHub

This folder is already a git repository with the first commit made.
You only need to create the remote and push.

---

## Step 1 — Create the GitHub repository

1. Go to **https://github.com/new**
2. Repository name: `modelcraft-site`
3. Set it to **Public** (required for free GitHub Pages; optional if using Netlify)
4. **Do NOT** tick "Add a README" / "Add .gitignore" — the repo already has files
5. Click **Create repository**

---

## Step 2 — Push this folder

Open a terminal in this folder and run the two commands GitHub shows you:

```bash
git remote add origin https://github.com/YOUR-USERNAME/modelcraft-site.git
git push -u origin main
```

You'll be asked to sign in. GitHub no longer accepts account passwords here —
use a **Personal Access Token** as the password:
**GitHub → Settings → Developer settings → Personal access tokens → Tokens (classic)
→ Generate new token → tick `repo` scope**

(If you'd rather avoid the terminal entirely, see "No-terminal option" at the bottom.)

---

## Step 3 — Connect to Netlify (recommended)

1. Go to **https://app.netlify.com** → **Add new site** → **Import an existing project**
2. Choose **GitHub**, authorise, and pick `modelcraft-site`
3. Leave build settings empty — publish directory is `.` (already set in `netlify.toml`)
4. Click **Deploy**

From now on, every `git push` redeploys the site automatically.

### Then turn on form notifications
**Netlify → Forms → Form notifications → Add notification → Email notification**
→ `bimwork.contact@gmail.com`

Without this, enquiries are still saved in Netlify but you won't be emailed.

---

## Alternative — GitHub Pages instead of Netlify

**Settings → Pages → Source: Deploy from a branch → Branch: `main` / `root` → Save`**

Your site appears at `https://YOUR-USERNAME.github.io/modelcraft-site/` in a few minutes.

### Important limitation
GitHub Pages serves static files only — it **cannot process the enquiry form**.
On GitHub Pages the form will not submit anywhere. If you go this route, tell me and
I'll switch the form to a free third-party handler (Formspree or Getform), or replace
it with a direct mail link.

This is the main reason Netlify is the better fit for this particular site.

---

## Step 4 — Custom domain (optional)

**Netlify:** Domain settings → Add a custom domain → follow the DNS steps. HTTPS is automatic.
**GitHub Pages:** Settings → Pages → Custom domain, then add a CNAME record at your registrar.

Afterwards, add the canonical tag, og:url and a sitemap.xml pointing at the real
domain, then commit and push:
```bash
git add -A && git commit -m "Add real domain" && git push
```

---

## No-terminal option

If you'd rather not use git commands at all:

1. Create the repo as in Step 1, but **do** tick "Add a README"
2. On the repo page click **Add file → Upload files**
3. Drag in `index.html`, `thanks.html`, `robots.txt`, `sitemap.xml`, `netlify.toml`
4. Click **Commit changes**

Then continue from Step 3. You lose the local commit history, but the result is identical.

---

## Making changes later

Edit files, then:
```bash
git add -A
git commit -m "describe what changed"
git push
```
Netlify rebuilds within about a minute.
