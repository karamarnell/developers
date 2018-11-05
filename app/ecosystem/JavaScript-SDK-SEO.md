---
id: page-plugin
title: Qordoba - JavaScript SDK SEO
header_title: Qordoba - JavaScript SDK SEO
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
We are often asked about the impact of the JavaScript SDK on SEO. Thankfully, the good folks at Google have over the past couple of years done great work on updating their crawling and indexing technology to keep up with with the explosion of AJAX on the web. As a result, the localized pages you create with the Qordoba JavaScript SDK solution are fully indexed and ranked by Google, as is other JavaScript that you may have on your website. The Google crawler will see your local sites the same way your users do, by rendering your localized content as the spiders crawl your website.

Here are a few things you should do to optimize your localized websites for SEO:

### Assign a unique URL to each localized page
The search engines need a unique URL for each localized version of a page on your website. If your website is in 7 languages, each page on your site should have 7 unique URLs.

You can set up your localized sites to be accessed via a subdirectory or subdomain to your existing site and infrastructure, or via a country-code top-level domain:
* Subdirectories: `yoursite.com/es`, `yoursite.com/fr`
* Subdomains: `es.yoursite.com`, `fr.yoursite.com`
* Country-code top-level domains: `yoursite.es`, `yoursite.fr`

### Link to the translated version of your pages
In order for search engines to find the localized version of your pages, you must link to them in your HTML. The brute-force approach to getting the localized websites indexed is by using your site’s sitemap to add your localized URLs. Pages that are not linked to anywhere may be crawled in this fashion.

### Localize the title, description and keyword content for each localized URL
The SDK will by default pull in SEO content into the SEO module in the [Qordoba](https://app.qordoba.com/) web application, where your team can submit and iterate on the key SEO markers by market and page. Along with producing well-localized content, this is the best way to achieve high marks in-country for your website.

### Pre-render your website for those non-Google search engines
Depending on the markets you are targeting, search engines other than Google may play a role in determining your SEO strategy. Baidu, for example, does not render JavaScript as Google does, and thus, you'll want to serve up your JavaScript (both Qordoba's and others you have on your site) as HTML. Products like prerender.io create static HTML out of a JavaScript page which these engines can crawl. Remember that Google penalizes sites that seem to be offering up different content to crawlers than to users, so you will want the pre-rendered HTML, whether for the localized sites or for your core language site, to be part of a comprehensive strategy of [progressive enhancement](https://en.wikipedia.org/wiki/Progressive_enhancement) for optimal SEO.

Prerender.io makes a great open source tool for creating static HTML out of JavaScript. You can fork it from our [GitHub developers' site](https://github.com/Qordobacode/prerender)

One last thing to note: though Google has deprecated its [AJAX recommendation](https://developers.google.com/webmasters/ajax-crawling/docs/getting-started), Google still continues to support this directive, and the Qordoba SDK implements the recommendations on your localized pages.

### Resources
To learn more about how Google crawls your JavaScript website, please see below for a couple of launch points:
*  [Google Webmaster Blog re AJAX](https://webmasters.googleblog.com/2015/10/deprecating-our-ajax-crawling-scheme.html)
* [We Tested How Googlebot Crawls Javascript And Here’s What We Learned](http://searchengineland.com/tested-googlebot-crawls-javascript-heres-learned-220157)
