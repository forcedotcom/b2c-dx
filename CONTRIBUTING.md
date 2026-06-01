# Contributing Guide for the B2C DX VS Code Extension

This repository is the **publishing surface** for the B2C DX VS Code Extension on the Visual Studio Marketplace and Open VSX. Development of the extension does **not** happen here.

- **Source code, issues, pull requests, and development discussion** all live in the development monorepo: <https://github.com/SalesforceCommerceCloud/b2c-developer-tooling>.
- This repo holds only the marketplace landing page, governance files, release artifacts (mirrored from the monorepo), and the workflows that publish those artifacts to the two marketplaces.

If you are looking to contribute code, file a bug, or request a feature, please open an issue or pull request in the monorepo: <https://github.com/SalesforceCommerceCloud/b2c-developer-tooling/issues>.

# Governance Model

## Salesforce Sponsored

The intent and goal of open sourcing this project is to increase the contributor and user base. However, only Salesforce employees will be given `admin` rights and will be the final arbiters of what contributions are accepted or not.

# Issues, requests & ideas

Use the monorepo's [Issues page](https://github.com/SalesforceCommerceCloud/b2c-developer-tooling/issues) to submit issues, enhancement requests, and discuss ideas. Issues opened directly on this repo will be redirected.

### Bug Reports and Fixes
- Search the [monorepo issues](https://github.com/SalesforceCommerceCloud/b2c-developer-tooling/issues) before filing a new one. If your bug isn't tracked, [open a new issue](https://github.com/SalesforceCommerceCloud/b2c-developer-tooling/issues/new) there.
- If you'd like to submit a fix, send the pull request to the monorepo and reference the issue.

### New Features
- Describe the problem you want to solve in a [new monorepo issue](https://github.com/SalesforceCommerceCloud/b2c-developer-tooling/issues/new).
- Wait for maintainer feedback before writing the code so we can confirm alignment.

# Contributions to this repo

Pull requests are welcome here only for the narrow set of files this repo owns: marketplace `README.md`, `CHANGELOG.md` (when not auto-mirrored), governance docs (`CODE_OF_CONDUCT.md`, `SECURITY.md`, `CONTRIBUTING.md`), and the publish workflows under `.github/workflows/`. All other changes — extension features, bug fixes, build tooling — go to the monorepo.

# Contribution Checklist

- [x] Clean, simple, well styled changes
- [x] Commits should be atomic and messages must be descriptive. Related issues should be mentioned by issue number.
- [x] Reviews
  - Changes must be approved via peer code review

# Creating a Pull Request

1. **Confirm the change belongs in this repo** (see the narrow scope above). If it's an extension feature or bug fix, open the PR in the [monorepo](https://github.com/SalesforceCommerceCloud/b2c-developer-tooling) instead.
2. **Clone** the forked repo to your machine.
3. **Create** a new branch to contain your work.
4. **Commit** changes to your own branch.
5. **Push** your work back up to your fork.
6. **Submit** a Pull Request against the `main` branch.
7. **Sign** the Salesforce CLA (you will be prompted to do so when submitting the Pull Request).

# Contributor License Agreement ("CLA")

In order to accept your pull request, we need you to submit a CLA. You only need to do this once to work on any of Salesforce's open source projects.

Complete your CLA here: <https://cla.salesforce.com/sign-cla>

# Code of Conduct

Please follow our [Code of Conduct](CODE_OF_CONDUCT.md).

# License

By contributing your code, you agree to license your contribution under the terms of our project [license](license.txt) and to sign the [Salesforce CLA](https://cla.salesforce.com/sign-cla).
