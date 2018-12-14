---
title: Bitbucket Integration 
---

# How to Integrate with Bitbucket

Qordoba's Bitbucket integration simplifies localization management for developers. It automatically detects missing translations and streamlines how translations are received from linguists. Integration increases developer productivity and eliminates errors caused by manual string management.

This guide will show how to enable the Bitbucket Qordoba App during workspace creation.

1. Create Workspace Within Qordoba

In Qordoba, create a new workspace, and fill out the preliminary fields. Make sure that you select "Bitbucket Cloud" for the integration type. Once you get to the Bitbucket authentication page, you should see this:

**insert image here**

Notice there is a "Authorize new org or account" link. Click on it.

2. Use Popup to Give Permissions at Repository Level

When you click the Authorize button, a pop-up window will appear. In the popup, click Grant Access.

**insert image here**


Once you have selected and saved that repository, you should be able to select that same repository from the dropdown menu back in Qordoba's UI. Afterwards, select your protected branch, as well as the desired naming convention for files that are returning to Github from Qordoba. Complete the workspace creation.

Once the workspace is created, the integration is complete. Qordoba adds a webhook to the Github repository that will look at PRs sent against the protected branch and pull new content into Qordoba.
