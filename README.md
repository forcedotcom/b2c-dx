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
- A `releases/latest.json` marker file pointing at the most recently released monorepo tag.
- The GitHub Actions workflows that turn each merged release PR into a published extension.

What does **not** live here: the extension's source code, build tooling, tests, or developer docs. Those live in the monorepo.

## How a release lands here

1. The monorepo cuts a stable release of `b2c-vs-extension`, builds the VSIX, and attaches it to a GitHub release on the monorepo.
2. The monorepo opens a **release PR** on this repo titled `Release b2c-vs-extension X.Y.Z`. The PR updates `CHANGELOG.md` and rewrites `releases/latest.json` with the version, monorepo tag, and source release URL.
3. A maintainer reviews and merges the PR (this is the manual gate before anything reaches the marketplaces).
4. On merge, `.github/workflows/release-on-merge.yml` reads the marker, downloads the VSIX from the monorepo release, and creates a release on this repo. The release event fires `publish-vscode.yml` and `publish-openvsx.yml`, which `vsce publish` and `ovsx publish` to the marketplaces.

## Issues, bugs, feature requests

File them in the monorepo: <https://github.com/SalesforceCommerceCloud/b2c-developer-tooling/issues>

Issues opened directly on this repo will be redirected.

## Security

Report vulnerabilities to <security@salesforce.com>. See [SECURITY.md](SECURITY.md).

## License

Apache-2.0. See [license.txt](license.txt).
