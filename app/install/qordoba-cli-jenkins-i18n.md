---
id: page-install-method
title: Qordoba CLI Installation
header_title: Qordoba CLI Installation
header_icon: /assets/images/icons/icn-installation.svg
breadcrumbs:
  Installation: /install
---

### Packages

- [Homebrew Formula]({{ site.repos.homebrew }})

----

### Installation

1. **Install Qordoba Command Line Integration (Q-CLI)**

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

    There are two ways to include these parameters in the C-CLI:
    
    **Recommended:** Download Configuration File.

    The configuration file saves you from re-entering your option-value pairs on the command line each time you want to send content to Qordoba.
    
    To download the configuration file, go to your project's settings in Qordoba, and click on CLI config. Click on Download
        


    B.  Connecting via config.yml  - *recommended*





    Go to your desired project within Qordoba that you want to link the Q-CLI to.
    In Project settings, go to CLI config and download the configuration file.

    **Note**: migrations should never be run concurrently; only
    one Kong nodes should be performing migrations at a time.

3. **Start Kong**

    ```bash
    $ kong start [-c /path/to/kong.conf]
    ```

4. **Use Kong**

    Kong is running:

    ```bash
    $ curl -i http://localhost:8001/
    ```

    Quickly learn how to use Kong with the [5-minute Quickstart](/docs/latest/getting-started/quickstart).

[configuration]: /docs/{{site.data.kong_latest.release}}/configuration#database
