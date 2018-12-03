---
id: page-plugin
title: The WPML language configuration file
header_title: The WPML language configuration file
header_icon: /assets/images/icons/plugins/ee-request-transformer.png
breadcrumbs:
  Plugins: /plugins
nav:
  - label: Getting Started
    items:
      - label: Requesting Access
---
The WordPress multilingual plugin WPML has been created far before Polylang and thus some plugins and themes have been written to play nicely with it. Polylang does support the WPML language configuration file wpml-config.xml to avoid double work for themes and plugins author.

Here is an example which is pretty much self-explanatory:


```
<wpml-config>
    <custom-fields>
        <custom-field action="copy">quantity</custom-field>
        <custom-field action="translate">custom-title</custom-field>
    </custom-fields>
    <custom-types>
        <custom-type translate="1">book</custom-type>
        <custom-type translate="1">DVD</custom-type>
    </custom-types>
    <taxonomies>
        <taxonomy translate="1">genre</taxonomy>
    </taxonomies>
    <admin-texts>
        <key name="my_plugins_options">
            <key name="option_name_1" />
            <key name="option_name_2" />
            <key name="options_group_1">
                <key name="sub_option_name_11" />
                <key name="sub_option_name_12" />
            </key>
        </key>
        <key name="simple_string_option" />
    </admin-texts>
</wpml-config>
```

**custom-fields:** the custom field name needs to be provided and also the action that Polylang is expected to take:

* “ignore”: no action from Polylang
* “translate”: the custom field is copied from the source post but may be modified
* “copy”: the custom field is copied from the source post and synchronized across translations

**custom-types:** the custom post types that Polylang should translate

**taxonomies:** the custom taxonomies that Polylang should translate

**admin-texts:** When themes and plugins use ‘get_option’, Polylang can filter these calls and provide translation to the values of these options. To translate a single option, add a key entry under admin-texts (as simple_string_option in the example above). To translate a serialized array, add several keys under a key, (as in my_plugin_options in the example above.

Polylang does not support the <language-switcher-settings> section.

The file wpml-config.xml must be placed in the root directory of the plugin or theme. It is also possible for users to create their own wpml-config.xml file and to upload it in /wp-content/polylang/ (create the directory if it does not exist).
