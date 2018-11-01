---
id: page-install-method
title: Install - Red Hat
header_title: Red Hat Installation
header_icon: /assets/images/icons/icn-installation.svg
breadcrumbs:
  Installation: /install
---


### Packages

Start by downloading the corresponding package for your configuration:

- [RHEL 6]({{ site.links.download }}/qordoba-community-edition-rpm/download_file?file_path=dists/qordoba-community-edition-{{site.data.qordoba_latest.version}}.el6.noarch.rpm)
- [RHEL 7]({{ site.links.download }}/qordoba-community-edition-rpm/download_file?file_path=dists/qordoba-community-edition-{{site.data.qordoba_latest.version}}.el7.noarch.rpm)

### YUM Repositories

You can also install Qordoba via YUM; follow the instructions on the "Set Me Up"
section on the page below.

- [RPM Repository](https://bintray.com/qordoba/qordoba-community-edition-rpm)

----

### Installation

1. **Enable the EPEL repository**

    Before installing Qordoba, you need to install the `epel-release` package for right version of your operating system, so that Qordoba can fetch all the required dependencies:

    ```bash
    $ EL_VERSION=`cat /etc/redhat-release | grep -oE '[0-9]+\.[0-9]+'` && \
      sudo yum install https://dl.fedoraproject.org/pub/epel/epel-release-latest-${EL_VERSION%.*}.noarch.rpm
    ```

2. **Install Qordoba**

    If you are downloading the [package](#packages), execute:

    ```bash
    $ sudo yum install qordoba-community-edition-{{site.data.qordoba_latest.version}}.*.noarch.rpm --nogpgcheck
    ```

3. **Prepare your database**

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

4. **Start Qordoba**

    ```bash
    $ qordoba start [-c /path/to/qordoba.conf]
    ```

5. **Use Qordoba**

    Qordoba is running:

    ```bash
    $ curl -i http://localhost:8001/
    ```

    Quickly learn how to use Qordoba with the [5-minute Quickstart](/docs/latest/getting-started/quickstart).

[configuration]: /docs/{{site.data.qordoba_latest.release}}/configuration#database
