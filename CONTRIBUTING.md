# Contributing to vxedge

Thanks for considering a contribution. vxedge is a research testbed, so some changes can affect
a published reproducibility claim. Read this before opening a PR or an issue.

This file applies to every repository in the `vxedge` org unless a repository's own
`CONTRIBUTING.md` overrides a section. Build, test and lint commands are **not** repeated here.
Each repository's `AGENTS.md` is the authoritative source for those.

## Before you start

- **Open an issue before a PR** for anything beyond a typo or an obvious bug fix. A change that
  looks cosmetic can move a measured number. See the methodology in
  [`docs/ARCHITECTURE.md`](https://github.com/vxedge/docs/blob/main/ARCHITECTURE.md) §12.
- **Manifests and the vxAPI protobuf (`vxedge/proto/`) are cross-language interfaces.** A change
  to either affects every downstream repository, so call it out explicitly in the PR description.
- **Single-source-of-truth rules apply** ([`ARCHITECTURE.md`](https://github.com/vxedge/docs/blob/main/ARCHITECTURE.md) §4):
  - A part's `part.yaml` in `vxparts` is authoritative for its images and node IDs.
  - An experiment manifest's `services` block is authoritative for runtime config, but not for the service's code.

## Making a change

1. Fork the repository and branch from `main`.
2. Run the repository's build, test and lint commands (see its `AGENTS.md`) before opening the PR.
3. Follow the existing code style. Rust repositories run `cargo fmt`, `cargo clippy -D warnings`,
   and `cargo deny` in CI.
4. Add a line under `[Unreleased]` in `CHANGELOG.md` for any user-visible change (Keep a Changelog
   format; see [`docs/VERSIONING.md`](https://github.com/vxedge/docs/blob/main/VERSIONING.md)).
5. New source files start with an SPDX header: `SPDX-License-Identifier: Apache-2.0` for code, and
   `CC-BY-4.0` for docs, manifests and models.
6. Open the PR against `main`. Describe **what** changed and **why**, because the commit history
   doubles as the project's research log.

## Sign your commits (DCO)

Every commit must carry a Developer Certificate of Origin sign-off
(<https://developercertificate.org>), which certifies that you wrote the change or have the right to submit it:

```bash
git commit -s -m "your message"
# adds: Signed-off-by: Your Name <you@example.com>
```

There is no CLA.

## What gets merged

- **Bug fixes and documentation corrections** take the fast path.
- **New features, manifest schema changes, and anything that touches a measured metric** need a
  prior issue. Any change affecting a published result also needs a note on how it was verified
  against the existing results archive.

## Licensing

By contributing, you agree that your contribution is licensed under the same terms as the repository
you contribute to: Apache-2.0 (`LICENSE`) for code, and CC BY 4.0 (`LICENSE-DOCS`) for docs,
results, figures and models.

## Code of conduct

This project follows the Contributor Covenant. See [`CODE_OF_CONDUCT.md`](CODE_OF_CONDUCT.md).

## Questions

Open an issue on the relevant repository, or email **hello@vxedge.dev**. For anything
security-sensitive, see [`SECURITY.md`](SECURITY.md).
