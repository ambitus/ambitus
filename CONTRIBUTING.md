# Contribution Guidelines

## Contributions to Projects Under Ambitus

All contributions to projects under Ambitus are subject to the requirements of the Open Mainframe Project and Linux Foundation.  Each project here has its own set of conventions, but all projects follow this common set of guidelines:

- All code contributed must be made under an [Apache 2 license](https://spdx.org/licenses/Apache-2.0.html), and any documentation and non-code will be received and made available by the Project under the [Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0/), following the [license and copyright guidelines of the Open Mainframe Project](https://github.com/openmainframeproject/tsc/blob/master/process/contribution_guidelines.md#license-specification)
- All contributions must be accompanied by a [Developer Certification of Origin (DCO) signoff](https://github.com/openmainframeproject/tsc/blob/master/process/contribution_guidelines.md#developer-certificate-of-origin)
- Contributions must be made as a pull request, and is subject to review by a [committer](https://github.com/ambitus/ambitus/blob/master/GOVERNANCE.md#committer) to be accepted.
- All projects must release code with a unique version id correlates to a set of documented changes so users can understand the function contained in the package.  Version IDs should follow either the
[Semantic Versioning](https://semver.org/) or [Calendar Versioning](https://calver.org/) convention.
- Projects should tag their releases to make identification of finished works easier to find.
- Projects must provide a human-readable summary of major changes in each release.  These can be provided as release notes, CHANGELOG, NEWS, discussion group announcement, or something similar. The key is being in a human-readable form rather than something like raw git log output.
- Release notes for a project must list all CVEs that the release resolves.
- Each project will have a security policy in ```SECURITY.md```, and provide a means to report security vulnerabilities privately.  Both of these can be enabled in Github Security overview settings.

If you have any questions or concerns - feel free to reach out to [ambitus-discussion@lists.openmainframeproject.org](ambitus-discussion@lists.openmainframeproject.org).

## Contributions to the Ambitus Repo

If you'd like to make a commit to the Ambitus repo itself there are a couple of additional things that you'll need to be aware of.

This repository is using a combination of the following tools. Both can be installed with VSCode as extensions or standalone.

It is recommended and is easier to use these as VSCode Extensions. PR checking is enabled to make sure that the linting has happened. PR reviews will expose Prettier not being used.

### VSCode Extensions
- [MarkdownLint VSCode Extension](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint)
- [Prettier VSCode Extension](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)

### Instructions for an NPM install
- [MarkdownLint CLI Installation](https://github.com/DavidAnson/markdownlint-cli2)
- [Prettier CLI Installation](https://prettier.io/docs/install)