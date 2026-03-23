# Eigenflow Advisory

A clean, single-page AI consulting interface powered by Google Gemini. AJ, your senior data and business advisor, draws on a behind-the-scenes team of specialists — data engineers, data scientists, ML engineers, statisticians, and more — to deliver one coherent expert perspective on your most complex challenges.

---

## What it does

- **Single advisor interface** — one conversation with AJ, no clutter
- **Full conversation memory** — AJ builds on everything discussed in the session
- **Multi-agent under the hood** — 9 specialist agents (data engineering, data science, BI, analytics, AI/ML, statistics, market research, data governance, cloud/MLOps) inform every response
- **Adaptive responses** — depth and structure calibrate to what you ask
- **Zero backend** — runs entirely in the browser, no server required

---

## Tech stack

| Layer | Technology |
|---|---|
| Frontend | Vanilla HTML, CSS, JavaScript |
| AI Model | Google Gemini 2.5 Flash |
| API | Google Generative Language API (browser-direct) |
| Hosting | GitHub Pages |

---

## Getting started

### 1. Get a free Gemini API key

1. Go to [aistudio.google.com](https://aistudio.google.com)
2. Sign in with a Google account
3. Click **Get API Key** → **Create API key**
4. Copy the key

### 2. Add your key to the file

Open `index.html` and find this line near the bottom:

```javascript
const GEMINI_KEY = 'YOUR_GEMINI_API_KEY_HERE';
```

Replace `YOUR_GEMINI_API_KEY_HERE` with your actual key.

### 3. Run locally

No build step needed. Just open `index.html` in any browser.

---

## Deploying to GitHub Pages

```bash
# Clone your repo (if not already done)
git clone https://github.com/YOUR_USERNAME/YOUR_REPO.git
cd YOUR_REPO

# Copy the file in (rename to index.html)
cp eigenflow.html index.html

# Push to GitHub
git add index.html
git commit -m "Deploy Eigenflow Advisory"
git push origin main
```

Then in your GitHub repo:

1. Go to **Settings → Pages**
2. Under **Source**, select **Deploy from a branch**
3. Select **main** branch and **/ (root)**
4. Click **Save**

Your app will be live at `https://YOUR_USERNAME.github.io/YOUR_REPO` within a minute.

---

## Customisation

All customisation is done inside `index.html` — no separate config files.

### Change the accent colour

Find the `:root` block at the top of the `<style>` section:

```css
:root {
  --accent: #1a3a5c;   /* header, buttons, highlights */
  --gold:   #b8963e;   /* gold rule and accent labels */
}
```

### Change the advisor name or firm

Search and replace directly in the file:
- `AJ` → your advisor name
- `Eigenflow` → your firm name
- Update the monogram `<div class="welcome-monogram">AJ</div>` to match

### Change the AI model

```javascript
const GEMINI_MODEL = 'gemini-2.5-flash'; // change this line
```

Available free-tier models: `gemini-2.5-flash`, `gemini-2.5-flash-lite`, `gemini-2.5-pro`

### Edit the starter cards

Find the `.starter-card` blocks in the HTML and update the `onclick` prompts and labels to match your use cases.

---

## Security note

The Gemini API key is embedded in the HTML file and visible in the browser source. This is fine for personal use or private repos. For a public-facing production deployment, route API calls through a serverless proxy (e.g. Cloudflare Workers) and keep the key server-side.

---

## License

MIT
