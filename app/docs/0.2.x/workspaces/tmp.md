---
title: CLI
---

# What is the Q-CLI?

The Q-CLI is a ** PyPi package** that allows you to manage project files between Qordoba and your localhost. 

Core elements are the push and pull command and your config file (.qordoba.yml) which holds your organization-id, access-token, project-id to safely authenticate you to Qordoba.

# Why you should use it.

Are there a lot of local projects files which need to be uploaded to Qordoba's strings project for localization? Q-CLI enables you to push/pull any number of project files in a very short amount of time -  no more tedious manual uploading.

Many of our customers automated the Q-CLI. A code snippet in Jenkins can easily automate the Q-CLI execution for every build.


# Installation

##Option 1:
The client uses pip commands for housekeeping. Please have both [python](https://www.python.org/) and [pip](https://pip.pypa.io/en/stable/installing/#) installed and available in the system PATH.

```
	pip install qordoba
	pip install qordoba -U (upgrade)
```

##Option 2: 

1. [Download](https://github.com/Qordobacode/qordoba-cli/tree/master)
2. Unpack
3. cd into directory
4. pip install.


# Authenticating - Config.yml

Connecting to a Qordoba project from your localhost needs authentication. 
**Organization ID**, **Project ID**, and **Account Token** (Required)

##Option 1: Connecting via config.yml  - *recommended*

The configuration file saves you from re-entering your option-value pairs on the command line.

**Step 1: download** your configuration file located in your project settings. The file contains your --organization-id, project-id and --access-token. 

**Step 2: move** your downloaded configuration file and optionally set an environment variable.

    `qordoba` will look for its configuration file in the following order:

    1. At the path specified in the environment variable `QORDOBA_CONFIG`.
    2. In the current working directory as hidden file `.qordoba.yml`.
    3. In the user's home directory as hidden file `.qordoba.yml`.

**Step 3: rename** the filename from `config.yaml` to `.qordoba.yml` (Important: not y**a**ml).

**Step 4: add ** (optional) the source path and target path to your configuration as shown. The default will push/pull projects files based on dir of the configuration file.


```
qordoba: 
  access_token: 10c7f4qordobaisdopestdf2d817a0e9e28391ad9c6f22d
  organization_id: 1234
  project_id: 12321
       
  #as off version 1.2.0:
  push: (requisite)
    sources:
    - "./source/*.yml" 
  pull: (optional. default: files pulled in same dir as config)
    targets:
    - "./<language_code>/<filename>.<extension>" 
```

##Option 2: Connecting over command line

Without a configuration file, you must enter option-value pairs for authentication on the command line.

1. Under your settings in your Qordoba projects click the CLI Config tab. 
2. On your host computer command line, `cd` to your project directory and enter command options plus authentication pairs.

```
$ qor push --organization-id 1234 --access-token 10c7f4cfrohzuseinbedarfeswenige2d --project-id 4422

```

Note:  command line option-value pairs will override the configuration file option-value pairs.




## Next Steps

Now that you've added your API to Qordoba, let's learn how to enable plugins.

Go to [Enabling Plugins &rsaquo;][cli-configuration]

[cli-configuration]: /docs/{{page.qordoba_version}}/qordoba-cli/cli-configuration

