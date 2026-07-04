# legal — Privacy & Support pages

Public static site hosting privacy-policy and support pages for the developer's iOS apps.
No code, no secrets — safe to be public. This exists to satisfy App Store Connect's
required **Privacy Policy URL** (and support URL) fields.

> ⚠️ **CONFIRM THE GITHUB USERNAME FIRST.** Everything below assumes the username is
> **`hugoblur-ctrl`**. This has **not** been verified. If your GitHub username is different,
> replace `hugoblur-ctrl` in (a) the git remote below, (b) every resulting URL, and
> (c) the URLs already wired into the app code (see "URLs used in app code").

## Apps covered

| App | Privacy | Support |
| --- | --- | --- |
| 오늘의 향수 노트 (ScentNote) | `scentnote/privacy.html` | `scentnote/support.html` |
| Lexibite | `lexibite/privacy.html` | `lexibite/support.html` |
| Paletta | `paletta/privacy.html` | `paletta/support.html` |

## Deploy — exact steps

### 1. Create a new PUBLIC repo named `legal`
On GitHub: **New repository** → Owner `hugoblur-ctrl`, Repository name `legal`,
visibility **Public**. Do **not** add a README/.gitignore/license (this folder already
has files). Click **Create repository**.

### 2. Init, commit, and push this folder
Run from inside this `legal_site/` directory:

```bash
cd "path/to/legal_site"
git init
git add .
git commit -m "Add privacy & support pages for ScentNote, Lexibite, Paletta"
git branch -M main
git remote add origin https://github.com/hugoblur-ctrl/legal.git
git push -u origin main
```

> If the username is not `hugoblur-ctrl`, change the remote URL accordingly, e.g.
> `git remote add origin https://github.com/<YOUR_USERNAME>/legal.git`

### 3. Enable GitHub Pages
On GitHub: repo **Settings → Pages** → under **Build and deployment**,
set **Source = Deploy from a branch**, **Branch = `main`**, folder **`/ (root)`** →
**Save**. Wait ~1 minute for the first build.

## Resulting URLs

Base: `https://hugoblur-ctrl.github.io/legal/`

| Page | URL |
| --- | --- |
| Landing | `https://hugoblur-ctrl.github.io/legal/` |
| ScentNote — Privacy | `https://hugoblur-ctrl.github.io/legal/scentnote/privacy.html` |
| ScentNote — Support | `https://hugoblur-ctrl.github.io/legal/scentnote/support.html` |
| Lexibite — Privacy | `https://hugoblur-ctrl.github.io/legal/lexibite/privacy.html` |
| Lexibite — Support | `https://hugoblur-ctrl.github.io/legal/lexibite/support.html` |
| Paletta — Privacy | `https://hugoblur-ctrl.github.io/legal/paletta/privacy.html` |
| Paletta — Support | `https://hugoblur-ctrl.github.io/legal/paletta/support.html` |

After Pages is live, paste the matching **Privacy** URL into each app's
**App Store Connect → App Privacy / App Information → Privacy Policy URL**,
and the **Support** URL into the **Support URL** field.

## URLs used in app code

- **ScentNote** — `AppLinks.privacyPolicy` in
  `ScentNote/ScentNote/EntitlementStore.swift` is wired to
  `https://hugoblur-ctrl.github.io/legal/scentnote/privacy.html`.
- **Lexibite** and **Paletta** — their in-app URL constants are owned/updated separately.
  Point them to the Lexibite/Paletta URLs above.

If the GitHub username turns out not to be `hugoblur-ctrl`, update those in-app constants too.
