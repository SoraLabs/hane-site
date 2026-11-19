# Hane public website — Phase 5H

This folder contains the **public-facing website only** for Hane (Sora Lab). It contains no application source code, keys, certificates, model files, or MSIX packages. It is based on the read-only Claude Code privacy audit at sealed commit `c668ade` and should be reviewed by the publisher before publication.

## Files

- `index.html` — simple landing page
- `privacy.html` — privacy policy (the Partner Center privacy-policy URL)
- `support.html` — support page
- `style.css` — locally hosted website styles; no trackers, scripts, or remote fonts
- `PRIVACY-POLICY.md` — editable master text for the privacy policy
- `.nojekyll` — keeps GitHub Pages a simple static website

## Publish using GitHub Pages

1. Sign into GitHub and create a **new separate PUBLIC repository** such as `hane-site` or `hane-privacy` (do not make the Hane application repository public).
2. Upload the **individual files in this folder** to the new repository's root; do not upload the ZIP as a single file.
3. Open the new repository's **Settings → Pages**.
4. For **Build and deployment**, choose **Deploy from a branch**; select `main` and `/(root)`; save.
5. Wait for GitHub Pages to publish, then check both the policy and support links in a private/incognito browser window.
6. The expected URLs for a repository called `hane-site` are `https://YOUR-GITHUB-USERNAME.github.io/hane-site/privacy.html` and `/support.html`. Replace the placeholder with the actual account and repo names; do not assume the URLs exist until verified.
7. Enter the verified `privacy.html` URL as Hane's **Privacy policy URL** in Partner Center. Use the support email `hane.support@gmail.com` or the verified `support.html` URL as **Support contact info**.

Publishing GitHub Pages makes these documents public **but does not publish the Hane app or its private source repository**. Keep the Microsoft Store private audience restriction configured separately.

## Before release

- The draft currently displays an effective date of 19 November 2026; if publishing later, update the date in both `privacy.html` and `PRIVACY-POLICY.md` to the actual first-publication date.
- Confirm the full policy matches the exact Store binary / release behavior.
- Confirm `hane.support@gmail.com` receives mail.
- Review Google Gemini's provider terms, especially unpaid-tier content use, developer terms and age restrictions, before setting the Microsoft Store age rating and target markets.
- Confirm provider links and policy wording are still current.
- Confirm the public website is accessible without login and works on mobile.
- Record the published URL in Phase 5H submission notes.

No content in this folder has been published automatically.
