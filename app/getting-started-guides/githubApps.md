---
title: Github Apps Integration 
---

# How to Integrate with GitHub

Qordoba's GitHub integration simplifies localization management for developers. It automatically detects missing translations and streamlines how translations are received from linguists. Integration increases developer productivity and eliminates errors caused by manual string management.

![flow](https://github.com/Qordobacode/developers/blob/dev/app/_assets/images/githubflow.png)

This guide will show how to gain the required repository access permissions within Github, as well as how to enable the Github Qordoba App during workspace creation.


1. Gain permissions within Github

Make sure that you have admin privileges to the specific repository that you want to connect with Qordoba. You need the organization admin to add you as an admin collaborator at the repository level.

2. Create Workspace Within Qordoba

In Qordoba, create a new workspace, and fill out the preliminary fields. Make sure that you select "Github Apps" for the integration type. Once you get to the Github authentication page, you should see this:

![workspace](https://github.com/Qordobacode/developers/blob/images/app/_assets/images/githubWorkspace.png) 

Notice there is a "Authorize your session here" button. Click on it.

3. Use Popup to Give Permissions at Repository Level

When you click the Authorize button, a popup window will appear. In the popup, click Install in the top right, and look for the organization with your desired repository:

![permissions](https://github.com/Qordobacode/developers/blob/images/app/_assets/images/githubPermission.png)

In that organization, you should have permission to specifically allow the one repository that you have admin access to:

![repo](https://github.com/Qordobacode/developers/blob/images/app/_assets/images/githubRepo.png)

Once you have selected and saved that repository, you should be able to select that same repository from the dropdown menu back in Qordoba's UI. Afterwards, select your protected branch, as well as the desired naming convention for files that are returning to Github from Qordoba. Complete the workspace creation.

Once the workspace is created, the integration is complete. Qordoba adds a webhook to the Github repository that will look at PRs sent against the protected branch and pull new content into Qordoba.
