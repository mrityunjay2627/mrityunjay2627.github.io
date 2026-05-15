# Priyanshu M Sharma — Portfolio Site

A single-file portfolio website. No build step, no dependencies, no framework. Just `index.html`, your resume PDF, and the brick wall background image.

## What's in the folder

```
portfolio/
├── index.html                       # the entire site (HTML + CSS + JS inline)
└── Priyanshu_Sharma_Resume.pdf      # served by the "Download CV" button
```

Both files must be in the same folder when you deploy.

## Two things you MUST do before going live

### 1. Wire up the contact form (Formspree, free, ~3 minutes)

1. Go to **https://formspree.io** and sign up with `mrityunjay2627@gmail.com`.
2. Verify your email when Formspree sends the confirmation link. **This step is critical** — Formspree will NOT forward form submissions to your inbox until you've clicked the verification link. Until then, submissions only show up in the Formspree dashboard.
3. Click **"+ New form"**, name it something like "Portfolio Contact", and copy the **form ID** (it looks like `xyzabcde` — eight characters).
4. Open `index.html` in any editor. Search for: `YOUR_FORMSPREE_ID`
5. Replace it with your actual form ID. The line will look like:
   ```html
   <form id="contactForm" action="https://formspree.io/f/xyzabcde" method="POST">
   ```
6. Save the file.

That's it. Test it after deploying by sending yourself a message.

### 2. Quick proofread

Open `index.html` in your browser (just double-click it) and scroll through. Check:
- Hero blurb reads how you want
- About section voice feels like you
- All twelve project descriptions match what you'd say in an interview
- Phone number, email, links all correct
- The four certificate cards all point to your LinkedIn certifications page

If anything feels off, send me the list of changes in one batch and I'll iterate.

---

## Deploying to GitHub Pages (free, ~10 minutes)

You'll get a URL like `https://mrityunjay2627.github.io` (or a custom one if you have a domain).

### Step 1 — Create the repo

1. Go to **https://github.com/new**
2. Repository name: **`mrityunjay2627.github.io`** (must match your GitHub username exactly — this gives you a clean URL with no path).
3. Set it to **Public**. Don't initialize with a README — we'll push our own files.
4. Click **Create repository**.

### Step 2 — Push the files

Open a terminal in this `portfolio/` folder and run:

```bash
git init
git add .
git commit -m "Initial portfolio site"
git branch -M main
git remote add origin https://github.com/mrityunjay2627/mrityunjay2627.github.io.git
git push -u origin main
```

If git asks for credentials and your password doesn't work, you need a **Personal Access Token** instead:
- GitHub → Settings → Developer settings → Personal access tokens → Tokens (classic) → Generate new token (classic).
- Give it `repo` scope, generate, and use the token as the password when git asks.

### Step 3 — Turn on Pages

1. In the new repo on GitHub, click **Settings** (top tab).
2. Left sidebar: **Pages**.
3. Under **Build and deployment**, set **Source** to **Deploy from a branch**.
4. Set **Branch** to **main** and folder to **`/ (root)`**. Click **Save**.
5. Wait ~1–2 minutes. Refresh the Pages settings page. You'll see "Your site is live at https://mrityunjay2627.github.io".

### Step 4 — Visit it

Go to **https://mrityunjay2627.github.io** in any browser. Done.

---

## Making changes later

The whole site is one file. To update anything:

1. Edit `index.html` locally.
2. Run:
   ```bash
   git add .
   git commit -m "describe what you changed"
   git push
   ```
3. Wait ~30 seconds. GitHub Pages will redeploy automatically.

## Replacing the resume

Drop a new `Priyanshu_Sharma_Resume.pdf` into the folder (same name), commit, and push. The download button always points to the same filename.

## Custom domain (optional, later)

If you ever buy a domain (e.g. `priyanshusharma.com`):
1. Add a CNAME record at your domain registrar pointing to `mrityunjay2627.github.io`.
2. In the repo: Settings → Pages → Custom domain → enter your domain → save.
3. GitHub will auto-issue an HTTPS cert.

## Tech notes

- **No build step**: edit `index.html`, push, done.
- **Fonts**: Fraunces (display), Inter (body), JetBrains Mono (mono) — loaded from Google Fonts.
- **Color tokens** live in CSS variables at the top of `<style>`. Change `--orange` once and it cascades everywhere.
- **No analytics, no trackers** — add them yourself if you want them.

---

## Troubleshooting

**Site shows 404 after enabling Pages.** Wait a full 2 minutes after enabling Pages. GitHub's first build can take a moment.

**Resume download doesn't work.** Make sure `Priyanshu_Sharma_Resume.pdf` is in the same folder as `index.html` in the repo (case-sensitive).

**Contact form says "could not send".** Either (a) you haven't replaced `YOUR_FORMSPREE_ID`, or (b) you haven't verified your Formspree email yet. Both required.
