# B2C DX VS Code Extension

The official Salesforce VS Code extension for **B2C Commerce** developer experience: sandbox realm explorer, cartridge code sync, WebDAV browser, content libraries, SCAPI API browser, B2C Script debugger, scaffold/CAP install, log tailing, and a Page Designer Assistant.

## Install

- **VS Code Marketplace:** <https://marketplace.visualstudio.com/items?itemName=Salesforce.b2c-vs-extension>
- **Open VSX:** <https://open-vsx.org/extension/Salesforce/b2c-vs-extension>

From the command line:

```bash
code --install-extension Salesforce.b2c-vs-extension
```

## Documentation

End-user documentation — installation, configuration, and feature tour — lives at:

<https://salesforcecommercecloud.github.io/b2c-developer-tooling/vscode-extension/>

## This repository

**This repo is the publishing surface for the extension.** Development happens in the development monorepo:

<https://github.com/SalesforceCommerceCloud/b2c-developer-tooling>

What lives here:

- The marketplace landing page (this README), Apache-2.0 license, and governance files (CODE_OF_CONDUCT, CONTRIBUTING, SECURITY, CODEOWNERS).
- A mirrored CHANGELOG.
- The GitHub Actions workflows that publish each release to VS Code Marketplace and Open VSX.

What does **not** live here: the extension's source code, build tooling, tests, or developer docs. Those live in the monorepo.

## Issues, bugs, feature requests

File them in the monorepo: <https://github.com/SalesforceCommerceCloud/b2c-developer-tooling/issues>

Issues opened directly on this repo will be redirected.

## Security

Report vulnerabilities to <security@salesforce.com>. See [SECURITY.md](SECURITY.md).

## License

Apache-2.0. See [license.txt](license.txt).
