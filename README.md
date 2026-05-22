# Abhishek Kumar — Portfolio

Deploy-ready for **Cloudflare Pages** and **GitHub Pages**.

---

## ✅ Fix: Cloudflare Pages Deployment

The error you saw:
> `Could not detect a directory containing static files`

Is fixed by the `wrangler.toml` file now included in this repo.

---

## 🚀 Deploy on Cloudflare Pages (correct settings)

1. Go to [Cloudflare Dashboard](https://dash.cloudflare.com) → **Pages**
2. Click **Create a project → Connect to Git**
3. Select your repo: `SagomiX/Abhishek_portfulio`
4. Set build settings:

   | Setting | Value |
   |---|---|
   | Framework preset | **None** |
   | Build command | *(leave blank)* |
   | Build output directory | **/** (just a forward slash, meaning root) |

5. Click **Save and Deploy**

> You do NOT need `npx wrangler deploy` as the deploy command.
> Cloudflare Pages auto-detects static HTML — just leave the build command empty.

---

## 🔁 Alternative: Change deploy command in Cloudflare

If you already have a project set up, go to:
**Settings → Builds & Deployments → Build command**
→ Clear it (leave blank)
→ **Build output directory** → set to `/` or `.`
→ Save → Trigger new deployment

---

## 📁 File Structure

```
Abhishek_portfulio/
├── index.html          ← Main portfolio (dark/night theme)
├── port-day.html       ← Day theme variant
├── port-night.html     ← Night theme variant
├── wrangler.toml       ← Cloudflare Pages config (fixes the error)
├── projects/
│   ├── index.json      ← Add project files here
│   └── (your .html project files)
└── README.md
```

---

## ➕ Adding Projects

1. Drop any `.html` file into the `projects/` folder
2. Register it in `projects/index.json`:

```json
{
  "projects": [
    {
      "file":  "my-project.html",
      "title": "My Project",
      "desc":  "A landing page I built.",
      "type":  "WordPress",
      "emoji": "🌿"
    }
  ]
}
```

3. Push to GitHub → auto-deploys on Cloudflare Pages
