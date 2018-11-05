---
id: page-plugin
title: Qordoba - GitHub enterprise integration
header_title: Qordoba - GitHub enterprise integration
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

Qordoba - GitHub enterprise integration

----
Qordoba's GitHub Enterprise integration supports the same powerful integration available for repositories hosted on GitHub.com. 

### Endpoint URLs
All API endpoints except for the Management Console API endpoints are prefixed with the following:

```
http(s)://hostname/api/v3/
```

The Management Console API endpoints are only prefixed with a hostname:

```
http(s)://hostname/
```

### Authentication
Your Enterprise installation's API endpoints accept the same authentication methods as the GitHub.com API. Specifically, you can authenticate yourself with OAuth tokens (which can be created using the Authorizations API) when you access Qordoba.

```
Qordoba requires using "https://" and port 443 to access your Github Enterprise server.
```

### Create an OAuth application
All developers need to register their application before getting started. A registered **OAuth application** is assigned a unique Client ID and Client Secret. The Client Secret should not be shared. 

Go to your GitHub Enterprise installation, and start by registering a new Developer application. This can be done by going to your GitHub User Settings, clicking Applications on the left, then selecting Developer applications at the top:


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/88dba68-github-user-settings-6fa2b465f0ab95b777c20928032df074c74ea5c97f9a0c72191cbe43765a9a9c.png",
        "github-user-settings-6fa2b465f0ab95b777c20928032df074c74ea5c97f9a0c72191cbe43765a9a9c.png",
        602,
        652,
        "#e3e2e2"
      ]
    }
  ]
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/905589f-applications-menu-fdac6bf705123d29ecc70e13cff95a46d26bea84ea3477faf085fb16ce5a5811.png",
        "applications-menu-fdac6bf705123d29ecc70e13cff95a46d26bea84ea3477faf085fb16ce5a5811.png",
        686,
        314,
        "#e1e3e7"
      ]
    }
  ]
}
[/block]
From this page, click Register new application
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/057d292-register-application-button-3ca9b9a371a9b9febb4d0fcada6e8b4bb0e0262fcaa996bcd80af572e5d5b19b.png",
        "register-application-button-3ca9b9a371a9b9febb4d0fcada6e8b4bb0e0262fcaa996bcd80af572e5d5b19b.png",
        1137,
        174,
        "#f3f3f3"
      ]
    }
  ]
}
[/block]
Name

`Qordoba`

URL

`https://qordoba.com`

Callback URL

`https://app.qordoba.com/api`

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

Once filled out, click the Register application button at the bottom of the form.

Now that we've created an application, we have access to the Client ID and Client Secret. We'll need those to setup your GitHub Enterprise project on Qordoba.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6e69336-client-secrets-8e76c5470a71d9b6d56a34b9d3b5402a04a2e7916f383614e57ad92474a6c7a4_1.png",
        "client-secrets-8e76c5470a71d9b6d56a34b9d3b5402a04a2e7916f383614e57ad92474a6c7a4 (1).png",
        880,
        350,
        "#662828"
      ]
    }
  ]
}
[/block]
