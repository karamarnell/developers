---
id: page-plugin
title: Qordoba - JavaScript i18n SDK Initialize
header_title: Qordoba - JavaScript i18n SDK Initialize
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
All the ways you can customize the JavaScript SDK to suit your needs. With no additional parameters to the basic installation, the SDK will save all text segments, images, CSS and SEO on all source pages to which the SDK is applied. You can customize this set up as outlined below. To add parameters list them below the siteKey in the SDK (and make sure you are using camelCase!)

# customDomain
[block:parameters]
{
  "data": {
    "h-0": "Parameter",
    "h-1": "Default",
    "h-2": "Accepts",
    "0-2": "String",
    "0-1": "null",
    "0-0": "customDomain"
  },
  "cols": 3,
  "rows": 1
}
[/block]
**What it does:** Use this parameter when you want to pull content from a domain that is different than the one provided when you created your project in Qordoba.

**Why use it:** Can be used to save content from URLs that are still in a staging environment, even if they do not match the project name in Qordoba (_i.e._, the production domain.) Should be used with projectDomain as shown below. Value should be the URL of the staging environment.
```
Qordoba.init({
            siteKey: '123.abc',
            customDomain: 'staging.yoursite.com',
            projectDomain: 'yoursite.com',
});
```
# liveSyncPages
[block:parameters]
{
  "data": {
    "h-0": "Parameter",
    "h-1": "Default",
    "h-2": "Accepts",
    "0-2": "Boolean",
    "0-1": "false",
    "0-0": "liveSyncPages"
  },
  "cols": 3,
  "rows": 1
}
[/block]
**What it does:** When set to false, content will only be pulled into your Qordoba project when the `force-collect=true` parameter is applied to the URL. Load the desired page while `force-collect=true` is included as a URL querystring parameter, and content will be sent to Qordoba.

If you'd like your content to be "automatically" collected every time the page is visited without having to include the `force-collect=true` querystring parameter, simply add `liveSyncPages: true` as a property on the `Qordoba.init` object in your SDK settings.

**Why use it:** This is a great customization for customers who want to create microsites of select content for different locales, rather than all pages :golf:. Content can be added as the project scope grows.

# liveEditor
[block:parameters]
{
  "data": {
    "h-0": "Parameter",
    "h-1": "Default",
    "h-2": "Accepts",
    "0-2": "Boolean",
    "0-1": "true",
    "0-0": "liveEditor"
  },
  "cols": 3,
  "rows": 1
}
[/block]
**What it does:** When set to true, will apply the design resources set from the visual Live Editor feature in the Qordoba web application. The default is that this is on, so that if one of your team members expands a text box so that the German word for "Company" can fit (Unternehmen), this will go live.

**Why use it:** You can turn off the Live Editor if you'd prefer to make the box longer via code instead of the visual Live Editor. Your team would still see the Live Editor in the Qordoba web application, but their changes there would not go live.

# blackList
**What it does:** A filter applied to DOM node collection results to ignore content whose node path contains a forbidden value.

**Why use it:** Determines CSS-like selectors (as well as elements nested inside them) that the Qordoba scraper should ignore. You can prevent scraping unneeded or unwanted content with this option. Customers who have injected third-party widgets or other code often end up with various content being generated that they don't want to be copied over to localized versions of the page. With this parameter, this pesky occurrence is banished. :hammer:

```
blackList:[
'[notranslate=true]',
'.gm-style',
'.twitter-video',
'#q-ext-root',
'.twitter-tweet',
'^script',
'^qwts',
'^style',
'^iframe',
'^svg',
'^canvas',
'^noscript',
'#comment$'
]	
```

# overrideCss
[block:parameters]
{
  "data": {
    "h-0": "Parameter",
    "h-1": "Default",
    "h-2": "Accepts",
    "0-0": "overrideCss",
    "0-1": "true",
    "0-2": "Boolean"
  },
  "cols": 3,
  "rows": 1
}
[/block]
**What it does:** When set to true, will add the CSS rules that were declared in the CSS settings of your project in the Qordoba web application.

**Why use it:** By default, you can add CSS rules in Qordoba to fix issues caused by language. You can do this by locale. If you don't want anyone to use this feature, you can set this parameter to false.

# projectDomain
[block:parameters]
{
  "data": {
    "h-0": "Parameter",
    "h-1": "Default",
    "h-2": "Accepts",
    "0-2": "String",
    "0-1": "null",
    "0-0": "projectDomain"
  },
  "cols": 3,
  "rows": 1
}
[/block]
**What it does:** Can be used in combination with customDomain to save and replace URLs that do not match the project name in Qordoba (_i.e._, the production domain).

**Why use it:** Can be used to save content from URLs that are still in a staging environment, even if they do not match the project name in Qordoba (_i.e._, the production domain). Should be used with customDomain above. Value should be the URL of the production domain.

```
Qordoba.init({
            siteKey: '123.abc',
            customDomain: 'staging.yoursite.com',
            projectDomain: 'yoursite.com',
});

```

# rewriteAbsoluteLinks
[block:parameters]
{
  "data": {
    "h-0": "Parameter",
    "h-1": "Default",
    "h-2": "Accepts",
    "0-0": "rewriteAbsoluteLinks",
    "0-1": "true",
    "0-2": "Boolean"
  },
  "cols": 3,
  "rows": 1
}
[/block]
**What it does:** When set to true, will rewrite all absolute "href" attributes on `<a>` tags that reference the project domain to link to their localized versions.

**Why use it:** The default behavior of the SDK is that all internal links in the pages where the SDK is applied are automatically changed to the localized versions. For example, if your German visitor is sent to the German homepage, whether by browser language detection, geolocation or manual switch, clicking to the blog from there will send her to the German blog. However, if you are using the SDK to create local content on only some pages, or only on parts of pages, then you wouldn't want your visitor to see `lang=de` in the blog URL even though it is in English. Whew.

# saveNewAttributes
[block:parameters]
{
  "data": {
    "h-0": "Parameter",
    "h-1": "Default",
    "h-2": "Accepts",
    "0-0": "saveNewAttributes",
    "0-1": "true",
    "0-2": "Boolean"
  },
  "cols": 3,
  "rows": 1
}
[/block]
**What it does:** When set to true, the SDK will detect and save new `<a>` "title" or `<input>` "placeholder" and "value" attributes on the page. When set to false, new attributes will not be saved.

**Why use it:** If you don't want to save attributes at all or want to prevent the SDK from saving new content, you can set this property to false.

# saveNewImages
[block:parameters]
{
  "data": {
    "h-0": "Parameter",
    "h-1": "Default",
    "h-2": "Accepts",
    "0-2": "Boolean",
    "0-1": "true",
    "0-0": "saveNewImages"
  },
  "cols": 3,
  "rows": 1
}
[/block]
**What it does:** When set to true, the SDK will detect and save new images on the page. When set to false, new images will not be saved.

**Why use it:** This is useful if you are using a third-party tool to manage images on your site (_i.e._, a PIM.)

# saveNewSegments
[block:parameters]
{
  "data": {
    "h-0": "Parameter",
    "h-1": "Default",
    "h-2": "Accepts",
    "0-2": "Boolean",
    "0-1": "true",
    "0-0": "saveNewSegments"
  },
  "cols": 3,
  "rows": 1
}
[/block]
**What it does:** When set to true, the SDK will detect and save text segments on the page. When set to false, segments will not be saved.

**Why use it:** If you don't want to save text segments at all or want to prevent the SDK from saving new segments, you can set this property to false.

# saveSeo
[block:parameters]
{
  "data": {
    "h-0": "Parameter",
    "h-1": "Default",
    "h-2": "Accepts",
    "0-2": "Boolean",
    "0-1": "true",
    "0-0": "saveSeo"
  },
  "cols": 3,
  "rows": 1
}
[/block]
**What it does:** When set to false, will not save any of the `title`, `meta`, `content`, and `description` values for your pages.

**Why use it:** We don't know. Don't you want more organic traffic?!? j/k. Maybe your marketing team decides to not pull in any of the SEO until they develop more strategy around global SEO.

# selectLastLanguage
[block:parameters]
{
  "data": {
    "h-0": "Parameter",
    "h-1": "Default",
    "h-2": "Accepts",
    "0-2": "Boolean",
    "0-1": "true",
    "0-0": "selectLastLanguage"
  },
  "cols": 3,
  "rows": 1
}
[/block]

[block:api-header]
{}
[/block]
**What it does:** When set to true, this parameter saves the language that was last visited by the user and serves the same language the next time she accesses the site.

**Why use it:** It's good karma to remember user preferences, but there may be reasons why you'd want to turn off this behavior and send a user to the main domain each time (_i.e._, a global landing page.)

# translateSegments
[block:parameters]
{
  "data": {
    "h-0": "Parameter",
    "h-1": "Default",
    "h-2": "Accepts",
    "0-2": "Boolean",
    "0-1": "true",
    "0-0": "translateSegments"
  },
  "cols": 3,
  "rows": 1
}
[/block]
**What it does:** When set to true, allows content published in Qordoba's web application to appear on your pages. If false, will not change any source content.

**Why use it:** This parameter is used by customers who want to review a project's content in staging or test environments before publishing to the production environment. To set up this workflow, the TranslateSegments parameter is kept as true in the staging environment, but false in the production environment, until all of the "Publish" actions in the Qordoba web application have been reviewed in staging.

# translateAttributes
[block:parameters]
{
  "data": {
    "h-0": "Parameter",
    "h-1": "Default",
    "h-2": "Accepts",
    "0-2": "Boolean",
    "0-1": "true",
    "0-0": "translateAttributes"
  },
  "cols": 3,
  "rows": 1
}
[/block]
**What it does:** When set to true, will replace all `<a>` "title" attributes and `<input>` "placeholder" and "value" attributes with the translations published from the Qordoba web application project. If set to false, original values will stay the same.

**Why use it:** This parameter can be used by customers who don't want to translate content attributes.

# translateImages
[block:parameters]
{
  "data": {
    "h-0": "Parameter",
    "h-1": "Default",
    "h-2": "Accepts",
    "0-2": "Boolean",
    "0-1": "true",
    "0-0": "translateImages"
  },
  "cols": 3,
  "rows": 1
}
[/block]
**What it does:** When set to true, will replace all images with the values published from the Qordoba web application project. If set to false, original images will stay the same.

**Why use it:** Admin users in your Qordoba project are able to swap out images for the localized pages, replacing an image of the Golden Gate bridge :bridge_at_night: with the Tokyo Tower :tokyo_tower:, for example. Customers who don't want anyone to change images, ever, will use this parameter to turn off this feature.

# translateSeo
[block:parameters]
{
  "data": {
    "h-2": "Accepts",
    "0-2": "Boolean",
    "h-1": "Default",
    "0-1": "true",
    "h-0": "Parameter",
    "0-0": "translateSeo"
  },
  "cols": 3,
  "rows": 1
}
[/block]
**What it does:** When set to true, will localize `<title>` and `<meta>` "content" and "description" for your pages based on the content for these fields in the Qordoba platform. If false, will leave as original source value.

**Why use it:** You may want to turn this off if you'd prefer to handle SEO for your pages differently (_e.g._, manually.)

# siteKey
[block:parameters]
{
  "data": {
    "h-2": "Accepts",
    "h-1": "Default",
    "h-0": "Parameter",
    "0-0": "siteKey",
    "0-1": "null",
    "0-2": "String"
  },
  "cols": 3,
  "rows": 1
}
[/block]
**What it does:** This required parameter determines which project in the Qordoba web application to associate with your website content.

**Why use it:** You'll need to include this in your SDK at all times.

# showLoaderWhenSwitchingLanguage
[block:parameters]
{
  "data": {
    "h-0": "Parameter",
    "h-1": "Default",
    "h-2": "Accepts",
    "0-2": "Boolean",
    "0-1": "false",
    "0-0": "showloaderwhenswitchinglanguage"
  },
  "cols": 3,
  "rows": 1
}
[/block]
**What it does:** When user changes a language, by default the page goes blank for a moment until the SDK gets translations (so it seems like page refresh.) For SPA that might not always be desired, so this option changes this behavior to show loader instead.

**Why use it:** If you want to prevent the page flashing, you can set this option to true, instead of blank page there will be a loader shown.

#loaderCustomHTML

loaderCustomHTML will allow to change you loader to whatever fits your style.
[block:parameters]
{
  "data": {
    "h-0": "Parameter",
    "h-1": "Default",
    "h-2": "Accepts",
    "0-0": "loaderCustomHTML:",
    "0-2": "HTML string"
  },
  "cols": 3,
  "rows": 1
}
[/block]
Example:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/76bbaf1-Screen_Shot_2017-06-28_at_2.10.49_PM.png",
        "Screen Shot 2017-06-28 at 2.10.49 PM.png",
        600,
        304,
        "#f9f9f8"
      ],
      "sizing": "80"
    }
  ]
}
[/block]
# pageNotFound
[block:parameters]
{
  "data": {
    "h-0": "Parameter",
    "h-1": "Default",
    "h-2": "Accepts",
    "0-0": "pageNotFound",
    "0-1": "null",
    "0-2": "String"
  },
  "cols": 3,
  "rows": 1
}
[/block]
**What it does:** Use this parameter to identify the absolute URL of the page you'd like to re-direct users to when a translated page cannot be found. If you'd like to serve a localized `/404` page, make sure you have a page in your project titled `/404` and that page is completed and published. You may then use our URL path mapping conventions to serve the localized page.

**Why use it:** Can be leveraged to help users effectively navigate your localized site.

#preferCanonicalUrls
[block:parameters]
{
  "data": {
    "0-0": "preferCanonicalUrls",
    "h-0": "Parameter",
    "h-1": "Default",
    "h-2": "Accepts",
    "0-1": "false",
    "0-2": "boolean"
  },
  "cols": 3,
  "rows": 1
}
[/block]
**What it does:** When set to `true`, this parameter forces Qordoba to use the canonical URL for the page instead of the URL in the address bar. 

**Why use it:** Some websites have multiple URL endpoints that all land on the same page, and each of these URL endpoints have the same canonical URL. If this parameter is `false`, Qordoba will re-collect the same page once for each URL endpoint. Since we only want one version of each page in Qordoba, we could set this parameter to `true`, and Qordoba would only collect one page for each canonical URL, regardless of what you see in the address bar.

#ignoreDomPath
[block:parameters]
{
  "data": {
    "h-0": "Parameter",
    "h-1": "Default",
    "h-2": "Accepts",
    "0-0": "ignoreDomPath",
    "0-1": "true",
    "0-2": "boolean"
  },
  "cols": 3,
  "rows": 1
}
[/block]
**What it does:** When we apply translations to a foreign language website, we use a number of factors to determine where on the page a given segment should be applied. One of these factors is "DOM path", which is the actual "location" of the segment on the page.

When set to "true", this parameter will tell Qordoba to ignore location and apply translations solely by looking for the "source" segment from Qordoba on the webpage.

**Why use it:** If you are planning to change the layout of your website but not the content and you want your translations to persist, you should change this to "true". That way, Qordoba will continue to translate the segments in the same way even though their location on the page has changed.

#collectDelay
[block:parameters]
{
  "data": {
    "h-0": "Parameter",
    "h-1": "Default",
    "h-2": "Accepts",
    "0-0": "collectDelay",
    "0-1": "3000",
    "0-2": "number"
  },
  "cols": 3,
  "rows": 1
}
[/block]
**What it does:** Delays the SDK running on your page for the number of milliseconds specified.

**Why use it:** If some of your page content takes a while to load, our SDK may run before all content is loaded. Use this parameter to introduce a delay and allow the content to fully load.
