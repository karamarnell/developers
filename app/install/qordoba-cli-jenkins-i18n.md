---
id: page-install-method
title: Qordoba CLI Installation
header_title: Qordoba CLI Installation
header_icon: /assets/images/icons/icn-installation.svg
breadcrumbs:
  Installation: /install
---

### Installation

1. **Install Qordoba Command Line Integration (Q-CLI) Package**

    The client uses pip commands for housekeeping. Please have both [python](https://www.python.org/) and [pip](https://pip.pypa.io/en/stable/installing/#) installed and available in the system PATH. Run the following command on your command line:

    ```
    pip install qordoba
    ```
    If you are instead updating an existing Q-CLI, run this command:

    ```
    pip install qordoba -U
    ```

2. **Configure Q-CLI to Project**

    Connecting to a Qordoba project from your command line needs authentication. The required parameters are: 
    - Organization ID
    - Project ID
    - Access Token

    There are two ways to include these parameters in the Q-CLI:

    <br/>
    **Recommended:** Download Configuration File.

    The configuration file saves you from re-entering your option-value pairs on the command line each time you want to send content to Qordoba.
    
    To download the configuration file, go to your project's settings in Qordoba, and select CLI config. Click on "Download the config file". Once downloaded, you can move the file named `config.yaml` to one of three places:<br/><br/>
    -   At the path specified in the environment variable `QORDOBA_CONFIG`.<br/>
    -   In the current working directory as hidden file `.qordoba.yml`.<br/>
    -   In the user's home directory as hidden file `.qordoba.yml`.

    Once this is done, make sure to rename `config.yaml` to `.qordoba.yml`.<br/>
    **Note**: _Notice that **.yaml** changes to **.yml**_

    Edit the file to add your source paths and optionally your output paths:

    ```yaml
     #Example .qordoba.yml file after adding push and pull edits.
    qordoba: 
      access_token: 10c7f4qordobaisdopestdf2d817a0e9e28391ad9c6f22d
      organization_id: 1234
      project_id: 12321
       
      #as of version 1.2.0:
      push: #(required)
        sources:
          - "./sourcePath/*.yml"
      pull: #(optional. default: files pulled into same dir as config)
        targets:
          - "./<language_code>/<filename>.<extension>" 
    ```
    <br/>
    <br/>
    **Not Recommended:** Manual addition of parameters.

    The other option is to manually add parameters to each call to Qordoba. If you do this, you will also have to identify which source files you want to push with each call, and where you want each output file to be stored.

    ```bash
    $ qor push --organization-id 1234 --access-token 10c7f4cfrohzuseinbedarfeswenige2d --project-id 4422
    ```

3. **Send Content To Qordoba**

    Now that you have your configuration set up, all you have to do to send strings for translation to Qordoba is the command (assuming you have added and edited the `.qordoba.yml` file):

    ```bash
    $ qor push
    ```
    And all of the valid files specified in your sources paths will get uploaded to your project in Qordoba. If the `.qordoba.yml` file was saved into the file structure of your codebase, make sure you are in the same working directory when you call this command.

4. **Retrieve Content from Qordoba**

    Once content is complete in Qordoba, it will be able to be collected from Qordoba. To do this, run:

    ```bash
    $ qor pull
    ```

    And all finished content will be pulled down and added to the location you defined in `.qordoba.yml`.

5. **Next Steps/Help**
    You can type:

    ```bash
    $ qor -h
    ```
    To get basic help and instructions for the Q-CLI. If you cannot find what you are looking for there, Please look at our FAQ **INSERT LINKS** and documentation **INSERT LINKS** pages.