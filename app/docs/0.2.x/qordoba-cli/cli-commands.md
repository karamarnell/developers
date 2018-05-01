---
title: Commands-Options
---

## Commands-Options

The following options work with `qor` (`qordoba`) and any other command on this page.

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

Untranslated local source files =. Use the `push` command to upload your local files to the project identified by `project_id`, matching the files `de.yml` and `en.yml` in the config/locales folder:

```
qor push
Push all local source files to the Qordoba project. 

*files
	(Optional). Lists the file paths to upload.
--update
	(Optional). Updates an existing file.
--version
	(Optional). Sets the version tag. Updates the file with version tag. Uploads a  file with the version tag.
  
--file-path (BETA) pushs entire (relative) file paths.
```

#### upload file paths
Same filenames - even though located in different folders - cannot be hosted without a version tag in a Qordoba project. In BETA we provide a (still) very simple functionality to solve this issue. 

`qor push --file-path` uploads files and their relative path to Qordoba. 

```
Make sure your file path contains one of the following source code patterns:

```<language_code>``` -  en-us
```<language_lang_code>``` -  en
```<language_name>``` - english
```<language_name_cap>``` -  English
```<language_name_allcap>``` - ENGLISH
```<local_capitalized>``` -  US (as off version 1.5.5)

Example:
"./folder/**en**/index.html"
"./folder/**en-us**.proj/index.html"
```

## pull

Downloads translations for registered source files.

```
-w --workflow               allow to download not completed translations. Will ask for feedback on workflowstep. By default - download only completed translations.
-l --languages              Option to work only on specific (comma-separated) languages. example: `qor -l ru,en`
-f --force                  force to update local files by remote translations. Do not ask approval.
--skip                      skip downloading if file exists. (default: False)
--replace                   replace existing file. (default: False)
--set-new                   ask to set new filename if file exists. (default: False)
--bulk                      pulls translated files in bulk, including the source language. Will automatically create a directory 'bulk_download'.
-w --workflow               pulles files from specific workflow step/milestones. Opens a diaglog for each file.
--workflow-all              pull all files from given workflowstep. workflowstep name is required. e.g. `--workflow-all review`
--custom                    pull files and change their extension naming. custom extension defined within the config file.
--distinct                  pull specific files, defined in your config
--file-path-patterns        (BETA) pull filepaths into local folder structure

```

*Available params in pattern:*

```<language_code>``` -  en-us
```<language_lang_code>``` -  en
```<language_name>``` - english
```<language_name_cap>``` -  English
```<language_name_allcap>``` - ENGLISH
```<local_capitalized>``` -  US (as off version 1.5.5)

*Default pattern for pull:*

`<language_code><filename>.<extension>`

#### Examples:
```
i18n/<language_code>/translations.json  ->  i18n/zh-cn/translations.json
folder1/values-<language_lang_code>/strings.xml  ->  folder1/values-en/strings.xml
config/locales/server.<language_code>.yml  ->  config/locales/server.fr-fr.yml
folder2/<language_name>/strings.xml  ->  folder2/Chinese/strings.xml
folder3/strings.<language_name_cap>  ->  folder3/strings.French
<language_name_allcap>.locale  ->  FRENCH.locale

```
#### pull file paths 



Pulling file paths smoothly back into your local folder structure has two requirements:


Know the source code pattern. 

The pattern needs to be added as a flag `--file-path-pattern` to your pull command:

```<language_code>``` -  en-us
```<language_lang_code>``` -  en
```<language_name>``` - english
```<language_name_cap>``` - English
```<language_name_allcap>``` - ENGLISH
```<local_capitalized>``` - US 

Example:

```
source file-path: "./folder/**en**/index.html"
pattern: language_lang_code
command: `$ qor pull --file-path-pattern language_lang_code`

*the name of the source language will change accordingly* 

```

Default:
`qor pull --file-path-pattern default`.


## delete
Deletes any resource and its translations. Your user account must have admin privileges to run this command.

```
`-f`   `--force`          Optional. Force deletion of the remote page and its translations. Do not ask for approval.
a filename or filenames    Required. The filename or filenames to delete. Use commas to separate multiple filenames. Do not specify the translated files.

`-l`                      Optional. Delete one or more translations. example `-l en, us`
```


The client will not delete resources or languages that contain translations. To force the deletion, use the `-f`` option.

```
$ qor delete -f <file paths or file ids>
```



## init
Creates a basic configuration file, `.qordoba.yml`, in the current directory. This file is required for the client to connect to the server and synchronize files.

 Execute the `qor init` command with the following option-value pairs from your project settings.

```
--project-id                  (Required) Save the *Project ID* to the configuration file.
--access-token                (Required) Save the *Account Token* to the configuration file.
--organization-id             (Required) Save the *Organization ID* to config file
--force                       (Optional) Recreate config file, overwriting the previous one.
```



## status

Displays the status of localization work on the current project. It lists the resources initialized under the local project and their associated translation files.

use  *qor status --json* if you want the output to be in json format instead of a table


* **LOCALE**: The language code and country code separated by a dash. See [Languages](language-resource-dev)
* **#WORDS**: The number of words per locale.
* **#SEGMENTS**: The number of segments per locale
* **TRANSLATION**: If proofreading is one of the steps in the project workflow, the percentage of work completed on the translation step.
* **EDITING**: If proofreading is one of the steps in the project workflow, the percentage of editing work completed.
* **PROOFREADING**: If proofreading is one of the steps in the project workflow, the percentage of proofreading work completed.
* **COMPLETED**: The percentage of all project work completed.



## ls

Lists remote files.


## --help
* Optional. Displays help for any command and option.
* Example A: To display a list of commands, enter `qordoba --help`, as shown here.

* Example B: To display a list of options for any command, enter the command followed by `--help`, as shown here.

## --traceback

* Optional. Displays full tracebacks on exceptions/errors from running a command. Helps identify mistakes in resource files.
* Example: `$ qor init --organization-id 1234 --access-token 10c7f4cb7e1df2d817a0e9e28391ad9c6f22d` --project-id 4321 --traceback`

## --debug

* Optional. Enables debug messages for any command. 
* Example: `$ qor init --organization-id 1234 --access-token 10c7f4cb7e1df2d817a0e9e28391ad9c6f22d`

Generates a step-by-step report of the executed command. The report includes the contents of the files to be processed. For example:



## Next Steps

Now that you've added your .qordoba.yml, to see some cli config exmaple go to [Cli configuration &rsaquo;][cli-configuration]

[cli-configuration]: /docs/{{page.kong_version}}/qordoba-cli/cli-configuration
