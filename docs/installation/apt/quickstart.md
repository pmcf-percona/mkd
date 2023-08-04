---
title: Installation guide
---
# Install via `apt`

Specific information on the supported platforms, products, and versions is described in [Percona Software and Platform Lifecycle](https://www.percona.com/services/policies/percona-software-platform-lifecycle#mysql).

## Install the latest version

--8<-- "quickstart.md"

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