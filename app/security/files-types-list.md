---
title: SOC 2 Compliance
header_icon: /assets/images/icons/icn-documentation.svg
header_title: SOC 2 Compliance
breadcrumbs:
  Security: /security
---


|Name|Extension|Key show in CE|Adding Key in CR|Delete Key|Edit Key|Edit source|Pluralization support|Segmentation support|Reference in CE (file comments)|DNM behavior|Send the comments back|GitHub support|Variables Rules|Content_type API Endpoint|Comment|Example file overview|
|--- |--- |--- |--- |--- |--- |--- |--- |--- |--- |--- |--- |--- |--- |--- |--- |--- |
|Android XML|.xml||show key|add key|delete key|edit|edit source|yes|||yes builtin, segments described as dnm are not imported into CE||extractcommit||xmlAndroid|AndroidXML support. This file format has as much in common with XML as extension. It is not generic XML reader (and will never be).||
|CSV|.csv||show key|n/a|||edit source||yes||ce based||extractcommit||csv|Classic RFC version of CSV||
|gettext / classic standard|.po||show key|not supported|||edit source|yes|non icu||ce based||extractcommit||PO|Gettext PO, Can't be used together with content_type=POKEY||
|Gettext template / classic standard|.pot||show key|not supported|||edit source|yes|non icu||ce based||extractcommit||POT|Gettext POT (PO template)||
|HTML|.htm, .html||||||edit source||yesbut icu don't have any sense||ce based||extractcommit||stringsHtml|Standard complaint HTML. Nonstandard stuff will be treated up to standard which may be surprising to customers.||
|iOS Strings File|.strings||show key|add key|delete key|edit|edit source|yes|yesIf using plurals non icu only||ce based||extractcommit||macStrings|iOS/OSX strings file||
|iOS Stringsdict|.stringsdict||show key||||edit source|yes|non icu||ce based||extractcommit||iosStringsDict|iOS/OSX strings dict file||
|Java Properties|.properties||show key|add key|||edit source||yes||ce based||extractcommit||propertiesJava|Java properties file (old version)||
|JSON|.json||show key|add key|delete key|edit|edit source||yes||ce based, if something is a number or boolean it's marked as dnm on ce||extractcommit||JSON|100% Standard JSON file format||
|Open Office XML|.docx, .xlsx||||||edit source||yesbut icu don't have any sense||ce based||||stringsDocxexcel|Microsoft Office file formats,||
|Po msgid as key|.po||show key|not supported|||edit source|yes|non icu||ce based||extractcommit||POKEY|Nonstandard PO file type where msgid contains key. Can't be used together with content_type=PO||
|SRT|srt||show key||||edit source||||ce based||extractcommit||SRT|||
|Text|.text.md||show key||||edit source||||ce based||||md|Markdown file format||
|Visual Studio|.resx||show key||||edit source||||ce based||extractcommit||stringsResx|Visual Studion Resx file format||
|XLIFF 1.2|.xliff, .xlf||show key||||edit source||yes||cd based||extractcommit||XLIFF1.2|Xliff 1.2 support, Can't be used with content_type=xliff||
|XLIFF 2.0|.xliff, .xlf||||||edit source||yes||cd based||||xliff|Xliff 2.0, Can't be used with content_type=XLIFF1.2Franzi: Is this again the rule, that either xliff or xliff1.2 can be added? Yes 👍||
|YAML|.yml,.yaml||show key|||edit|edit source||yes||ce based, if something is a number or boolean it's marked as dnm on ce||extractcommit||YAML|Standard Yaml 1.1, Can't be used with content_type=YAMLi18n||
|YAMLi18n|.yml,.yaml||show key|||edit|edit source||yes||ce based, if something is a number or boolean it's marked as dnm on ce||extractcommit||YAMLi18n|Yaml 1.1 where root node name is language code of the segments inside,If root node is not a language code it will behave as standard YAMLCan't be used with content_type=YAML||
||.properties||show key|add key|||edit source||yes||ce based||extractcommit||stringsI18nProperties|Random text file format from some frameworkBy accident compatible with new java 9+ properties files (AFAIK)Waseem AlShikh can you fill more here||
|||||||||||||||||||
