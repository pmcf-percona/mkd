---
title: Quickstart
---
# Install via `apt`

Specific information on the supported platforms, products, and versions is described in [Percona Software and Platform Lifecycle](https://www.percona.com/services/policies/percona-software-platform-lifecycle#mysql).

## Install the latest version {.power-list}

Before starting, we advise updating the `apt` repositories and installing `curl` download utility to fetch the package. If you want to fetch the package manually, follow this guide instead: [Manual Installation](#).
```{.bash data-prompt="$"}
$ sudo apt update
$ sudo apt install curl
```

Once everything is updated and ready, you can follow the below tasks to install:

1. The first step is downloading the `percona-release` repository package:
	```{.bash data-prompt="$"}
	$ curl -O https://repo.percona.com/apt/percona-release_latest.generic_all.deb
	```

2. Install the downloaded package with `apt` as root or with `sudo`, and then refresh the local cache to update the package information:
	```{.bash data-prompt="$"}
	$ sudo apt install gnupg2 lsb-release ./percona-release_latest.generic_all.deb
	$ sudo apt update
	```

3. Use `percona-release` to set up the repository for the Percona Server for MySQL 8.0 version:
	```{.bash data-prompt="$"}
	$ sudo percona-release setup ps80
	```
	You can check the repository setup for the Percona original release list in `/etc/apt/sources.list.d/percona-original-release.list`.

4. Install the server package with the `percona-release` command:
	```{.bash data-prompt="$"}
	$ sudo apt install percona-server-server
	```
	For more information on `percona-release` command see [Configuring Percona Repositories](https://docs.percona.com/percona-software-repositories/percona-release.html).

5. It should now be installed! Percona Server runs automatically after installation. To control the service, learn how to [Stop/Run Percona Server](apt/run-stop.md).

!!! info "Storage engine option"
	Percona Server for MySQL comes with **InnoDB storage engine**. If you prefer to install MyRocks instead, go to [MyRocks Installation Guide](https://docs.percona.com/percona-server/8.0/myrocks/install.html).

	Starting with Percona Server for MySQL 8.0.28-19 (2022-05-12), the TokuDB storage engine is no longer supported. We have removed the storage engine from the installation packages and disabled the storage engine in our binary builds. For more information, see [TokuDB Introduction](https://docs.percona.com/percona-server/8.0/tokudb/tokudb_intro.html).

### Improve checksums speed <small>(optional)</small>

Percona Server for MySQL contains user-defined functions from [Percona Toolkit](https://docs.percona.com/percona-toolkit/). These user-defined functions provide faster checksums. For more details on the user-defined functions, see [Percona Toolkit UDF functions](https://www.percona.com/doc/percona-server/8.0/management/udf_percona_toolkit.html).

After the installation completes, run the following commands to create these functions:

```mysql
mysql -e "CREATE FUNCTION fnv1a_64 RETURNS INTEGER SONAME 'libfnv1a_udf.so'"
mysql -e "CREATE FUNCTION fnv_64 RETURNS INTEGER SONAME 'libfnv_udf.so'"
mysql -e "CREATE FUNCTION murmur_hash RETURNS INTEGER SONAME 'libmurmur_udf.so'"
```

### Install a pre-release <small>(optional)</small>

Percona offers pre-release builds from the testing repository. To enable it, run
percona-release with the `testing` argument. Run the following command as root or use the sudo command:

```{.bash data-prompt="$"}
$ sudo percona-release enable ps80 testing
```

!!! warning "Don't run pre-releases in production"
	These pre-release builds should not be run in production. They may not contain all of the features available in the final release. The features may change without notice.