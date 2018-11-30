---
title: Github Enterprise Integration 
---
**Note**: Qordoba requires using "https://" and port 443 to access your Github Enterprise server.

# How to Integrate with GitHub Enterprise

This guide will show how to gain the required repository access permissions within Github, as well as how to enable the Github Qordoba App during workspace creation.

Go to your GitHub Enterprise installation, and create a new Application at:

  https://[[host]]/organizations/[[Org Name]]/settings/apps/new
  
Please use these values for the below three fields; and follow Github help as required for the others. Their values do not affect Qordoba interactions.

https://app.qordoba.com
https://app.qordoba.com/githubAppAuthRedirect.html
https://app.qordoba.com/api/qordoba/github/app/webhook/callback

**insert image here**

**Permissions**
  - Read-only
  - Repository metadata

**Read & write**

  - Repository contents
  - Issues
  - Pull requests
  - Commit statuses

**Subscribe to events**
  - Commit comment
  - Delete
  - Issues
  - Pull request
  - Create
  - Push
  - Pull request review comment
  
Here's an image you can use:

**insert image here**


Once the app is created; generate a Private Key for it by clicking "Generate a private key."

Then in [http://app.qordoba.com](http://app.qordoba.com) during the first "GitHub Enterprise Apps" workflow create, you will be prompted for the below values

**insert image here**


The Redirect Url for Installation is of the form:

https://[[host]]/organizations/[[Org Name]]/settings/apps/[[App Name]]/installations



