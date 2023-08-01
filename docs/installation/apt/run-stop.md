---
title: Run/Stop
---
# Run/Stop Percona Server for MySQL

## Run

Run the following commands as root or by using the `sudo` command.

??? info "Optional use of `debian-sys-maint` user"
    Debian and Ubuntu installation doesn’t automatically create a special `debian-sys-maint` user which can be used by the control scripts to control the Percona Server for MySQL `mysqld` and `mysqld_safe` services which was the case with previous Percona Server for MySQL versions. If you still require this user you’ll need to create it manually.

Unless any error is found during the process, Percona Server for MySQL is automatically started after installation. To confirm the service is running, you can check it with:

```bash
$ sudo service mysql status
```

If stopped, you can also manually start Percona Server by entering:

```bash
$ sudo service mysql start
```

??? info "You can either use `service` or `systemctl`"
    Debian 9.0 (stretch) and Ubuntu 18.04 LTS (bionic) come with [systemd](http://freedesktop.org/wiki/Software/systemd/) as the default system and service manager. You can invoke all the above commands with `systemctl` instead of `service`. Currently, both are supported.

## Stop & Restart

You can stop the service by entering:

```bash
$ sudo service mysql stop
```

To restart the service:

```bash
$ sudo service mysql restart
```

## Files & Configuration

Percona Server for MySQL stores the data files in `/var/lib/mysql/` by default. You can find the configuration file that is used to manage Percona Server for MySQL in `/etc/mysql/my.cnf`.

## AppArmor

Associate an AppArmor profile to Percona Server. For information, see [Working with AppArmor](../security/apparmor.md).