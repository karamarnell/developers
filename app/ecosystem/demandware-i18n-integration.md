---
id: page-plugin
title: Plugins - LDAP Authentication
header_title: LDAP Authentication
header_icon: /assets/images/icons/plugins/ldap-authentication.png
breadcrumbs:
  Plugins: /plugins
---

1. Introduction
This document gives the Technical Specifications for the Qordoba Demandware Link cartridge as well
as the LINK implementation guide for setting up Qordoba on standard SiteGenesis 2.0.
The Cartridge allows you to use Qordoba to translate products, categories and content assets from
your Demandware catalogues.

2. Cartridge Installation
To install the Qordoba cartridge, go to Administration –> Sites –> Manage Sites –> Sites-Site -
Settings and add the cartridge `qordoba_integration` to the beginning of your cartridge path.
Be sure to also add the cartridge to the Business Manager cartridge path by selecting 'Manage
the Business Manager Site'.

System and Custom Object Extensions

There are several metadata files that need to be imported into the site for the integration to function
properly. Import the provided system object type extensions in file
“metadata/system-objecttype-extensions.xml” by navigating to Site Development/Import &
Export/Metadata
This will extend the SitePreferences object to include an attribute for the Qordoba configuration
preferences.
Upload the file from your local workspace via 'Upload', then select 'Import' and choose your newly
uploaded file.
Follow the same process for the file 'metadata/custom-objecttypedefinitions.xml'.

This file creates two new system object definitions:

1. QORDOBA_SUBMISSION – an object that stores the state of a translation submission. The
scheduled jobs will use this object to query, send, and update batch information.
2. QORDOBA_LOCALES – A custom object to store the relevant locales for this instance.
Custom Object Data
To populate the locales custom object, navigate to: Merchant Tools / Custom Objects / Import &
Export
Select 'upload' and choose the local file 'metadata/QORDOBA_LOCALES.xml' from the cartridge
installation package.
Once this file is imported, all the locales supported by Qordoba will be loaded into the
QORDOBA_LOCALE custom object definition.

Job Schedule Definitions

The Qordoba integration utilizes two scheduled jobs to send and receive batch communications to
the Qordoba platform. Import the provided definitions by navigating to: Administration / Operations /
Import & Export
Choose 'upload' and upload the provided schedule definition file 'metadata/schedules.xml'. After
uploading, choose 'Import' and select the newly uploaded file.
This will result in two job configurations that will be discussed in detail below.

Site Preferences

The integration comes with a seeded set of base configurations for integration with Qordoba. These
will need to be updated based on your integration specifics but are included here for ease of setup.
Navigate to Site Preferences / Custom Preferences / QORDOBA


In the Qordoba configuration, paste the following JSON:

{
"api_url" : "https://app.qordoba.com/api/" ,
"project_id" : "{your_project_id" ,
"api_key" : "{your_api_key}" ,
"time_out" : "4500" ,
"retrival_type" : "published" ,
"source_locale" : "default" ,
"auto_authorize_content" : "true" ,
"target_locale" : "{\"target_locale\": [{ \"demandware\":\"fr_FR\" , \"qordoba\":\"fr-FR\"
},{ \"demandware\":\"de_DE\" , \"qordoba\":\"de-DE\" }]}" ,
"product_attribute_json" : "{\"product_attribute\":[{ \"id\":\"name\" , \"type\":\"string\" ,
\"custom\":\"false\" },{ \"id\":\"shortDescription\" , \"type\":\"html\" ,
\"custom\":\"false\"},{ \"id\":\"longDescription\" , \"type\":\"html\" ,
\"custom\":\"false\"},{ \"id\":\"pageDescription\" , \"type\":\"string\" ,
\"custom\":\"false\"},{ \"id\":\"pageTitle\" , \"type\":\"string\" , \"custom\":\"false\"
},{\"id\":\"pageKeywords\" , \"type\":\"string\" , \"custom\":\"false\" }]}" ,
"content_attribute_json" : "{\"content_attribute\":[{ \"id\":\"name\" , \"type\":\"string\" ,
\"custom\":\"false\" },{ \"id\":\"description\" , \"type\":\"string\" , \"custom\":\"false\"
},{\"id\":\"pageDescription\" , \"type\":\"string\" , \"custom\":\"false\" },{
\"id\":\"pageTitle\" , \"type\":\"string\" , \"custom\":\"false\" },{ \"id\":\"pageKeywords\"
, \"type\":\"string\" , \"custom\":\"false\" },{ \"id\":\"body\" , \"type\":\"html\" ,
\"custom\":\"true\" }]}" ,
"category_attribute_json" : "{\"category_attribute\":[{ \"id\":\"displayName\" ,
\"type\":\"string\" , \"custom\":\"false\" },{ \"id\":\"description\" , \"type\":\"string\" ,
\"custom\":\"false\" },{\"id\":\"pageDescription\" , \"type\":\"string\" ,
\"custom\":\"false\" },{ \"id\":\"pageTitle\" , \"type\":\"string\" , \"custom\":\"false\" },{
\"id\":\"pageKeywords\" , \"type\":\"string\" , \"custom\":\"false\" }]}" ,
"catalog_ids" : "apparel-catalog, electronics-catalog"
}

3. External APIs List

Name
Endpoint
Response 
list languages
https://api.qordoba.com/v2/languages
{
  "languages": [
    {
      "id": 94,
      "name": "English - United States",
      "code": "en-us",
      "direction": "ltr",
      "override_order": "aaa - aaa - English - United States"
    },
    


list projects
https://api.qordoba.com/v2/projects/list
{
  projectCount: 999,
  projects [
    {
      "id": 000,
      "name": "Product Test",
	    "creator": "John Doe",
	    "created": 1485366552000,
	    "sourceCode": "en-us",
	    "sourceId": 94,
	    "status": 1
		},...
	]
}
show project status
https://api.qordoba.com/v2/projects/status
{
  "languages": [
    {
      "id": 234,
      "code": "es-es",
      "name": "Spanish - Spain",
      "segments": 285,
      "words": 1052,
      "total": 285,
      "total_words": 1052,
      "milestones": [
        {
          "id": -100,
          "name": "Completed",
          "order": 1000,
          "count": 76,
          "words_count": 258,
          "percent": 26.67
        },...
      ]
   ]
}


list files
https://api.qordoba.com/v2/files/list


[
  {
    "id": 000000,
    "fileId": 000000,
    "enabled": true,
    "completed": false,
    "fileName": "sample.json",
    "segmentCount": 2,
    "updated": 1485473148000,
    "preparing": false,
    "deleted": false,
    "versionTag": "0.0"
  },
  


upload file
https://api.qordoba.com/v2/files/upload
{
    "result": "success",
    "files_ids":[
      000000
    ]
  }
  
  export files
https://api.qordoba.com/v2/files/export
{
    "downloadLink": "https://app.qordoba.com/api/file/download?token=abc123def456&filename=sample.zip"
  }


update file
https://api.qordoba.com/v2/files/update
{
    "result": "success",
  }
 value by key
https://api.qordoba.com/v2/files/value_by_key
{
    "resultCount": 6,
    "sourceId": 94,
    "sourceCode": "en-us",
    "targetId": 124,
    "targetCode": "de-de",
    "segments":[
      {
        "segmentId": 00000000,
        "segment": "Cookie Cam!",
        "reference": null,
        "plurals": null,
        "translationId": 000000000,
        "translation": "Keks Kam!",
        "pluralRule": null,
        "order": null,
        "stringKey": ""
      },
    {"segmentId": 0000001, "segment": "sample.org", "reference": null,…},…
    ]
  }



4. Data Storage
Qordoba using two types of custom object for saving data:
● QORDOBA_SUBMISSION
● QORDOBA_LOCALES
