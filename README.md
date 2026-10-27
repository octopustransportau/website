# octopustransportau.website

Static site for the `octopustransportau.website` OAuth application (a private,
single-user Google Drive client built on [rclone](https://rclone.org/)).

It exists to satisfy the Google Cloud OAuth consent screen / verification
requirements: a public home page that explains the app's purpose, plus a privacy
policy and terms page.

## Pages

| File           | Purpose                                                        |
| -------------- | -------------------------------------------------------------- |
| `index.html`   | Home page: what the app is, how OAuth works, which scope it uses |
| `privacy.html` | Privacy policy (incl. Google API Services Limited Use section)   |
| `terms.html`   | Short terms of use                                              |
| `assets/style.css` | Shared styles (no external assets, no JS, no trackers)      |

## Editing

Plain HTML + CSS, no build step. Open `index.html` in a browser, or serve it:

```bash
python3 -m http.server 8080
```

## Publishing

GitHub Pages serves `main` from the repository root:
<https://octopustransportau.github.io/website/>

```bash
git add -A
git commit -m "Rewrite site for OAuth verification"
git push
```

`.nojekyll` is present so that files/directories starting with `_` are served as-is.

## Notes for verification

- App name on the pages must match the OAuth consent screen name exactly.
- Home page must be publicly reachable **without login**.
- Privacy policy URL: <https://octopustransportau.github.io/website/privacy.html>
- Ownership of the domain must be verified in Search Console (HTML file or meta
  tag), then wait 24 hours before resubmitting verification.
