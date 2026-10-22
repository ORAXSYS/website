# ORAXSYS website deployment

## Current production configuration

- Public site: https://oraxsys.com/; `https://www.oraxsys.com/` redirects to the apex domain.
- Repository: `ORAXSYS/website`, GitHub Pages from `main` and `/ (root)`.
- `CNAME` contains `oraxsys.com`; `.nojekyll` keeps publication static.
- In Cloudflare DNS, `@` and `www` are CNAME records pointing to `oraxsys.github.io`, both **DNS only**.
- HTTPS and the page assets have been verified after the domain move on 2026-10-22.

The development repository `gilshl/orqaxis-website` is private and has Pages disabled. Application development is separate from both website repositories.

## Publish a new version

1. Review a specific commit in the private development repository and check the rendered page, linked assets, and brand text.
2. Copy the approved static files to this repository in one consolidated commit. Keep this repository's `CNAME`, `.nojekyll`, and production deployment documentation. Do not copy a development workflow or domain configuration.
3. Update `publication.json` with the source commit, tree and copied file hashes in the same commit.
4. Wait for GitHub Pages to publish, then check https://oraxsys.com/ and https://www.oraxsys.com/ over HTTPS. Verify stylesheet, favicon, logo, and the main call to action.

Development pushes do not update production. If a published snapshot is broken, revert its production commit and verify GitHub Pages again; keep `CNAME` and DNS intact.

## Email contact

The website does not advertise a domain email address until it is configured and tested. After enabling inbound delivery for `hello@oraxsys.com` and verifying a message arrives, the main call to action can link to that address in a later reviewed release.
