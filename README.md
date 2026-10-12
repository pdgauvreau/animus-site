# animus-site

Static marketing site for Animus, plus the privacy policy and account deletion pages Google Play requires.
Plain HTML and CSS, no build step, no cookies, no tracking.

| Page | Path |
|---|---|
| Home | `/` |
| Privacy policy | `/privacy/` |
| Delete account | `/delete-account/` |
| Terms of use | `/terms/` |

## Preview locally

```bash
python -m http.server 4321
```

Then open http://localhost:4321.

## Deploy (Vercel, recommended)

1. Push this folder to a public GitHub repo named `animus-site`.
2. In Vercel, choose **Add New > Project**, import the repo, keep Framework Preset **Other**, no build command, and deploy.
3. The site goes live at `https://animus-site.vercel.app`. If Vercel gives you a different domain, replace `https://animus-site.vercel.app` in the `<head>` of every `index.html` (canonical and Open Graph tags).

`vercel.json` turns on trailing slashes, so `/privacy` redirects to `/privacy/`.

## Deploy (GitHub Pages, alternative)

Repo **Settings > Pages**, source **Deploy from a branch**, branch `main`, folder `/ (root)`.
Pages run at `https://<user>.github.io/animus-site/`. Page links are relative so they work there, but update the canonical and Open Graph URLs, and note `404.html` uses root paths, so it only styles correctly on a custom domain.

## Content sources

- Colors, fonts and logo: the Animus Brand folder (brand sheet v1, approved Oct 11, 2026).
- Privacy and terms text: `src/lib/legal.ts` in the app repo, updated for Firebase Cloud Messaging, Android geocoding, microphone use and retention. Keep the two in sync.
- Screenshots: `Animus Brand/Animus Tex/screenshots/android-1080x1920`, resized to 540px WebP in `assets/screens/`.
