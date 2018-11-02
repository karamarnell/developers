---
id: page-plugin
title: Qordoba - JavaScript i18n SDK
header_title: Qordoba - JavaScript i18n SDK
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
To populate your Qordoba account with your project content, paste the following code into the page you want to track inside the `<head>` and `</head>` tags, before the first section. Change `site-key` to—you guessed it—your site key. You can find your key in the Settings tab in the [Qordoba](https://app.qordoba.com/) web application.
```
<script type="text/javascript">
  document.write("<scrip"+"t src=\"//qcdn.qordoba.com/qordoba-	latest.min.js\"></scrip"+"t><scrip"+"t src=\"https://storaged.qordoba.com/sdk-settings-<site-key>.js?cachebust="+Math.random()+"\"></scrip"+"t>")
</script>

```
The SDK works with all major frontend frameworks, including Angular and Backbone.
