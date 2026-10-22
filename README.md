# ORAXSYS public website

This repository holds reviewed snapshots of the public website.

- Website development: [gilshl/orqaxis-website](https://github.com/gilshl/orqaxis-website).
- Production website: [ORAXSYS/website](https://github.com/ORAXSYS/website).
- Application source stays in its separate development repository.

Updates in the development repository do not automatically publish here. Promote a reviewed snapshot in one commit and update `publication.json` with its source commit and file hashes. Keep production deployment settings and `CNAME` separate from development.

## Initial publication

The imported website keeps its existing content and branding. Source provenance is recorded in `publication.json`.

Enable GitHub Pages under **Settings → Pages → Deploy from a branch**, selecting **main** and **/ (root)**. Test the initial site at https://oraxsys.github.io/website/ before moving the custom domain.

See [docs/deployment.md](docs/deployment.md) for the domain cutover and future publication process.
