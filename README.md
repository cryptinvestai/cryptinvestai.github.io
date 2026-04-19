# Cryptinvest AI LLC — Website Deployment Guide

This folder contains the official website for **Cryptinvest AI LLC**.

---

## Files

| File | Purpose |
|------|---------|
| `index.html` | Main website (single page) |
| `logo.png` | Company logo — **add this manually** |
| `CNAME` | Custom domain config (update with your real domain) |
| `README.md` | This file |

---

## Step 1 — Add Your Logo

Before deploying, add your logo file:
- Filename must be exactly: `logo.png`
- Place it in this `website/` folder
- Recommended size: 512×512px or larger, square, transparent background
- The HTML already references it as `<img src="logo.png">`
- If no logo.png is present, the site shows a 🤖 placeholder automatically

---

## Step 2 — Create the GitHub Pages Repository

1. Go to [github.com](https://github.com) and sign in
2. Click the **+** icon → **New repository**
3. Set the repository name to exactly: **`cryptinvestai.github.io`**
   - This name is required for GitHub Pages user sites
4. Set visibility to **Public**
5. Do **not** initialize with README (you'll upload files manually)
6. Click **Create repository**

---

## Step 3 — Upload Files to GitHub

### Option A — GitHub Web UI (easiest)

1. On the new empty repo page, click **"uploading an existing file"**
2. Drag and drop ALL files from this `website/` folder:
   - `index.html`
   - `logo.png`
   - `CNAME`
3. Scroll down, add commit message: `Initial website deployment`
4. Click **Commit changes**

### Option B — Git Command Line

```bash
cd ~/cryptinvest/cryptinvest/website

git init
git remote add origin https://github.com/cryptinvestai/cryptinvestai.github.io.git
git add .
git commit -m "Initial website deployment"
git branch -M main
git push -u origin main
```

---

## Step 4 — Enable GitHub Pages

1. Go to your repo: `github.com/cryptinvestai/cryptinvestai.github.io`
2. Click **Settings** tab
3. Click **Pages** in the left sidebar
4. Under **Source**, select:
   - Branch: `main`
   - Folder: `/ (root)`
5. Click **Save**

GitHub will show: *"Your site is published at..."*

---

## Step 5 — Your Live URL

After a few minutes (usually under 2 minutes), your site will be live at:

```
https://cryptinvestai.github.io
```

Test it in your browser. If it shows a 404, wait 2–3 minutes and refresh.

---

## Step 6 — Upload logo.png Later

If you didn't have the logo ready at deployment time:

1. Go to your repo on GitHub
2. Click **Add file** → **Upload files**
3. Upload `logo.png`
4. Commit — the site updates automatically within ~1 minute

---

## Step 7 — Connect a Custom Domain (When Ready)

When you purchase a domain (e.g., `cryptinvestai.com`):

### In GitHub:
1. Go to repo **Settings** → **Pages**
2. Under **Custom domain**, enter: `cryptinvestai.com`
3. Click **Save** — this creates a `CNAME` file automatically
   (the `CNAME` file in this folder is pre-configured for `cryptinvestai.com`)

### At Your Domain Registrar (GoDaddy, Namecheap, etc.):
Add these DNS records:

**For apex domain (`cryptinvestai.com`):**
```
Type: A    Name: @    Value: 185.199.108.153
Type: A    Name: @    Value: 185.199.109.153
Type: A    Name: @    Value: 185.199.110.153
Type: A    Name: @    Value: 185.199.111.153
```

**For www subdomain:**
```
Type: CNAME    Name: www    Value: cryptinvestai.github.io
```

DNS changes can take 10 minutes to 48 hours to propagate.

### Enable HTTPS:
Once the domain is verified in GitHub Pages settings, check:
☐ **Enforce HTTPS** — GitHub provides free SSL via Let's Encrypt

---

## Final URL (after custom domain)

```
https://cryptinvestai.com
```

---

## Updating the Website

To update any content:
1. Edit `index.html` locally
2. Either upload via GitHub web UI or push via git
3. Changes go live within ~1 minute

---

*Cryptinvest AI LLC · Palm Bay, FL · 2026*
