---
name: "Contribution Guidelines"
about: "[Please read this excellent guide to get started](https://guides.github.com/activities/hello-world/)."
title: "Contribution Guidelines"
source: "https://github.com/creativecommons/creativecommons.github.io-source/blob/master/content/contributing-code/contents.lr"
---

General contribution guide:

1. Comment on it and say you're working on an issue. This is to avoid conflicts with others also working on the issue.
2. Fork the repository and create a new branch from the default branch (usually `master`), with an appropriate name.
3. Write your code. Follow these guidelines for writing manifests:
    * Read the Wiki on how app manifests work - [App Manifests](https://github.com/ScoopInstaller/Scoop/wiki/App-Manifests) - and how to create one - [Creating an App Manifest](https://github.com/ScoopInstaller/Scoop/wiki/Creating-an-app-manifest).
    * Follow this general order of fields (whichever exist) in the JSON file:
      * `##`
      * `version`
      * `description`
      * `homepage`
      * `license`
      * `depends`
      * `suggest`
      * `architecture`
        * `64bit`
        * `32bit`
        * `arm64`
      * `url`
      * `hash`
      * `extract_dir`
      * `extract_to`
      * `pre_install`
      * `installer`
      * `post_install`
      * `env_add_path`
      * `env_set`
      * `bin`
      * `shortcuts`
      * `persist`
      * `uninstaller`
      * `checkver`
      * `autoupdate`
      * `notes`
    * Use a tab width of 4 spaces.
    * The license property should be a valid [SPDX Identifier](https://spdx.org/licenses).
    * Version must not be raw text or commit id, use [semver](https://semver.org/) if possible.
    * Portable configuration is highly preferred (by using `persist`).
    * If the program file is a CLI application, no need to add it in `shortcuts`.
    * If the program file is a GUI application _and_ it doesn't accept any commandline arguments, no need to add it in `bin`.
    * If an array contains only one item, write it as a string.
    * If the application provides _only_ a 32bit download, the `architecture` field is not required. In all other cases, `architecture` field is mandatory.
4. Test your manifest by installing, uninstalling, checking functionality, persistence etc.
5. Confirm that manifest gets updated automatically - see [App Manifest Autoupdate](https://github.com/ScoopInstaller/Scoop/wiki/App-Manifest-Autoupdate).
6. Submit your pull request. Titles should follow these rules:
    * If it's a new manifest, use `<app name>: Add version <version>`.
    * If it's an update to an existing manifest, use `<app name>@<version>: <small description>`.
    * If it's something related to maintenance, use `(chore): <small description>`.
7. Add a comment starting with "/verify" after raising the PR - this will kick in the automatic manifest verifier.
8. Wait for code review and address any issues raised as soon as you can.

**A note on collaboration:** We encourage people to collaborate as much as possible. We especially appreciate contributors reviewing each others pull requests, as long as you are [kind and constructive](https://medium.com/@otarutunde/comments-during-code-reviews-2cb7791e1ac7) when you do so.

## Proposing a new issue

If you want to work on something that there is no GitHub issue for, follow these steps:

1. Create a new GitHub issue associated with the relevant repository and propose your change there. Be sure to include implementation details and the rationale for the proposed change.
    * We are very reluctant to accept random pull requests without a related issue created first.
2. Wait for a project maintainer to evaluate your issue and decide whether it's something that we will accept a pull request for.
3. Once the project maintainer has approved the issue, you may start work on code as described in the **Contribution process** section above.

When in doubt, ask a question in the Discussions tab.
