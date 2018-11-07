---
id: page-plugin
title: How to switch from WPML to Polylang?
header_title: How to switch from WPML to Polylang?
header_icon: /assets/images/icons/plugins/ee-request-transformer.png
breadcrumbs:
  Plugins: /plugins
nav:
  - label: Getting Started
    items:
      - label: Requesting Access
---
Use Qordoba's plugin to switch from WPML to Polylang. This plugin automates the conversion. It imports languages, all posts and terms languages as well as translations, strings translations, multilingual nav menus and also WPML options (when they have their counterpart in Polylang)

## How to proceed?

Important: Although WPML data should not be corrupted, as Polylang data are created without deleting anything, make a database backup before proceeding.

* De-activate WPML
* Download and activate Polylang and WPML to Polylang. Do not create any language with Polylang.
* Go in Tools -> WPML Importer
* If all checks pass, click on ‘Import’
* De-activate the plugin WPML to Polylang (you can even delete it)
* Check that everything is OK

If something went wrong and you want to revert to WPML, you can delete Polylang using the red link in Plugins table (it will delete all data created for Polylang) and then re-activate WPML

This plugin is still experimental and does not include error management.
