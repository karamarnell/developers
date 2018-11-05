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
_source_ page or _target_ page. If the SDK determines the URL is a _source_ page it will send page content to your project in Qordoba. If the SDK determines the URL is a _target_ page it will replace page content with the content developed in Qordoba for that locale.

# PathMap URLs
To set up your URL structure, you will ask the SDK to show localized content based on certain URL conditions. For example: Dear SDK, please save content to Qordoba when the URL is
`http://yoursite.com/language=en`; replace content with German content when the URL is
`http://yoursite.com/language=de`, and with Spanish content when the URL is
`http://yoursite.com/language=sp`

Configure these rules via the **pathMap** key, which is an array of key/value rules to declare when a URL is a _source_ language and when a localized version of the URL should be loaded.
[block:code]
{
  "codes": [
    {
      "code": "Qordoba.init({\n  .\n  .\n  .\n  path: \"yoursite.com/.*[&?]language=<lang>\", // RegExp string to define the format of the URL. For clarity use language and <lang> (not lang and <lang>).\n  source: \"english\", // Save content when <lang> is \"en\"\n  targets: [\n    {\n      code: \"de-de\",\n      val: \"german\" // Replace with \"de-de\" values when <lang> is \"de\"\n    },\n    {\n      code: \"sp-sp\",\n      val: \"spanish\" // Replace with \"sp-sp\" values when <lang> is \"sp\"\n    }\n  ]\n]);",
      "language": "javascript",
      "name": "example"
    }
  ]
}
[/block]
# PathMap subfolder/subdomain
If you are publishing content to subdomains or subfolders (_i.e._, `de.yoursite.com` or `yoursite.com/de/some-page`), your server must be configured to point target pages to their matching original source content. Although the URL will display `http://de.yoursite.com/some-page`, the content loaded will be drawn from `http://yoursite.com/some-page`, with the localized strings, images and CSS inserted on page load.

After configuring the server to always point to the original _source_ page configure a matching **pathMap**.
[block:code]
{
  "codes": [
    {
      "code": "path: \"yoursite.com<lang>.*\", // RegExp string to define the format of the URL.\nsource: \"\", // Leave blank to save content when there is no <lang> subfolder\ntargets: [\n    {\n        code: \"de-de\",\n        val: \"/german\" // Replace with \"de-de\" values when <lang> subfolder is \"german\"\n    },\n    {\n        code: \"sp-sp\",\n        val: \"/spanish\" // Replace with \"sp-sp\" values when <lang> subfolder is \"spanish\"\n    }\n]",
      "language": "javascript",
      "name": "example"
    }
  ]
}
[/block]
So, without being too pedantic, the **pathMap** above would have the following result:

Someone visits: `http://yoursite.com/de/some-page`
Action: Show German versions of source page

Someone visits: `http://yoursite.com/sp/some-page`
Action: Show Spanish versions of source page

# PathMap multiple mapping
As **pathMap** is an array, it can be configured to accept multiple URL maps for a site. The following **pathMap** configuration example will collect when the URL is `http://yoursite.com/some-page-en/some-article` _OR_ `http://yoursite.com/en/some-page` and replace on `http://yoursite.com/some-page-german/some-article` _OR_ `http://yoursite.com/german/some-page`
[block:code]
{
  "codes": [
    {
      "code": "[\n    {\n        path: \"yoursite.com/.*<lang>\", // RegExp string to define the format of the URL.\n        source: \"-en\", // Save content when <lang> is \"-en\"\n        targets: [\n            {\n                code: \"de-de\",\n                val: \"-german\" // Replace with \"de-de\" values when url contains \"-german\"\n            }\n        ]\n    },\n    {\n        path: \"yoursite.com/<lang>.*\", // RegExp string to define the format of the URL.\n        source: \"en/\", // Save content when <lang> is \"en/\"\n        targets: [\n            {\n                code: \"de-de\",\n                val: \"german/\" // Replace with \"de-de\" values when URL contains \"german/\"\n            }\n        ]\n    }\n]",
      "language": "javascript",
      "name": "example"
    }
  ]
}
[/block]
# Exclude page content
Remember that the Qordoba JavaScript SDK will save **all** content on your pages other than that with `notranslate` attributes in the HTML. The SDK will ignore all HTML nested within any tag with the `notranlate` attribute.

The SDK will also ignore the following tags by default: `<script> <noscript> <style> <iframe> <object> <path> <svg> <canvas>`

The SDK has filters to prevent content from Google Maps, Twitter, Facebook, and dynamic numbers from being saved to your Qordoba project, but using `notranslate` is recommended. Content _can_ be disabled from the Qordoba web application, but your product team might not be super happy about cleaning up thousands of strings. :cop:

# Manually disable SDK
For translated pages, you may occasionally want to disable the SDK to see the raw, untranslated content. To do so, just add `?q_sdk_disable_now` as a query parameter. Example: `www.demo.com/jp/aboutus.html?q_sdk_disable_now`
