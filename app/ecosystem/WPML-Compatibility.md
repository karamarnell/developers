---
id: page-plugin
title: Compatibility with the WPML API
header_title: Compatibility with the WPML API
header_icon: /assets/images/icons/plugins/ee-request-transformer.png
breadcrumbs:
  Plugins: /plugins
nav:
  - label: Getting Started
    items:
      - label: Requesting Access
---
The WordPress multilingual plugin WPML has been created far before Polylang and thus some plugins and themes have been written to play nicely with it. Polylang does support most of the [WPML API](http://wpml.org/documentation/support/wpml-coding-api/) to avoid double work for themes and plugins author.

###icl_get_home_url

**Polylang equivalent**: pll_home_url

Link to the home page in the active language.
**Usage**:

```
icl_get_home_url();
```

### icl_get_languages

**Polylang equivalent**: none

Used for building custom language selectors

**Usage**:
```
icl_get_languages($args);
```

$args is an optional array parameter. Options are:

  * ‘orderby’ => ‘slug’, ‘name’ or ‘id’ (default: ‘id’)
  * ‘order’ => ‘DESC’ or ‘ASC’ (default: ‘ASC’)
  * ‘skip_missing’ => 0 or 1 (default: 0)
  * link_empty_to => works in conjunction with skip_missing=0 and allows using custom links for the languages that do not have translations for the current element. {$lang} can be used as placeholder for the language code (default: empty)

###icl_link_to_element

**Polylang equivalent**: none

used for creating language dependent links

**Usage**:
```
1 icl_link_to_element($id, $type, $text, $args, $anchor);
```

  * $id => (required) the ID of the post, page, tag or category to link to
  * $type => (optional) the type of page to link to. Can be ‘post’, ‘page’, ‘tag’ or ‘category’. (default: ‘post’)
  * $text => (optional) the link text. If not specified, the name of the element will be used.
  * $args => (optional) arguments for the link. When used, this should be a PHP array
  * $anchor => (optional) anchor for the link

### title": "icl_object_id"

**Polylang equivalent**: pll_get_post and pll_get_term

returns the tranlation id of an object

**Usage**:

```
icl_object_id($id, $type, $return_original_if_missing, $lang);
```

  * $id => (required) the ID of the post, page, tag or category
  * $type => (required) ‘post’, ‘page’, post_tag’ or ‘category’.
  * $return_original_if_missing => (required) true if Polylang should return the ID of the original language element if the translation is missing or false if Polylang should return a NULL if translation is missing
  * $lang => (optional) if set, forces the language of the returned object and can be different than the displayed language

### icl_register_string"

**Polylang equivalent**: pll_register_string

Allows plugins to add their own strings in the “strings translation” panel. Unlike pll_register_string, icl_register_string stores the string in the database (as the WPML original function does).

**Usage**:

```
icl_register_string($context, $name, $string);
```

  * $context => (required) the name of the plugin
  * $name => (required) the name of the string
  * $string => (required) the string that needs to be translated

### icl_unregister_string"

**Polylang equivalent**: none

Removes a string from the database

**Usage**:

```
icl_unregister_string($context, $name);
```

  * $context => (required) the name of the plugin
  * $name => (required) the name of the string

### icl_t

**Polylang equivalent**: pll__

get the translated string

**Usage**:
```
icl_t($context, $name, $string);
```
  * $context => (required) the name of the plugin
  * $name => (required) the name of the string
  * $string => (required) the string that needs to be translated
