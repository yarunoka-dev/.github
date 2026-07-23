# Contributing to Yarunoka

Thank you for considering a contribution. These guidelines apply to
every repository in the yarunoka-dev organization.

## Reporting issues

- Use the issue forms of the repository where the problem lives.
- Never report security vulnerabilities in public issues — follow the
  [security policy](SECURITY.md) instead.

## Pull requests

- For anything beyond a trivial fix, open an issue first so the change
  can be discussed before you invest work in it.
- Keep each pull request to a single topic.
- CI must pass; each repository defines its own checks.
- The DSL is defined by the [spec
  repository](https://github.com/yarunoka-dev/spec). Implementations
  follow the spec, so propose behavior changes there rather than in an
  implementation repository.

## Documentation

Each public repository keeps its documentation in `docs/`. The
yarunoka.dev site builds versioned documentation from these files,
reading released tags only — nothing on main is published until a
release is tagged.

The rules below are the essentials. They are enforced mechanically
when the site builds; the validation code is the authoritative
definition of the exact rules.

### Structure

- The top level of `docs/` holds `index.md` (required — it becomes
  the landing page of a documentation version) and a fixed set of
  sections: `concepts`, `guides`, `reference`, and, in the spec
  repository only, `specification`. Use only the sections the
  repository needs.
- A section is either a single page (`guides.md`) or a directory of
  pages (`guides/` with a required `guides/index.md`) — never both.
- Do not nest further: pages live directly inside a section
  directory at the deepest.
- Files that are not Markdown (images and the like) go under
  `docs/assets/`, the only reserved directory outside the section
  set. Refer to them by relative path.
- In implementation repositories, `docs/reference/` is generated
  from docblocks in the source code. Do not edit it by hand — fix
  the docblock instead.

### File names

- Page files are named in lowercase English kebab-case
  (`getting-started.md`), and the name should describe the page's
  subject — file names become URLs.
- Do not prefix names with numbers for ordering; ordering is what
  `sidebar.order` is for.
- `index.md` is reserved for the entry page of the top level and of
  section directories.
- Renaming a page changes its URL. Avoid it; when unavoidable, do
  it in a new version only.

### Frontmatter

Every page carries exactly these three keys, all required:

```yaml
---
title: Page title
description: A one-sentence summary of the page.
sidebar:
  order: 1
---
```

No other keys are accepted. The dividing line: what a document says
and how the pages are organized belongs to the author — how the
site looks and behaves belongs to the website.

### Language

Write documentation in English. Translations are generated on the
website side — do not add translated pages to `docs/`.

## Contributor License Agreement

On your first pull request, the CLA assistant bot asks you to sign the
[Yarunoka Individual Contributor License
Agreement](CLA.md). Signing once covers all repositories in the
organization.

## AI-assisted contributions

We neither prohibit AI assistance nor require its disclosure. What we
require is responsibility: by signing the CLA you accept full
responsibility for every part of your contribution, however it was
produced. Submit only what you have personally reviewed and can stand
behind.

## Development setup

See the README and docs of each repository.
