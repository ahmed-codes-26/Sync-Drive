# Drive Sync — Website

Static homepage and privacy policy for **Drive Sync**, a locally-run tool that syncs a folder to Google Drive. Built to serve as the public-facing site for the Google OAuth consent screen.

**Live URL:** [https://sync.ahmedcodes.pro](https://sync.ahmedcodes.pro)

---

## Files

| File           | Purpose                          |
| -------------- | -------------------------------- |
| `index.html`   | Homepage                         |
| `privacy.html` | Privacy Policy                   |
| `404.html`     | Custom 404 error page            |
| `styles.css`   | Stylesheet (dark theme)          |
| `favicon.svg`  | SVG favicon (sync arrows icon)   |

## Before deploying

Replace **`YOUR_EMAIL_HERE`** with your actual contact email in:
- `index.html` (footer)
- `privacy.html` (footer + contact section)
- `404.html` (footer)

```bash
# Quick find-and-replace (macOS / Linux)
sed -i 's/YOUR_EMAIL_HERE/you@example.com/g' index.html privacy.html 404.html
```

---

## Deployment

This site is fully static — no build step, no dependencies. Just deploy the root directory.

### Netlify

1. Push this folder to a GitHub repo.
2. Go to [app.netlify.com](https://app.netlify.com), click **Add new site → Import an existing project**.
3. Connect your repo. Set:
   - **Build command:** _(leave blank)_
   - **Publish directory:** `.` (or the subfolder path if nested)
4. Deploy. Add your custom domain `sync.ahmedcodes.pro` under **Domain management**.

> Netlify automatically uses `404.html` for missing pages.

### Vercel

1. Push to GitHub.
2. Import the repo at [vercel.com/new](https://vercel.com/new).
3. Framework preset: **Other**. No build command needed. Output directory: `.`
4. Deploy and add `sync.ahmedcodes.pro` as a custom domain.

> Add a `vercel.json` for the 404 page:
> ```json
> { "routes": [{ "handle": "filesystem" }, { "src": "/(.*)", "dest": "/404.html", "status": 404 }] }
> ```

### Cloudflare Pages

1. Push to GitHub.
2. Go to **Cloudflare Dashboard → Pages → Create a project → Connect to Git**.
3. Build command: _(blank)_. Build output: `.`
4. Deploy. Add `sync.ahmedcodes.pro` as a custom domain in your Pages project settings.

> Cloudflare Pages automatically serves `404.html` for missing routes.

### GitHub Pages

1. Push to a GitHub repo.
2. Go to **Settings → Pages**, set source to the branch and folder containing these files.
3. Add `sync.ahmedcodes.pro` as a custom domain and configure DNS.

> GitHub Pages automatically serves `404.html` for missing routes.

---

## Tech

- Plain HTML + CSS (no frameworks, no JavaScript, no build step)
- [Inter](https://fonts.google.com/specimen/Inter) via Google Fonts
- Fully responsive and accessible
- SEO: `<title>`, meta descriptions, Open Graph, canonical URLs
