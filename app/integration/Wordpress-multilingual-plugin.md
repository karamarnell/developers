---
id: page-plugin
title: Wordpress multilingual plugin
header_title: Wordpress multilingual plugin
header_icon: /assets/images/icons/plugins/ee-request-transformer.png
breadcrumbs:
  Plugins: /plugins
nav:
  - label: Getting Started
    items:
      - label: Requesting Access
---

Qordoba plugin integrated with Polylang to offer a simple way to make your WordPress site truly multilingual. Manage all your multilingual content on the same site. No need to have a different site for each language!

### Features

1. You can translate posts, pages, media, categories, post tags, menus, widgets.
2. Custom post types, custom taxonomies, sticky posts and post formats, RSS feeds and all default WordPress widgets are supported.
3. The language is either set by the content or by the language code in the URL, or you can use one different subdomain or domain per language.
4. Categories, post tags as well as some other metal are automatically copied when adding a new post or page translation.
5. A customizable language switcher is provided as a widget or in the navigation menu.
6. The admin interface is, of course, multilingual too and each user can set the WordPress admin language in its profile.
7. Choose Qordoba strings project and workflows to handle your content.

### Installation

1. Make sure you have [Polylang](https://wordpress.org/plugins/polylang/) installed as it provides the framework for the Qordoba plugin.
2. Upload the Qordoba plugin folder to the /wp-content/plugins/ directory.
3. Activate the Qordoba plugin through the **Plugins** menu in WordPress.
4. Navigate to the Translation menu that appears in your admin menu.
5. From here you can connect to an existing Qordoba project.

```
The plugin can be installed through Wordpress plugin installer by uploading plugin package.
```

### Configuration

There is plugin configuration page under Languages > Qordoba (if Polylang is installed) or Settings > Qordoba (if Polylang is not installed). Several options must be configured to make synchronization work.

### Authentication

In this version, authentication is done through login/password. Authentication by the token is not supported yet. Fill in Qordoba login and password into corresponding fields.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/923bed9-Screenshot_2017-08-01_15.53.48.png",
        "Screenshot 2017-08-01 15.53.48.png",
        1206,
        554,
        "#f3f3f3"
      ]
    }
  ]
}
[/block]

### Language mapping

Languages in Polylang are identified by slugs (like en, es, de), while languages in Qordoba are identified by numeric IDs and locales (en_US, de_DE and so on). To make synchronization work, the languages must be mapped in settings:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/360e897-Screenshot_2017-08-01_15.55.09.png",
        "Screenshot 2017-08-01 15.55.09.png",
        1080,
        256,
        "#f1f2f2"
      ]
    }
  ]
}
[/block]
Left-hand side displays languages, configured in Polylang. Dropdown lists display languages, configured in Qordoba Project. At least Qordoba Project source language must be configured to allow sending content to Qordoba. Translation languages should be mapped as well for saving translations in Wordpress.

When a new project is configured, the plugin will automatically load all project languages and will attempt to suggest language mapping. The language mapping will not be saved at this point and there will be the notification that you need to save settings.

### Cron schedule

Specify how often plugin should automatically communicate with Qordoba to attempt downloading new translations. Please note: this is not the system Cron, so the schedule is not guaranteed. The process is triggered when someone is visiting the website. For more information on Wordpress' cron functionality, please visit: https://codex.wordpress.org/Function_Reference/wp_cron

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b428a22-Screenshot_2017-08-01_15.56.17.png",
        "Screenshot 2017-08-01 15.56.17.png",
        1202,
        190,
        "#f2f2f2"
      ]
    }
  ]
}
[/block]

## Custom fields
Here you can select which fields will be sent to Qordoba for translation. All existing fields will be listed here. All checked fields will be sent to Qordoba for translations and saved when new translations are downloaded

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/32b788b-Screenshot_2017-08-01_15.56.23.png",
        "Screenshot 2017-08-01 15.56.23.png",
        988,
        368,
        "#f2f2f2"
      ]
    }
  ]
}
[/block]

## Send/Download multiple translations
In this section, you can send/receive multiple translations with one click. Each button explained below. If there is nothing to send or download - the corresponding buttons will be disabled.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d22ecc9-Screenshot_2017-08-01_15.57.28.png",
        "Screenshot 2017-08-01 15.57.28.png",
        1248,
        358,
        "#f3f3f3"
      ]
    }
  ]
}
[/block]

## Send Content
Send all new or pending posts to Qordoba. This button is useful when the plugin is installed on a website with existing content. Any content that was never sent to Qordoba is considered “New” and can be sent by clicking this button. Additionally, whenever you update a post or term without sending it to Qordoba, that post/term is automatically marked as “pending”

## Receive Content
Attempt to download translated posts/terms, which translations are not yet completed in Wordpress. This is determined by translation versions: if a source post has version 5, but there are translations with a version less than 5 - the posts will be scheduled for translation. Same applies for taxonomy terms.

## Translate Strings
Download translated site strings. Functionality for sending strings will be explained in sections below.

```
Important: please pay attention to date/time format strings. They may be different per language, but there is specific date/time format which should be followed: [http://php.net/manual/en/function.date.php ](http://php.net/manual/en/function.date.php)
```

### Manually send/receive translations using Qordoba Widget

The Qordoba Widget is automatically displayed when you edit a post or taxonomy term (assuming that post type or taxonomy configured as multilingual in Polylang settings). It provides the following functionality:
* Status information: displays latest version of the document, sent to Qordoba, and versions of downloaded translations. If a translation’s version is less than document version, there will be a notification that translation in specific version is outdated (the plugin will automatically try to download it with cron task). Also, the widget will let you know if plugin configuration is not finished or if the current post/term was updated since last time it was sent to Qordoba.
* Save&Send button saves current post/term and sends it to Qordoba for translation. This will automatically increment document version and all translations of the post/term will become outdated and queued for download.
* Download: attempts to download post/term translations. Will not automatically reload the page to avoid losing unsaved changes.

The widget is displayed on all languages of posts/terms and it does not matter which translation you are currently editing, as long as project source language is mapped and source content exists (otherwise you can’t send content to Qordoba). For instance, if there are 3 languages on the website, like English (source), Spanish and French, you can send/receive translations while editing any language version of the post.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b100354-Screenshot_2017-08-01_16.02.22.png",
        "Screenshot 2017-08-01 16.02.22.png",
        508,
        468,
        "#097eb2"
      ]
    }
  ]
}
[/block]

## Creating VS updating translation

When a new translation of a post/term is created (i.e. it did not exist previously), all custom fields (including Featured Image) are either copied from source or translated. However, when an existing translation is updated, only translated content is saved and no additional data is carried over (such as featured image or new categories), i.e. the plugin will not override your changes, that are not supposed to be translated.

## Translating Media files

Media files are translated in the same way as posts (assuming Media option is enabled in Polylang settings), except that Alt Text field is actually a custom field called _wp_attachment_image_alt which needs to be enabled in plugin options if you would like to translate the alternative text of images via Qordoba.
