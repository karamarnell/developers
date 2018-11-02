---
id: page-plugin
title: Qordoba - GitHub Enterprise App Integration
header_title: Qordoba - GitHub Enterprise App Integration
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

```
Qordoba requires using "https://" and port 443 to access your Github Enterprise server.
```
### Create an Application
Go to your GitHub Enterprise installation, and create a new Application at 

`https://[[host]]/organizations/[[Org Name]]/settings/apps/new`

```

```

Please use these values for the below three fields; and follow Github help as required for the others. Their values do not affect Qordoba interactions.

https://app.qordoba.com
https://app.qordoba.com/githubAppAuthRedirect.html
https://app.qordoba.com/api/qordoba/github/app/webhook/callback
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2372bef-gha-requirefields.png",
        "gha-requirefields.png",
        641,
        291,
        "#f5f5f6"
      ]
    }
  ]
}
[/block]
**Permissions**
*Read-only*
Repository metadata

*Read & write*
Repository contents
Issues
Pull requests
Commit statuses

**Subscribe to events**
Commit comment
Delete
Issues
Pull request
Create
Push
Pull request review comment

Here's an image you can use:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d034fd8-8090724.png",
        "8090724.png",
        200,
        200,
        "#5454ac"
      ]
    }
  ]
}
[/block]
Once the app is created; generate a Private Key for it by clicking "Generate a private key."

Then; in http://app.qordoba.com; during the first "GitHub Enterprise Apps" workflow create, you will be prompted for the below values
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/50d1f6b-GitHub_Enterprise_Apps_Configuration.png",
        "GitHub Enterprise Apps Configuration.png",
        1914,
        947,
        "#b3b7ba"
      ]
    }
  ]
}
[/block]
The `Redirect Url for Installation` is of the form 
`https://[[host]]/organizations/[[Org Name]]/settings/apps/[[App Name]]/installations`
