# André's Investment Guidance — invest.andaluma.com

Static landing page for André's Investment Guidance, part of the Andaluma family of ventures.
Branding matches [andaluma.com](https://andaluma.com) (DM Sans + Playfair Display, same palette).

## Files
| File | Purpose |
|------|---------|
| `index.html` | Full branded landing page (self-contained, no build step) |
| `logo.svg` | Primary mark — ascending bars + rising trend line |
| `favicon.svg` | Favicon version of the mark |
| `CNAME` | Custom domain for GitHub Pages (`invest.andaluma.com`) |

## Deploy (manual steps — do these outside the code session)
1. Create a new GitHub repo, e.g. `andaluma/invest`.
2. Push this folder's contents to the repo root:
   ```bash
   git init
   git add .
   git commit -m "Foundation page for invest.andaluma.com"
   git branch -M main
   git remote add origin https://github.com/andaluma/invest.git
   git push -u origin main
   ```
3. In the repo: **Settings → Pages** → deploy from `main` / root, then set **Custom domain** to `invest.andaluma.com`.
4. At the DNS registrar, add: `CNAME  invest → andalumaorg.github.io`
   (GitHub confirms the exact target when you set the custom domain).

## Roadmap
- **Now:** foundation page — branding, structure, logo, placeholder sections.
- **Phase 2:** AI advisor backed by Firebase Cloud Functions + Realtime DB
  (`andaluma-planner-default-rtdb`). See the commented block at the bottom of `index.html`.
  Do **not** commit the Firebase `apiKey` in plaintext — inject at build time or restrict by HTTP referrer.
