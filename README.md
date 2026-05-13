# Swiss Fuel Finder — Website Setup Guide

## Folder Structure

Upload these files to your GitHub repository exactly as shown:

```
your-repo/
├── index.html          ← Main landing page
├── legal.html          ← Legal / Privacy / ToS page
├── CNAME               ← Your custom domain
└── assets/
    ├── logo.png        ← Rename SFF_Twint_Logo.png to logo.png
    ├── screenshot1.jpg ← Rename Screenshot_20260513_184332_SFF.jpg
    └── screenshot2.jpg ← Rename Screenshot_20260513_184356_SFF.jpg
```

---

## Step 1 — Update the CNAME file

Open the `CNAME` file and replace `www.yourdomain.com` with your actual domain.
Example: `www.swissfuelfinder.com`

---

## Step 2 — Add your legal document links

Open `legal.html` and replace the two `href="#"` placeholders:

```html
<a href="YOUR_PRIVACY_POLICY_URL" class="legal-card" id="privacy-link">
<a href="YOUR_TERMS_OF_SERVICE_URL" class="legal-card" id="tos-link">
```

---

## Step 3 — Add your App Store links

Open `index.html` and replace the two `href="#"` platform buttons with
your real App Store and Google Play URLs.

---

## Step 4 — Create the GitHub repository

1. Go to github.com and sign in (create a free account if needed)
2. Click the + icon → New repository
3. Name it anything (e.g. `sff-website`)
4. Set it to Public
5. Click Create repository

---

## Step 5 — Upload files

1. In your new repo, click Add file → Upload files
2. Upload ALL files: index.html, legal.html, CNAME, and the entire assets/ folder
3. Click Commit changes

---

## Step 6 — Enable GitHub Pages

1. In your repo, go to Settings → Pages
2. Under Source, select Deploy from a branch
3. Choose branch: main, folder: / (root)
4. Click Save
5. GitHub will show you a URL like https://yourusername.github.io/sff-website

---

## Step 7 — Point your Squarespace domain to GitHub Pages

In Squarespace DNS (Domains → your domain → DNS Settings), add these
four A records pointing to GitHub's servers:

| Type | Host | Value          |
|------|------|----------------|
| A    | @    | 185.199.108.153 |
| A    | @    | 185.199.109.153 |
| A    | @    | 185.199.110.153 |
| A    | @    | 185.199.111.153 |

These are GitHub Pages' IP addresses and bypass the locked www CNAME.
Your apex domain (yourdomain.com) will then redirect to www automatically.

Wait up to 24 hours for DNS to propagate.

---

## Step 8 — Verify in GitHub Pages settings

After DNS propagates, go back to Settings → Pages in your repo.
Enter your custom domain (www.yourdomain.com) and check
"Enforce HTTPS". GitHub will provision a free SSL certificate automatically.
