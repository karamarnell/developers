---
id: page-install-method
title: Install - Compile From Source
header_title: Compile Source
header_icon: /assets/images/icons/icn-installation.svg
breadcrumbs:
  Installation: /install
redirect_from: /install/compile/
---

{% capture luajit_version %}{{site.data.qordoba_latest.dependencies.luajit}}{% endcapture %}
{% capture luarocks_version %}{{site.data.qordoba_latest.dependencies.luarocks}}{% endcapture %}
{% capture openresty_version %}{{site.data.qordoba_latest.dependencies.openresty}}{% endcapture %}

1. **Install the dependencies**

    [OpenResty {{openresty_version}}](https://openresty.org/en/installation.html).
    Qordoba being an OpenResty application, you must follow the OpenResty
    [installation instructions](https://openresty.org/en/installation.html).
    You will need [OpenSSL](https://www.openssl.org/) and
    [PCRE](http://www.pcre.org/) to compile OpenResty, and to at least use the
    following compilation options:

    ```bash
    $ ./configure \
      --with-pcre-jit \
      --with-ipv6 \
      --with-http_realip_module \
      --with-http_ssl_module \
      --with-http_stub_status_module \
      --with-http_v2_module
    ```

    You might have to specify `--with-openssl` and you can add any other option
    you'd like, such as additional Nginx modules or a custom `--prefix` directory.

    OpenResty conveniently bundles [LuaJIT](http://luajit.org/) and
    [resty-cli](https://github.com/openresty/resty-cli) which are essential to
    Qordoba. Add the `nginx` and `resty` executables to your $PATH:

    ```bash
    $ export PATH="$PATH:/usr/local/openresty/bin"
    ```

    [Luarocks {{luarocks_version}}](https://github.com/keplerproject/luarocks/wiki/Download),
    compiled with the LuaJIT version bundled with OpenResty (See the
    `--with-lua` and `--with-lua-include` configure options). Example:

    ```bash
    ./configure \
      --lua-suffix=jit \
      --with-lua=/usr/local/openresty/luajit \
      --with-lua-include=/usr/local/openresty/luajit/include/luajit-2.1
    ```

2. **Install Qordoba**

    Now that OpenResty is installed, we can use Luarocks to install Qordoba's Lua sources:

    ```bash
    $ luarocks install qordoba {{site.data.qordoba_latest.luarocks_version}}
    ```

    **Or**:

    ```bash
    $ git clone git@github.com:Mashape/qordoba.git
    $ [sudo] make install # this simply runs the `luarocks make qordoba-*.rockspec` command
    ```

    Finally, place the `bin/qordoba` script in your `$PATH`.

3. **Prepare your database**

    [Configure][configuration] Qordoba so it can connect to your database. Qordoba
    supports both [PostgreSQL {{site.data.qordoba_latest.dependencies.postgres}}](http://www.postgresql.org/)
    and [Cassandra {{site.data.qordoba_latest.dependencies.cassandra}}](http://cassandra.apache.org/)
    as its datastore.

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
