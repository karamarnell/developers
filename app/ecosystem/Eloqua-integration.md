---
id: page-plugin
title: Plugins - OpenID Connect
header_title: OpenID Connect
header_icon: /assets/images/icons/plugins/ee-openid-connect.png
breadcrumbs:
  Plugins: /plugins
nav:
  - label: Getting Started
    items:
      - label: Requesting Access
---

Make your Eloqua marketing campaigns truly multilingual with Qordoba's Eloqua plugin. This plugin is added as a Chrome extension, and can be used to send and receive content with Qordoba, all from within Eloqua's UI.


# Installation


To get the plugin, contact Customer Success (support@qordoba.com) with a request to receive the plugin. Once you receive the plugin:

1. Unzip the Eloqua plugin .zip file.

2. Visit chrome://extensions/ to install the plugin.

3. Click on "Load Unpacked", which will create a popup to select your desired file.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c463820-Screen_Shot_2018-09-19_at_3.45.47_PM.png",
        "Screen Shot 2018-09-19 at 3.45.47 PM.png",
        1684,
        1140,
        "#e2e7f1"
      ]
    }
  ]
}
[/block]
4. Select the unzipped Eloqua folder.

5. The plugin should now be installed. You will know it installed correctly if you see a Qordoba logo in your extensions area of the Chrome top navbar.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f144dc3-Screen_Shot_2018-09-19_at_3.46.04_PM.png",
        "Screen Shot 2018-09-19 at 3.46.04 PM.png",
        1696,
        980,
        "#e0e5f1"
      ]
    }
  ]
}
[/block]
# Configuration

Once the plugin is installed, you will need to configure all pertinent information to allow Qordoba to sync with your Eloqua environment.

1. Right click on the Qordoba extension, and select "Options" from the resulting menu that appears. This will take you to the login/config page of the plugin.

2. Fill in all fields.
  * Your email and password are the email and password you used when you joined Qordoba.
  * To get Workspace ID, Organization ID, and Account Token, visit your workspace in app.qordoba.com. Once there, go to the settings tab (1), click on CLI Config (2), and collect the values (3).
  * To get your Eloqua information, use your Eloqua username, password, and company name. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/aea17d5-Screen_Shot_2018-09-19_at_3.41.38_PM.png",
        "Screen Shot 2018-09-19 at 3.41.38 PM.png",
        1564,
        1282,
        "#e9e8ec"
      ]
    }
  ]
}
[/block]
When you have filled in all of the fields, click "Test Connection" to make sure all fields are filled in accurately. If done correctly, you should see a green "Connected Successfully!" notification. Click "Save Preferences" when done, and close the page.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/81dc8ea-Screen_Shot_2018-09-19_at_3.54.11_PM.png",
        "Screen Shot 2018-09-19 at 3.54.11 PM.png",
        1372,
        1656,
        "#f4f5ec"
      ]
    }
  ]
}
[/block]
# Using the Plugin

Now that the plugin is installed and configured, you are able to use Qordoba to localize content in Eloqua.

1. Go to the draft page of the content that you wish to send to Qordoba.

2. Left click on the Qordoba plugin in your Chrome navbar (1). You should see a new button added to the page's UI above the email template (2). 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/bc7cc4c-Screen_Shot_2018-09-19_at_4.06.38_PM.png",
        "Screen Shot 2018-09-19 at 4.06.38 PM.png",
        3360,
        1156,
        "#d2d2d1"
      ]
    }
  ]
}
[/block]
Click the new button to pull up the Qordoba plugin. Here, you can send the current content to Qordoba by clicking "Create translation Request" (1). You can also download any completed content, by selecting the desired languages (2), and then clicking "Create content translation" (3). To figure out what content has been completed, and what is still in progress, check the Translation Status column (4).
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1aa1fea-Screen_Shot_2018-09-19_at_4.10.02_PM.png",
        "Screen Shot 2018-09-19 at 4.10.02 PM.png",
        1362,
        1704,
        "#d0d5d9"
      ]
    }
  ]
}
[/block]
And that's it! When the content is pulled back to Eloqua, we persist the styling and structure of your content, but replace the english strings with translated values.

If you have any questions, concerns, or suggestions for our plugin, don't hesitate to reach out to support@qordoba.com!
