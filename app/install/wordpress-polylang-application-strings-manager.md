---
id: page-install-method
title: Install - Vagrant
header_title: Vagrant Installation
header_icon: /assets/images/icons/icn-installation.svg
breadcrumbs:
  Installation: /install
---

Vagrant can be used to create an isolated environment for Qordoba and its
dependencies.

You can use the Vagrant box either as an all-in-one Qordoba installation for
testing purposes, or you can link it up with source code and start developing
on Qordoba or on custom plugins.

Here is a quick example showing how to build a (disposable) test setup:

1. **Get the Vagrantfile and start the VM**

    ```bash
    $ git clone https://github.com/Mashape/qordoba-vagrant
    $ cd qordoba-vagrant/
    $ vagrant up
    ```

2. **Start Qordoba**

    ```bash
    # specify migrations flag to initialise the datastore
    $ vagrant ssh -c "qordoba start --run-migrations"
    ```
    <br/>
    The host ports `8000`, `8001`, `8443`, and `8444` will be forwarded to the Vagrant box.

    <div class="alert alert-warning">
      <div class="text-center">
        <strong>Note</strong>: Check out the <a href="{{ site.repos.vagrant }}">qordoba-vagrant</a> repository for further details on customizations and development.
      </div>
    </div>

3. **Use Qordoba**

    Qordoba is running:

    ```bash
    $ curl http://127.0.0.1:8001
    ```

    Quickly learn how to use Qordoba with the [5-minute Quickstart](/docs/latest/getting-started/quickstart).
