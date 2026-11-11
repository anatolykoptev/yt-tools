# yt-tools

The public web pages of a personal YouTube tool: a home page, a privacy policy and terms of
service. They exist because Google's OAuth consent screen for the YouTube Data API and YouTube
Analytics API requires a public home page, privacy policy and terms of service for the app. The
tool itself is not in this repository, it is not offered to other people and it has no sign-up.

## What is here

| File | Page |
|---|---|
| `index.html` | Home: what the tool is and who uses it (the channel owner, on their own computer) |
| `privacy.html` | Privacy policy: what the tool accesses with the owner's consent, where data stays, how to revoke access |
| `terms.html` | Terms of service: provided as is, governed by the YouTube Terms of Service |

Each page is one self-contained HTML file with inline CSS: no build step, no scripts, no
dependencies, no configuration and no environment variables.

## View and publish

Open the files in a browser, or serve the directory with any static file server, for example
`python3 -m http.server`. The repository is published with GitHub Pages from the `main` branch,
root directory, so a change merged to `main` goes live without a further step. The page addresses
belong on the OAuth consent screen, so treat them as fixed: do not rename or move a page.

## Status

Stable and rarely changed. The privacy policy is dated; update the date whenever its text changes.
History is in [CHANGELOG.md](CHANGELOG.md), notes for agents in [CLAUDE.md](CLAUDE.md), contribution
rules in [CONTRIBUTING.md](CONTRIBUTING.md), and every document in [docs/INDEX.md](docs/INDEX.md).
Security reports go through [SECURITY.md](SECURITY.md). Licensed under Apache-2.0, see [LICENSE](LICENSE).
