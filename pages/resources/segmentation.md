---
title: Segmentation 
header_icon: /assets/images/icons/icn-documentation.svg
header_title: Segmentation
breadcrumbs:
  Resources: /resources
---

# Cell-based (default)

Coming soon



# Punctuation-based

Coming soon

# ICU MessageFormat

Qordoba can parse your resource file’s strings as ICU MessageFormat strings. Using this string formatting impacts how strings are created in your project. Captured strings are prepared and optimized for translation in the Qordoba content editor.

When translating ICU MessageFormat strings translators and editors are not required to understand ICU MessageFormat syntax. They are presented with normalized strings that are segmented and use placeholders (tags) as needed, making them easily translatable.

####Mapping ICU MessageFormat Features to Qordoba Strings

|ICU Feature|	Qordoba support|
|--|--|
|String without arguments|Plain string without placeholders|
|String with arguments | String with placeholders |
|String with a single select argument|Multiple source strings; one source string for each option of the select.|
|String with a single plural argument|Qordoba Plural string|
|String with multiple nested arguments (limit of one plural)|Limited to creating up to 20 strings, otherwise unsupported and captured as raw text|
|String with choice argument|Multiple source strings; one source string for each option of the select.|
|String with multiple plural arguments|Qordoba Plural string|
|String with plural argument and offset property| String with placeholders|
|String with **selectordinal** argument| String with placeholders|

####In the following table, we show the value of an example source string and the corresponding string captured in Qordoba.

| Hello world. | Hello world.| 
| -- | --| 
| Current temperature {temp}. | Current temperature {0}.| 
| Please confirm this is your date of birth: {dob, date}. |  Please confirm this is your date of birth: {0}.| 
| You chose {selector, select, 1 {Option 1} other {an unsupported option.}}|    You chose Option 1  <br/>You chose an unsupported option.| 
| Your playlist has {items, plural, one {# album.} other {# albums.}}|   Plural Other: Your playlist has {0} albums. <br/> Plural One: Your playlist has {0} album.| 


# How I can chnage my Segmentation type

Coming soon


