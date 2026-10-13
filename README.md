# Flaccid Sails artwork

This repository publishes fixed UI artwork at
`https://flaccid-sails.github.io/site-assets/v1/assets/`.
Game artwork belongs to Blizzard Entertainment. The original extraction notes
are retained alongside the artwork.

GitHub Pages must use **GitHub Actions** as its source. Deployment runs only
when versioned artwork, the index, or the deployment workflow changes, or when
manually dispatched. There is no scheduled deployment.

## Updating artwork

Published versions are immutable. Copy the complete updated `site/public/assets`
directory from the main site repository into a new version, such as `v2/assets`.
Do not overwrite or delete old versions: cached app builds may still use them.

After the new version is deployed, change `ARTWORK_BASE_URL` in the main site's
`.github/workflows/deploy-site.yml` to `https://flaccid-sails.github.io/site-assets/v2/`
and deploy the main site. Its local artwork must match that version because
the image service worker uses those files to calculate cache hashes.

The main repository retains local artwork for development and its icon fallback.
Talent icons, branding images, application code, and JSON remain with the main site.
