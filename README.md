<h1 align="center">B2C DX VS Code Extension</h1>

<p align="center">
  <strong>The official Salesforce VS Code extension for B2C Commerce developer experience.</strong>
  <br>
  Sandbox explorer · Cartridge code sync · WebDAV · Content libraries · SCAPI browser · B2C Script debugger
</p>

<p align="center">
  <a href="https://marketplace.visualstudio.com/items?itemName=Salesforce.b2c-vs-extension">
    <img alt="VS Marketplace version" src="https://img.shields.io/visual-studio-marketplace/v/Salesforce.b2c-vs-extension?label=VS%20Marketplace&color=0066d4">
  </a>
  <a href="https://marketplace.visualstudio.com/items?itemName=Salesforce.b2c-vs-extension">
    <img alt="VS Marketplace installs" src="https://img.shields.io/visual-studio-marketplace/i/Salesforce.b2c-vs-extension?label=installs&color=0066d4">
  </a>
  <a href="https://open-vsx.org/extension/Salesforce/b2c-vs-extension">
    <img alt="Open VSX version" src="https://img.shields.io/open-vsx/v/Salesforce/b2c-vs-extension?label=Open%20VSX&color=a60ee5">
  </a>
  <a href="license.txt">
    <img alt="License: Apache-2.0" src="https://img.shields.io/badge/license-Apache%202.0-blue">
  </a>
</p>

<p align="center">
  <a href="https://marketplace.visualstudio.com/items?itemName=Salesforce.b2c-vs-extension"><strong>Install</strong></a>
  ·
  <a href="https://salesforcecommercecloud.github.io/b2c-developer-tooling/vscode-extension/"><strong>Documentation</strong></a>
  ·
  <a href="https://github.com/SalesforceCommerceCloud/b2c-developer-tooling"><strong>Source &amp; Issues</strong></a>
  ·
  <a href="CHANGELOG.md"><strong>Changelog</strong></a>
</p>

---

## Install

From the command line:

```bash
code --install-extension Salesforce.b2c-vs-extension
```

Or in VS Code: **Extensions → search "B2C DX" → Install**.

For VSCodium / Cursor / Eclipse Theia, install from [Open VSX](https://open-vsx.org/extension/Salesforce/b2c-vs-extension).

## Documentation

End-user documentation — installation, configuration, and feature tour — lives at:

<https://salesforcecommercecloud.github.io/b2c-developer-tooling/vscode-extension/>

## This repository

**This repo is the publishing surface for the extension.** Development happens in the development monorepo:

<https://github.com/SalesforceCommerceCloud/b2c-developer-tooling>

What lives here:

- The marketplace landing page (this README), Apache-2.0 license, and governance files (CODE_OF_CONDUCT, CONTRIBUTING, SECURITY, CODEOWNERS).
- A mirrored CHANGELOG.
- Per-version `releases/*.json` markers (and a `releases/latest.json` pointer) recording the monorepo tag and the VSIX's sha256.
- The GitHub Actions workflows that turn each release into a published extension.

What does **not** live here: the extension's source code, build tooling, tests, or developer docs. Those live in the monorepo.

Nothing published from this repo is built here. The only artifact that crosses the boundary is the VSIX, which is built and cryptographically attested (SLSA build provenance) in the monorepo. Every workflow here re-verifies that provenance before acting, so a tampered or foreign VSIX cannot reach the marketplaces.

## How a release lands here

1. The monorepo cuts a stable release of `b2c-vs-extension`, builds the VSIX, attaches it to a GitHub release on the monorepo, and **attests its build provenance**.
2. The monorepo fires a `repository_dispatch` event to this repo carrying the version, monorepo tag, and the VSIX sha256. `.github/workflows/receive-monorepo-release.yml` validates the payload, downloads the VSIX, **verifies its sha256 and build provenance**, and opens a **release PR** titled `Release b2c-vs-extension X.Y.Z` that updates `CHANGELOG.md` and the `releases/*.json` markers.
3. A maintainer reviews and merges the PR (this is the manual gate before anything reaches the marketplaces).
4. On merge, `.github/workflows/release-on-merge.yml` reads the marker, downloads the VSIX, **re-verifies sha256 + provenance**, and creates a release on this repo — then triggers `publish-vscode.yml` and `publish-openvsx.yml`.
5. Each publish workflow runs in the protected `publish` environment (where the marketplace tokens live), **verifies provenance one final time**, and then `vsce publish` / `ovsx publish` to the VS Code Marketplace and Open VSX.

## Issues, bugs, feature requests

File them in the monorepo: <https://github.com/SalesforceCommerceCloud/b2c-developer-tooling/issues>

Issues opened directly on this repo will be redirected.

## Security

Report vulnerabilities to <security@salesforce.com>. See [SECURITY.md](SECURITY.md).

## License

Apache-2.0. See [license.txt](license.txt).
