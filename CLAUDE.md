# CLAUDE.md

Notes for coding agents working in yt-tools: three static HTML pages (`index.html`,
`privacy.html`, `terms.html`) that serve as the public home page, privacy policy and terms of
service for a personal YouTube tool's Google OAuth consent screen. There is no code, no build and
no tests. Every document is indexed in [docs/INDEX.md](docs/INDEX.md).

## Gate

There is no CI workflow. Before a PR, check by hand:

- every page opens in a browser, and each relative link between the three pages resolves;
- `repo-standards check --visibility public .` is clean.

## Invariants that are easy to break

- **Treat the page addresses as registered with Google.** The repository is published with GitHub
  Pages from the root of `main`, and the consent screen is meant to point at these three pages. Do not
  rename, move or delete `index.html`, `privacy.html` or `terms.html`, and do not add a build step
  that changes their paths.
- **The privacy policy must stay true.** It states that the OAuth token and API data stay on the
  owner's computer, that nothing is sold or sent to a server run by the tool, and how access is
  revoked. Change the text only when the tool's behaviour changes, update the "Last updated" date
  with it, and never weaken a statement without that behaviour change.
- **The pages are standalone.** One file each, inline CSS, no scripts, no external resources, so
  they load for the Google verification reviewer and cannot break on a dependency.
- **Everything in the repository is served.** Pages publishes the whole root, documents included,
  and the repository is public. No hostnames, operator paths, account names, tokens, OAuth client
  files or personal data in any tracked file; `.gitignore` excludes common credential files.
- **Licence: Apache-2.0** (owner decision, 2026-11-11). `LICENSE` is the canonical SPDX text; do not edit it.
