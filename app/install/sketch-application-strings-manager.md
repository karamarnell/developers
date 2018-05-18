---
id: page-install-method aws-marketplace
title: Install - Amazon Linux
header_title: Amazon Linux
header_icon: /assets/images/icons/icn-installation.svg
breadcrumbs:
  Installation: /install
---

### Packages

Start by downloading the following package specifically built for the Amazon Linux AMI:

- [Download]({{ site.links.download }}/qordoba-community-edition-aws/download_file?file_path=dists/qordoba-community-edition-{{site.data.qordoba_latest.version}}.aws.rpm)

----

### Installation

1. **Install Qordoba**

    After downloading the [package](#packages), execute:

    ```bash
    $ sudo yum install epel-release
    $ sudo yum install qordoba-community-edition-{{site.data.qordoba_latest.version}}.aws.rpm --nogpgcheck
    ```

2. **Prepare your database**

    [Configure][configuration] Qordoba so it can connect to your database. Qordoba supports both [PostgreSQL {{site.data.qordoba_latest.dependencies.postgres}}](http://www.postgresql.org/) and [Cassandra {{site.data.qordoba_latest.dependencies.cassandra}}](http://cassandra.apache.org/) as its datastore.

    If you are using Postgres, please provision a database and a user before starting Qordoba, i.e.:

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
