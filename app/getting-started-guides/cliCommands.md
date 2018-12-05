---
title: CLI Commands
---

# Commands-Options

The following options work with ```qor``` (qordoba) and any other command on this page.

```
$ qor --help
usage: qordoba [-h] {init,status,pull,push,ls,delete} ...

$ qor init --help
usage: qordoba init [-h] --organization-id ORGANIZATION_ID
                                   --access-token ACCESS_TOKEN
                                   [--project-id PROJECT_ID]
                                   [--file-format {YAMLi18n,androidXML,macStrings}]
                                   [--traceback] [--debug] [--force]

positional arguments:
  {init,status,pull,push,ls,delete}
                       
    init                creates a basic configuration page.
    status              displays the status of localization work on the current project.             
    pull                Use the pull command to download locale files from the project.
    push                Use the push command to upload your local files to the project.
    ls									lists remote 
    delete              will not delete resources or languages that contain translations. To force the deletion, use the `-f`` option.

optional arguments:
  -h, --help            show this help message and exit.
  --traceback           full tracebacks on errors from running a command.
  --debug               enables debug messages for any command. 

```

##Push

Use the push command to upload your local files to the project identified by project_id, matching the files de.yml and en.yml in the config/locales folder:

``` 
**push--subparser**

qor push
Push all local source files to the Qordoba project. 

*files
	(Optional). Lists the file paths to upload.
--update
	(Optional). Updates an existing file.
--version
	(Optional). Sets the version tag. Updates the file with version tag. Uploads a  file with the version tag.
  
--file-path pushs entire (relative) file paths. Please review the commands documentation further down.
```

```
**.qordoba.yml**

push:
  sources:
    - "./source/*.json" push only json sources
    - "./source/english.json"  push single json sources
    - "./source/*" push sources in folder and subfolders
    
```

## Pull

Downloads translations for registered source files.

``` 
**pull -- subparser**

-w --workflow               allow to download not completed translations. Will ask for feedback on workflowstep. By default - download only completed translations.
-l --languages              Option to work only on specific (comma-separated) languages. example: `qor pull -l en-us, de-de`
-f --force                  force to update local files by remote translations. Do not ask approval.
--skip                      skip downloading if file exists. (default: False)
--replace                   replace existing file. (default: False)
--set-new                   ask to set new filename if file exists. (default: False)
--bulk                      pulls translated files in bulk, including the source language. Will automatically create a directory 'bulk_download'.
-w --workflow               pulles files from specific workflow step/milestones. Opens a diaglog for each file.
--workflow-all              pull all files from given workflowstep. workflowstep name is required. e.g. `--workflow-all "review"`
--custom                    pull files and change their extension naming. custom extension defined within the config file.
--distinct                  pull specific files, defined in your config
--file-path-patterns        pull filepaths into local folder structure
```
Project files will be pulled file by file. The following options are available:

```
**.qordoba.yml**

pull:
  targets:
    - "<filename>.<extension>" pulls all files into same dir
    - "<language_name>/<filename>.<extension>" pulls all files into a dir called "english"
    - "partials/<filename>.po" use with --custom.
    - "topics/qorodoba.json" use with --distinct. pulls the file qorodoba.json, creates a folder named "topics"

```

Available params in pattern:

```<language_code>``` - en-us
```<language_lang_code>``` - en
```<language_name>``` - english
```<language_name_cap>``` - English
```<language_name_allcap>``` - ENGLISH
```<local_capitalized>``` - US (as off version 1.5.5)

Default pattern for pull:

```<language_code><filename>.<extension>```


Examples:

```
i18n/<language_code>/translations.json  ->  i18n/zh-cn/translations.json
folder1/values-<language_lang_code>/strings.xml  ->  folder1/values-en/strings.xml
config/locales/server.<language_code>.yml  ->  config/locales/server.fr-fr.yml
folder2/<language_name>/strings.xml  ->  folder2/Chinese/strings.xml
folder3/strings.<language_name_cap>  ->  folder3/strings.French
<language_name_allcap>.locale  ->  FRENCH.locale

```

## iOS project specifics

Due to Apples naming convention for iOS we have implemented an additional feature.
By configuring config pull as the bottom example, the exception folder names will be pulled with new names: zh-Hans, zh-Hant, pt-BR, zh-CN (before: zh-chs, zh-cht, pt-br, zh-cn)

```
***.qordoba.yml for iOS strings files***

qordoba: 
  access_token: 
  organization_id: 1234
  project_id: 12321
  push:
    sources:
    - "./*.Strings"
  pull:
    targets:
    - "./<language_lang_code>.lproj/<filename>.<extension>"
```
