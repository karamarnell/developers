---
id: page-plugin
title: Qordoba - GitHub integration
header_title: Qordoba - GitHub integration
header_icon: /assets/images/icons/plugins/GitHub-integration.png
breadcrumbs:
  Plugins: /ecosystem
nav:
  - label: Getting Started
    items:
      - label: Configuration
  - label: Usage
    items:
      - label: Associating Consumers
      - label: Upstream Headers
      - label: Paginate through the ACLs
      - label: Retrieve the Consumer associated with an ACL
---
Qordoba's GitHub integration simplifies localization management for developers. It automatically detects missing translations and streamlines how translations are received from linguists. Integration increases developer productivity and eliminates errors caused by manual string management.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/05ada0d-github.png",
        "github.png",
        909,
        664,
        "#cbcbca"
      ],
      "caption": "Sequence diagram of a Qordoba GitHub project"
    }
  ]
}
[/block]
# Integration
This GitHub integration provides the following benefits:
* Automatically detects missing translations in Pull Requests (PRs).
* Simplifies developer requests for translation support.
* Streamlines how translations get merged into a developer's feature branch.

Qordoba satisfies these requirements by performing status checks on protected branches within GitHub. When a pull request is created on the `Master` branch, Qordoba looks for missing translations based on a project's configuration, and prevents pull requests from being merged until all of the required translations are added.

# Pull Requests
Qordoba delivers localized strings to developers by creating a pull request. When developers approve the strings in the Qordoba application, a pull request can be created. This process should include the creation of:
* A branch of the original feature branch that triggered the status check.
* A single commit for each target language.
* A PR that uses the following template in the description field.

```
Localized strings for <branch-name>
| Target locale | Resource file | Number of strings |
|:------------- |:------------- |------------------ |
| …             | …             | …                 |
| …             | …             | …                 | 
/cc @<developer-name>
```

# Status Checks
Required status checks on protected branches are a relatively new addition to GitHub, added in late 2015. They allow third-party integrations like Qordoba to monitor pull requests for breaking changes. In most cases, the status checks are used for continuous integration testing. However, they can be also be used for translation workflows. If the status check fails, the following sequence of events will likely take place:
* Developer requests translations by following the link from the status check UI in GitHub PR.
* Linguists complete translation work associated with PR.
* Linguists create pull request from within Qordoba once translations ready.
* PR consists of a Qordoba-created branch merging into developer's origin branch.
* Developer merges the Qordoba branch containing translations into their origin branch.
* Qordoba status check now passes since translations have been added to origin branch.
* Developer can merge to `Master` and ship their localized feature.

## Anatomy
[block:parameters]
{
  "data": {
    "h-0": "Entity",
    "h-1": "Notes",
    "0-0": "Framework Configuration",
    "0-1": "During `project configuration`, the user confirms the i18n framework being used by the repository in question. This allows Qordoba to know where resources files should live within the repository. (Note: only a subset of frameworks will be supported to start with. Support for custom frameworks and/or file types will come later.)",
    "1-0": "Source locale",
    "1-1": "During `project configuration`, the user confirms the source locale (source language) for the project.",
    "2-0": "Target locales",
    "2-1": "During `project configuration`, the user confirms the target locale(s) (target languages) for the project.",
    "3-0": "PR files",
    "3-1": "Listing of files changed as part of this PR. Qordoba only checks for changes to resource files."
  },
  "cols": 2,
  "rows": 4
}
[/block]
# Use Cases
## PR with missing translations
_Scenario:_ Developer creates a pull request that requires translations.
_Given:_ Qordoba status check enabled.
_And:_ Resource file(s) changed as part of PR.
_Then:_ Mark status check as failing.
_And:_ Have status check URL link to the page from which translations can be requested.

## PR with failing status check
_Scenario:_ Developer needs to request translations for failing status check.
_Given:_ Failing Qordoba status check for PR.
_And:_ Developer clicked status check URL and landing on the page hosted by Qordoba.
_Then:_ Allow the developer to request translations.
_And:_ Notify linguists that work is waiting.

## PR with no missing translations
This use case should occur after a Qordoba branch with translations merges into developer's feature branch.

_Scenario:_ Developer creates a pull request that DOES NOT require translations.
_Given:_ Qordoba status check enabled.
_And:_ No resource files changed as part of PR.
_Then:_ Mark the status check as passing.
