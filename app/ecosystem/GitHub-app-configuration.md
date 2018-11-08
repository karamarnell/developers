---
id: page-plugin
title: Qordoba - GitHub Enterprise App Integration
header_title: Qordoba - GitHub App Configuration
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

This guide will show how to gain the required repository access permissions within Github, as well as how to enable the Github Qordoba App during workspace creation.

### 1. Gain permissions within Github"

Make sure that you have admin privileges to the specific repository that you want to connect Qordoba with. You need the organization admin to add you as an admin collaborator at the repository level:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7929a10-Screen_Shot_2018-06-22_at_3.44.32_PM_1.png",
        "Screen Shot 2018-06-22 at 3.44.32 PM (1).png",
        1568,
        1236,
        "#dedfdf"
      ]
    }
  ]
}
[/block]
Here, I had the admin of the witty-willow organization (Ethan) add me as a collaborator on the Github-Apps-Demo repository.

### 2. Create Workspace Within Qordoba"

In Qordoba, create a new workspace, and fill out the preliminary fields. Make sure that you select "Github Apps" for the integration type. Once you get to the Github authentication page, you should see this:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b1070aa-Screen_Shot_2018-06-22_at_3.45.32_PM.png",
        "Screen Shot 2018-06-22 at 3.45.32 PM.png",
        1808,
        1076,
        "#ededef"
      ]
    }
  ]
}
[/block]
Notice there is a "Authorize your session here" button. Click on it.

### 3. Use Popup to Give Permissions at Repository Level"

When you click the Authorize button, a popup window will appear. In the popup, click Install in the top right, and look for the organization with your desired repository:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/53ed0ef-Screen_Shot_2018-06-22_at_3.55.40_PM.png",
        "Screen Shot 2018-06-22 at 3.55.40 PM.png",
        1766,
        1214,
        "#f5f7f9"
      ]
    }
  ]
}
[/block]

In that organization, you should have permission to specifically allow the one repository that you have admin access to:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f791874-Screen_Shot_2018-06-22_at_3.52.34_PM.png",
        "Screen Shot 2018-06-22 at 3.52.34 PM.png",
        2112,
        1544,
        "#eff3f7"
      ]
    }
  ]
}
[/block]
Once you have selected and saved that repository, you should be able to select that same repository from the dropdown menu back in Qordoba's UI. Afterwards, select your protected branch, as well as the desired naming convention for files that are returning to Github from Qordoba. Complete the workspace creation.

Once the workspace is created, the integration is complete. Qordoba adds a webhook to the Github repository that will look at PRs sent against the protected branch, and pull new content into Qordoba.
