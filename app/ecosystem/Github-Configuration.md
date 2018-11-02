---
id: page-plugin
title: Qordoba - GitHub Enterprise App Integration
header_title: Qordoba - GitHub Configuration
header_icon: /assets/images/icons/plugins/GitHub-enterprise-integration.png
breadcrumbs:
  Plugins: /ecosystem
nav:
  - label: Getting Started
    items:
      - label: Configuration
  - label: Usage
    items:
      - label: Sending parameters
      - label: Known Issues
---
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e34236d-githubproject.png",
        "githubproject.png",
        724,
        561,
        "#cdccca"
      ],
      "caption": "GitHub project flows"
    }
  ]
}
[/block]
# GitHub OAuth
This is tied to your developer account in GitHub. 

# Choose repository and master branch
Qordoba automatically displays a list of repositories and, subsequently, the branches available for selection. Most developers pick the master branch for the repository, to which Qordoba will automatically configure a required status check.

# Select i18n framework
Select the framework you are using. This allows Qordoba to automatically pull resource files.

# Import existing strings
Qordoba imports existing strings from your repository and automatically creates the language-specific workspaces for your content team, based on the languages set up in the Qordoba project.

