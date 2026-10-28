# SalahMotion website

The marketing and legal site for **SalahMotion**, served at **https://salahmotion.com**.

Tracking issue: `xienta/SalahMotion#686`.

## What's here

| File | Purpose |
|------|---------|
| `index.html` | Landing page |
| `privacy.html` | Privacy policy (required by the App Store) |
| `support.html` | Support page (the App Store support URL) |
| `assets/styles.css` | Shared styles (Night Sky theme) |
| `CNAME` | Custom domain for GitHub Pages (`salahmotion.com`) |
| `.github/workflows/deploy.yml` | Builds & deploys to GitHub Pages on push to `main` |

## How it's published

Plain static HTML/CSS — no build step. A GitHub Actions workflow uploads the repo
and deploys it to GitHub Pages on every push to `main`.

### One-time setup (in GitHub)

1. **Settings → Pages → Build and deployment → Source** → **GitHub Actions**.
2. **Settings → Pages → Custom domain** → `salahmotion.com` → Save.
3. Once the DNS check is green, tick **Enforce HTTPS**.

### DNS (Route 53, `salahmotion.com` zone)

- Apex `A` → `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
- Apex `AAAA` → `2606:50c0:8000::153`, `2606:50c0:8001::153`, `2606:50c0:8002::153`, `2606:50c0:8003::153`
- `www` `CNAME` → `xienta.github.io`
- The domain is verified at the `xienta` org (a `_github-pages-challenge-xienta` `TXT` record).

## Working locally

Open `index.html` in a browser, or serve the folder:

```sh
python3 -m http.server 8000
```

then visit http://localhost:8000.

## Notes

- Pages from a **private** repo requires a paid org plan; otherwise make the repo public.
- Copy is a first draft generated from the app's behaviour — review before launch.
- Set up the `support@salahmotion.com` mailbox (or forwarding) before submission.
