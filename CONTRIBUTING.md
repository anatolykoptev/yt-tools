# Contributing

This repository holds three static pages for a personal tool, so contributions are limited to
corrections.

## What to send

- A typo, a broken link or an accessibility fix in `index.html`, `privacy.html` or `terms.html`.
- A correction to a document in this repository.

Changes to the meaning of the privacy policy or terms are made by the owner only, together with a
change in the tool's behaviour.

## Check before you open a pull request

There is no build or test suite. Open the changed pages in a browser, follow every link between
them, and run:

```sh
repo-standards check --visibility public .
```

`repo-standards` is <https://github.com/anatolykoptev/repo-standards>.

## Rules

- Keep each page a single self-contained HTML file: inline CSS, no scripts, no external
  resources.
- Do not rename or move a page; its address belongs on the OAuth consent screen.
- Update the "Last updated" date on the privacy policy whenever its text changes.
- No hostnames, secrets, OAuth client files or personal data in any file.

## Commits and pull requests

Short imperative subject, the body says why. One concern per pull request, with a line on how you
checked it. A user-visible change adds a line under "Unreleased" in [CHANGELOG.md](CHANGELOG.md),
and a new or renamed document is added to [docs/INDEX.md](docs/INDEX.md).
