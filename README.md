# Ticketum Backup — public information

A small, public information site for the administrator-operated Ticketum Backup OAuth application. This repository contains **only public documents and static assets**, not the private Ticketum application or backup credentials.

- Homepage: https://sotokuu.github.io/ticketum-privacy/
- Privacy Policy: https://sotokuu.github.io/ticketum-privacy/privacy.html
- Terms: https://sotokuu.github.io/ticketum-privacy/terms.html
- Public contact: jond50736@gmail.com

The backup automation is prepared. Google Drive authorization and the complete cloud backup process have not yet been validated. Publishing this website does not activate backups.

## Files and publication

`index.html`, `privacy.html`, `terms.html`, `styles.css`, `logo.svg`, `.nojekyll`, and this README. No framework, build command, npm packages, JavaScript, analytics or external fonts.

GitHub Settings → Pages → Build and deployment → Deploy from a branch → `main` → `/(root)` → Save. Keep the repository public. GitHub Pages publishes the static pages after pushes to main. Check the Pages deployment status in Actions and both public URLs after changes.

The ticket icon reuses the existing Ticketum brand artwork. All pages use relative links so the project path works on GitHub Pages.

## Google Auth Platform setup (manual)

In **Ticketum Backups → Branding**, use:

| Field | Value |
| --- | --- |
| App name | Ticketum Backup |
| User support email | jond50736@gmail.com (must be selectable for the current Google project) |
| Application home page | https://sotokuu.github.io/ticketum-privacy/ |
| Application privacy policy link | https://sotokuu.github.io/ticketum-privacy/privacy.html |
| Application terms of service link | https://sotokuu.github.io/ticketum-privacy/terms.html |

Use a reachable developer contact address chosen by the project owner. The OAuth client name **Ticketum Backup Client** is a separate field; the existing Desktop app client need not be replaced with a Web client to publish these documents. This task does not change OAuth redirects or credentials.

In **Data Access**, confirm that only `https://www.googleapis.com/auth/drive.file` is requested for Drive. In **Audience**, review External settings, then select **Publish app** if Google permits it and the owner chooses to proceed. This changes Publishing status to In production. It does not by itself verify branding, establish domain ownership, test the integration, or start scheduled backups.

After publishing, obtain a new offline refresh token through the existing secure Desktop OAuth procedure, since a token issued during Testing may still have the testing lifetime. Never enter tokens or client credentials in this repository. Configure automation secrets separately and verify a manual backup and isolated recovery before enabling any schedule.

## Domain ownership: important limitation

These pages are publicly hosted content, **not proof of Google domain verification**. `github.io` is a shared hosting domain, not a domain owned by the application operator. Do not claim ownership of `github.io` or assume that entering `sotokuu.github.io` in Authorized domains will pass Google's checks.

Google's domain-verification remediation guidance currently calls for a Search Console **Domain property verified via DNS**, rather than a URL-prefix property. An HTML verification file can demonstrate control of a GitHub Pages URL prefix for Search Console, but that is not the DNS proof required by that guidance. Ordinary project Pages hosting cannot edit the DNS TXT records of `github.io` or `sotokuu.github.io`.

If Branding accepts these URLs, they are useful public disclosures; acceptance of the fields is not a verification result. If the console rejects the authorized domain or requests DNS proof, stop there rather than claim verification or change unrelated hosting.

The narrow Drive scope is **non-sensitive**. Google distinguishes Publishing status, brand verification, and sensitive/restricted scope verification. Personal-use apps (fewer than 100 users personally known to the operator) may be exempt from mandatory verification. For a single-owner backup tool, using that exemption with the existing Desktop OAuth client may avoid a verified-domain purchase **if the console allows publishing without brand verification**. It does not guarantee branded consent screens or exemption from Google's data policies.

If Google insists on DNS domain verification in this project's actual flow, GitHub Pages alone does not provide a guaranteed free workaround. Use an already-owned domain with DNS control (no new purchase required), or a legitimately delegated domain whose provider permits DNS TXT verification and whose domain Google accepts. A custom domain can point to the same Pages site. This requires a separate owner decision; no domain has been acquired or verified here. Another shared `netlify.app` site does not automatically solve DNS ownership.

If verification is actually required, inspect **Verification Center → Branding / View issues** and complete the requested evidence using the Google account with project-owner rights. The owner must submit any verification request; this repository does not submit one and does not promise approval.

## Official sources checked November 5, 2026

- [Drive scope classification](https://developers.google.com/workspace/drive/api/guides/api-specific-auth)
- [OAuth policies and production homepage](https://developers.google.com/identity/protocols/oauth2/policies)
- [Branding fields](https://support.google.com/cloud/answer/15549049?hl=en)
- [Publishing status and Audience](https://support.google.com/cloud/answer/15549945?hl=en)
- [Verification exceptions, including personal use](https://support.google.com/cloud/answer/13464323?hl=en)
- [DNS domain verification requirements](https://support.google.com/cloud/answer/13804266?hl=en)
- [OAuth token lifetime](https://developers.google.com/identity/protocols/oauth2)
- [GitHub Pages publication](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site)

No backup files, client secrets, OAuth JSON, refresh tokens, encryption keys, viewer data or private manifests belong here. The public website does not read Google APIs or contact the Ticketum database.
