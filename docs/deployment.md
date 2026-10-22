# ORAXSYS website deployment

## Repositories

Develop the website in `gilshl/orqaxis-website`. Publish reviewed snapshots to `ORAXSYS/website`. A development commit does not automatically update production.

Only static website files belong here. Application development remains in its separate repository.

## Initial GitHub Pages setup

1. Open https://github.com/ORAXSYS/website/settings/pages.
2. Under **Build and deployment**, choose **Deploy from a branch**.
3. Select **main** and **/ (root)**, then **Save**.
4. Wait for the Pages deployment to succeed.
5. Open https://oraxsys.github.io/website/ and check the page, logo, stylesheet, and navigation.

This snapshot intentionally has no `CNAME` or custom deployment workflow. GitHub Pages publishes the selected branch; `.nojekyll` keeps the site static. Do not enable a second deployment workflow for the same site.

The existing custom domain remains attached to the development repository until cutover.

## Move oraxsys.com after validating the new site

1. In `gilshl/orqaxis-website` → **Settings → Pages**, remove the custom domain `oraxsys.com`. Keep the development repository.
2. In `ORAXSYS/website` → **Settings → Pages**, set the custom domain to `oraxsys.com` and save.
3. In Cloudflare DNS for `oraxsys.com`, change both CNAME targets to `oraxsys.github.io`:
   - `@` → `oraxsys.github.io`, **DNS only**.
   - `www` → `oraxsys.github.io`, **DNS only**.
4. Wait for GitHub's DNS check and certificate provisioning to complete.
5. Enable **Enforce HTTPS** when available.
6. Verify https://oraxsys.com and https://www.oraxsys.com, including the logo and stylesheet.

Add the custom domain in GitHub before changing its DNS. Keep the production `CNAME` created by Pages when promoting future snapshots.

If the new deployment fails validation, pause the cutover. To roll back after moving the domain, remove it from the production Pages settings, restore it in the personal repository's Pages settings, and restore both Cloudflare targets to `gilshl.github.io`.

## Later publications

Review a specific development commit. Copy its static website files in one consolidated commit and update `publication.json`. Preserve this repository's deployment documentation, `.nojekyll`, and production `CNAME`. Do not copy development deployment workflows or a development `CNAME`.

## Content follow-up

The initial import preserves the website's existing branding. The Contact Us link still points to `hello@orqaxis.com`; verify an approved replacement mailbox before the final branding update.
