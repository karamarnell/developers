---
id: page-plugin
title: WPML to Polylang
header_title: WPML to Polylang
header_icon: /assets/images/icons/plugins/ee-request-transformer.png
breadcrumbs:
  Plugins: /plugins
nav:
  - label: Getting Started
    items:
      - label: Requesting Access
---
## FEATURES

* Imports languages and WPML options (when the same options exist in Polylang)
* Imports posts and terms languages as well as translations (including for custom post types and * custom taxonomies)
* Imports multilingual nav menus
* Imports strings translations
* Does not delete WPML data

```
Although WPML data should not be corrupted, as Polylang data are created without deleting anything, make a database backup before proceeding.
```

## HOW TO PROCEED?

* De-activate WPML
* Activate Polylang and WPML to Polylang. Do not create any language with Polylang.
* Go in Tools -> WPML Importer
* If all checks pass, click on ‘Import’
* De-activate WPML to Polylang (you can even delete it)
* Setup a language switcher either as a widget or in nav menus
* Check that everything is OK
* If something went wrong and you want to revert to WPML, you can delete Polylang using the red link in Plugins table (You can delete all data created for Polylang by checking the relevant option in Settings > Languages> Settings > Tools before deleting Polylang) and then re-activate WPML

This plugin is still experimental and does not include error management.
