---
title: Uninstall
---
# Uninstall Percona Server for MySQL

To uninstall Percona Server for MySQL you’ll need to remove all the installed packages. Removing packages with `apt remove` does not remove the configuration and data files.

Removing the packages with `apt purge` does remove the packages with configuration files and data files (all the databases). Depending on your needs, you can choose which command better suits you.
{.power-list}

1. First, stop the Percona Server for MySQL service:
    ```bash
    $ sudo service mysql stop
    ```

2. Then remove the packages using your preferred method.
    - Remove the packages:
        ```bash
        $ sudo apt remove percona-server\
        ```
        This will leave the data files (databases, tables, logs, configuration, etc.) behind. If you don’t need them, you must remove them manually.

    - Purge the packages and delete data files:
        ```bash
        $ sudo apt purge percona-server\
        ```
        This command removes all the packages and deletes all the data files (databases, tables, logs, and so on.).