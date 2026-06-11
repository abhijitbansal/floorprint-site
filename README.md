# Floorprint — marketing & legal site

Static site served via **GitHub Pages from the public
[floorprint-site](https://github.com/abhijitbansal/floorprint-site) repo**
(the app code repo stays private; free-tier Pages needs a public repo).
Source of truth is this `site/` directory — the public repo is a derivative,
force-pushed by the deploy script.

## Files

```
index.html        Marketing landing page
privacy.html      Privacy policy — linked from the App Store listing
support.html      Support / FAQ — linked from the App Store listing
assets/
  style.css       Shared stylesheet (light + dark mode)
  app-icon-*.png  Icon at 512/180/64/32 px (generated from the Xcode asset)
  apple-touch-icon.png
  favicon-32.png
```

Hand-written HTML + one CSS file. No build step, no JavaScript.

## Deploying

```bash
./scripts/deploy-site.sh
```

Pushes the `site/` subtree to `git@github.com:abhijitbansal/floorprint-site.git`
(main branch, force). Override with `SITE_REMOTE=…` or a `.site-remote` file.
Requires the changes to be committed first — the script deploys from HEAD.

Pages setup (one-time, already done if the URL below resolves):
repo Settings → Pages → Source "Deploy from a branch" → `main` / `/ (root)`.

## URLs

- Site: https://abhijitbansal.github.io/floorprint-site/
- Privacy (ASC field): https://abhijitbansal.github.io/floorprint-site/privacy.html
- Support (ASC field): https://abhijitbansal.github.io/floorprint-site/support.html

Content sources: [marketing/privacy-policy.md](../marketing/privacy-policy.md)
and [marketing/support.md](../marketing/support.md) — keep them in sync when
either changes.
