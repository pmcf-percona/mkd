# Set up PMM Client using Percona Repositories

Use the Percona Repositories as it's a simplified, hassle-free process that will ensure you will always get the latest, tested and supported version without a hitch. It's also the fastest way to make sure you have accurate and insightful performance to monitor with PMM Server with all the cool features.

## Install PMM Client

=== "apt"

    If you're on Debian, Ubuntu or any other Debian-based system, follow these commands to install PMM Client package.
    {.power-number}

    1. First, configure the repositories.

        ```sh
        wget https://repo.percona.com/apt/percona-release_latest.generic_all.deb
        dpkg -i percona-release_latest.generic_all.deb
        ```

    2. Install the PMM Client package.

        <i info>Note:</i> You have to install with root permissions.

        ```sh
        apt update
        apt install -y pmm2-client
        ```

    3. Check if it's correctly installed.

        ```sh
        pmm-admin --version
        ```

=== "yum"

    If you're on Red Hat Enterprise Linux, CentOS or just using `yum`, follow these commands to install PMM Client package.
    {.power-number}

    1. First, configure the repositories.

        ```sh
        yum install -y https://repo.percona.com/yum/percona-release-latest.noarch.rpm
        ```

    2. Install the PMM Client package.

        ```sh
        yum install -y pmm2-client
        ```

    3. Check if it's correctly installed.

        ```sh
        pmm-admin --version
        ```

## Register PMM Client

Register your client node with PMM Server.

```sh
pmm-admin config --server-insecure-tls --server-url=https://admin:admin@X.X.X.X:443
```

- `X.X.X.X` is the address of your PMM Server.
- `443` is the default port number.
- `admin`/`admin` is the default PMM username and password. This is the same account you use to log into the PMM user interface, which you had the option to change when first logging in.

!!! caution "Important"
    Clients must be registered with the PMM Server using a secure channel. If you use http as your server URL, PMM will try to connect via https on port 443. If a TLS connection can't be established you will get an error and you must use https along with the appropriate secure port.

### Example

Register on PMM Server with IP address `192.168.33.14` using the default `admin/admin` username and password, a node with IP address `192.168.33.23`, type `generic`, and name `mynode`.

```sh
pmm-admin config --server-insecure-tls --server-url=https://admin:admin@192.168.33.14:443 192.168.33.23 generic mynode
```


## Next step: Connect Databases to PMM Server

Now that you have both PMM Server and one or more PMM Clients installed you need to do now is to connect one or more Databases to PMM Server. Learn how in the button below.

[Connect Databases to PMM Server :material-arrow-right:](../connect-databases/index.md){ .md-button .md-button--primary }