---
id: page-install-method
title: Install - Ubuntu
header_title: Ubuntu Installation
header_icon: /assets/images/icons/icn-installation.svg
breadcrumbs:
  Installation: /install
---

### Packages

Start by downloading the corresponding package for your configuration:

- [12.04 Precise]({{ site.links.download }}/qordoba-community-edition-deb/download_file?file_path=dists/qordoba-community-edition-{{site.data.qordoba_latest.version}}.precise.all.deb)
- [14.04 Trusty]({{ site.links.download }}/qordoba-community-edition-deb/download_file?file_path=dists/qordoba-community-edition-{{site.data.qordoba_latest.version}}.trusty.all.deb)
- [16.04 Xenial]({{ site.links.download }}/qordoba-community-edition-deb/download_file?file_path=dists/qordoba-community-edition-{{site.data.qordoba_latest.version}}.xenial.all.deb)
- [17.04 Zesty]({{ site.links.download }}/qordoba-community-edition-deb/download_file?file_path=dists/qordoba-community-edition-{{site.data.qordoba_latest.version}}.zesty.all.deb)

### APT Repositories

You can also install Qordoba via APT; follow the instructions on the "Set Me Up"
section on the page below, setting  *distribution* to the appropriate value
(e.g., `precise`) and *components* to `main`.

- [Deb Repository](https://bintray.com/qordoba/qordoba-community-edition-deb)

----

### Installation

1. **Install Qordoba**

    If you are downloading the [package](#packages), execute:

    ```bash
    $ sudo apt-get update
    $ sudo apt-get install openssl libpcre3 procps perl
    $ sudo dpkg -i qordoba-community-edition-{{site.data.qordoba_latest.version}}.*.deb
    ```

2. **Prepare your database**

    [Configure][configuration] Qordoba so it can connect to your database. Qordoba supports both [PostgreSQL {{site.data.qordoba_latest.dependencies.postgres}}](http://www.postgresql.org/) and [Cassandra {{site.data.qordoba_latest.dependencies.cassandra}}](http://cassandra.apache.org/) as its datastore.

    If you are using Postgres, please provision a database and a user before starting Qordoba, ie:

    ```sql
    CREATE USER qordoba; CREATE DATABASE qordoba OWNER qordoba;
    ```

    Now, run the Qordoba migrations:

    ```bash
    $ qordoba migrations up [-c /path/to/qordoba.conf]
    ```

    **Note**: migrations should never be run concurrently; only
    one Qordoba nodes should be performing migrations at a time.

3. **Start Qordoba**

    ```bash
    $ qordoba start [-c /path/to/qordoba.conf]
    ```

4. **Use Qordoba**

    Qordoba is running:

    ```bash
    $ curl -i http://localhost:8001/
    ```

    Quickly learn how to use Qordoba with the [5-minute Quickstart](/docs/latest/getting-started/quickstart).

[configuration]: /docs/{{site.data.qordoba_latest.release}}/configuration#database
