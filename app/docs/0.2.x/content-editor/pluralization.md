---
title: Pluralization in Qordoba
---

# Pluralization in Qordoba: How to Leverage it

Pluralization is the act of expressing a noun in the plural form. Every language handles the plurals of nouns differently:
For example, in English, plurals of nouns are expressed as either “one” or “other.” However, in Polish, plurals of nouns are expressed as “one,” “few,” “many,” and “other.”

You can view a full list of language pluralization rules [here] (http://www.unicode.org/cldr/charts/29/supplemental/language_plural_rules.html).

You need pluralization whenever your app or software project has unit variables.

For example, if you are localizing your English-language app for a Polish audience, you will need to ensure that your unit variables respect Polish pluralization rules.

If you have a variable of “%d users,” you will need to make sure that this segment is translated as:


| English       | Polish        |
| ------------- |:-------------:| 
| user (one)    | użytkownik (one)| 
| users (others)| użytkowników (few)| 
|               | użytkowników (many)|   
|               | użytkownicy (other)|   


Qordoba supports native pluralization for the following file types:

  - POT
  - .PO
  - .JSON
  - .Strings (iOS)
  - .XML (Android)
  - csv 
  - POKEY
  - macStrings
  - iosStringsDict
  - propertiesJava
  - stringsI18nProperties
  - xliff
  - YAML
  - YAMLi18n
  - stringsResx
  
Keys that are pluralizable in the source file will be displayed in Qordoba with the 'Pluralization' format as seen below:

**insert image**

The number of required pluralization translations will depend on the target language. For example, in Korean, there are more than multiple translations for pluralization depending on the count as seen here: 

**insert image**

To translate for each count, click on the tab you want to translate and make any edits necessary.

**Additional Information:**

You will want to translate each tab and push each tab once the translation is complete. You do not have to push them all at once. For example, you can save the count 'one' and push the count 'two.'
The translated tabs that are in different stages of the workflow can be identified via filters as seen here:

Simply select the files you want to filter through and select your filter type.

**insert image here**

Pluralization works with and without variables.
