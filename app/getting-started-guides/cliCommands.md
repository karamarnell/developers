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

## push

Use the push command to upload your local files to the project identified by project_id, matching the files de.yml and en.yml in the config/locales folder:

**push--subparser**
``` 
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

**.qordoba.yml**

```
push:
  sources:
    - "./source/*.json" push only json sources
    - "./source/english.json"  push single json sources
    - "./source/*" push sources in folder and subfolders   
```

## pull

Downloads translations for registered source files.

**pull -- subparser**
``` 
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

**.qordoba.yml**
```
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

***.qordoba.yml for iOS strings files***
```
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

## delete 

Deletes any resource and its translations. Your user account must have admin privileges to run this command.

```

***delete --subparser***

`-f`   `--force`          Optional. Force deletion of the remote page and its translations. Do not ask for approval.
a filename or filenames    Required. The filename or filenames to delete. Use commas to separate multiple filenames. Do not specify the translated files.

`-l`                      Optional. Delete one or more translations. example `-l en, us`
```
For example:

**delete**
```
$ qor delete -l <file paths or file ids>
```

The client will not delete resources or languages that contain translations. To force the deletion, use the ```-f``` option.

**delete**

```$ qor delete -f <file paths or file ids>```


## Init

Creates a basic configuration file, ```.qordoba.yml```, in the current directory. This file is required for the client to connect to the server and synchronize files.

Execute the ```qor init``` command with the following option-value pairs from your project settings.

**init --subparser**
```
--project-id                  (Required) Save the *Project ID* to the configuration file.
--access-token                (Required) Save the *Account Token* to the configuration file.
--organization-id             (Required) Save the *Organization ID* to config file
--force                       (Optional) Recreate config file, overwriting the previous one.
```

Example:

**qor init**
```
$ qor init --organization-id 1234 --access-token 10c7f4cfrohzuseinbedarfeswenige2d --project-id 4422

-> Loading qordoba config...
-> Checking organization and project...
-> Config `/Users/Qordoba/localization/.qordoba.yml` successfully saved.
```

## add single key

To add a single key to a project, do as follows:

step 1: get file id

  ```qor addkey --filelist FILENAME```
  
**response**
```
  filename    version      page_id
  | ----------  ---------  ---------
  | test.json   3             988204
  | test.json   2             988200
  | test.json                 988197
```

step 2: add new key-value pair to file

 ```qor addkey --key [KEY] --value "[VALUE]" --fileid [FILEID]```
 
## status

Displays the status of localization work on the current project. It lists the resources initialized under the local project and their associated translation files.

use qor status --json if you want the output to be in json format instead of a table

**status**
```
$ qor status
-> Loading qordoba config...
+--------+--------+-----------+---------+--------------+-----------+
| LOCALE | #WORDS | #SEGMENTS | EDITING | PROOFREADING | COMPLETED |
+--------+--------+-----------+---------+--------------+-----------+
| ja-jp  | 94     | 32        | 0%      | 78.13%       | 21.88%    |
| es-es  | 94     | 32        | 100%    | 0%           | 0%        |
+--------+--------+-----------+---------+--------------+-----------+
```

**LOCALE:** The language code and country code separated by a dash. See Languages
**#WORDS:** The number of words per locale.
**#SEGMENTS:** The number of segments per locale
**TRANSLATION:** If proofreading is one of the steps in the project workflow, the percentage of work completed on the translation step.
**EDITING:** If proofreading is one of the steps in the project workflow, the percentage of editing work completed.
**PROOFREADING:** If proofreading is one of the steps in the project workflow, the percentage of proofreading work completed.
**COMPLETED:** The percentage of all project work completed.

## ls

Lists remote files.

**ls**
$ qor ls
```
-> Loading qordoba config...
+--------+-----------------+-----------+---------------------+---------+
| ID     | NAME            | #SEGMENTS | UPDATED_ON          | STATUS  |
+--------+-----------------+-----------+---------------------+---------+
| 728068 | runtime.yaml    | 6         | 2017-01-20 10:19:27 | Enabled |
| 725570 | TestFileMH.json | 26        | 2016-12-21 22:40:13 | Enabled |
+--------+-----------------+-----------+---------------------+---------+
```

### --help

 - Optional. Displays help for any command and option.
	- Example A: To display a list of commands, enter ```qordoba --help```, as shown here.

	- Example B: To display a list of options for any command, enter the command followed by ```--help```, as shown here.
	
### **--traceback**

	- Optional. Displays full tracebacks on exceptions/errors from running a command. Helps identify mistakes in resource files.
	- Example: ```$ qor init --organization-id 1234 --access-token 10c7f4cb7e1df2d817a0e9e28391ad9c6f22d``` --project-id 4321 --traceback`

### **--debug** 

	- Optional. Enables debug messages for any command.
	- Example: ```$ qor init --organization-id 1234 --access-token 10c7f4cb7e1df2d817a0e9e28391ad9c6f22d```

Generates a step-by-step report of the executed command. The report includes the contents of the files to be processed.

## File Path - push and pull (alpha)

## push entire file paths

```qor push --file-path``` uploads files and their relative path to Qordoba.

***necessary condition: your file path need to contain a language_code***

**filepath naming**

```
Make sure your file path contains one of the following source code patterns:

<language_code> - en-us

<language_lang_code> - en

<language_name> - english

<language_name_cap> - English

<language_name_allcap> - ENGLISH

<local_capitalized> - US (as off version 1.5.5)

Example:
"./folder/en/index.html"
"./folder/en-us.proj/index.html"
```

### pull file paths into same project

Pulling file paths smoothly back into your local folder structure has two requirements:

1. **configuration file:** Your configuration file must be in the exact same location as it was for the push command.

2. **file naming**: 

	Know the source code pattern.

	The pattern needs to be added as a flag ```--file-path-pattern``` to your pull command:

	<language_code> - en-us

	<language_lang_code> - en

	<language_name> - english

	<language_name_cap> - English

	<language_name_allcap> - ENGLISH

	<local_capitalized> - US

	Example:

	source file-path: "./folder/en/index.html"
	pattern: language_lang_code
	command: ```$ qor pull --file-path-pattern language_lang_code```

	the name of the source language will change accordingly

	Default:
	```qor pull --file-path-pattern default.```

