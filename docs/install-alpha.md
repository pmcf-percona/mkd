# Product Alpha quickstart

This guide covers how you can quickly get started using PA. This is applicable to Docker compatible Linux based systems.

## Prerequisites

[Docker](#) 1.12.6 or higher.

## System requirements

### Disk

Approximately 1 GB of storage per monitored database node with data retention set to one week.

### Memory

A minimum of 2 GB per monitored database node. The increase in memory usage is not proportional to the number of nodes. For example, data from 20 nodes should be easily handled with 16 GB.

### Ports

This is a list of [ports](#) used by the various components of PA.

For PA to work correctly, your system’s firewall should allow TCP traffic on these ports (UDP is not needed).

## Install PA

!!! note "Important"
    - You can use the easy installation script that will verify and install any missing software and dependencies. To use it, run the command with sudo privileges or as root.
    - You can download the script from github.

Here are the steps for installing the PA server:

1. Set up Docker on [Mac](#) or [Linux](#).

2. Install the PA server using `cURL` or `wget` as follows:

    === "cURL"
        ```bash
        curl -fsSL https://www.percona.com/get/pa | /bin/bash
        ```

    === "wget"
        ```bash
        wget -qO - https://www.percona.com/get/pa | /bin/bash
        ```

3. Log in to PA with the default login credentials provided after the installation is completed.

For detailed instructions on installing the PA server with the other methods, see [Setting up PA](#).

## Add a database instance

=== "MySQL 5.7 or 8.0"
    Before you add a MySQL database for monitoring you should have a [database account for PA](#).

    Here are the steps to add a MySQL database for monitoring:

    1. From the PA UI, go to **Configuration → PA Inventory → Add Instance**.
    2. Select **MySQL**. The **Add Service** page opens.
    3. Enter your database credentials on the resulting page without changing any values.
    4. Optional: Enter the information on the **Labels** and **Additional Options** section.
    5. Click **Add Service** at the bottom.

    For detailed information, see [Adding a MySQL database for monitoring](#).

=== "MongoDB"
    Before you add a MongoDB database for monitoring you should have a [database account for PA](#).

    Here are the steps to add a MongoDB database for monitoring:

    1. From the PA UI, go to **Configuration → PA Inventory → Add Instance**.
    2. Select **MongoDB**. The **Add Service** page opens.
    3. Enter your database credentials on the resulting page without changing any values.
    4. Optional: Enter the information in the **Labels** and **Additional Options** section.
    5. Click **Add Service** at the bottom.

    For detailed information on adding a MongoDB database, see [Adding a MongoDB database for monitoring](#).

=== "PostgreSQL"
    Before you add a PostgreSQL database for monitoring you should have a [database account for PA](#).

    Here are the steps to add a PostgreSQL database for monitoring:

    1. From the PA UI, go to **Configuration → PA Inventory → Add Instance**.
    2. Select **PostgreSQL**. The **Add Service** page opens.
    3. Enter your database credentials on the resulting page without changing any values.
    4. Optional: Enter the information in the **Labels** and **Additional Options** section.
    5. Click **Add Service** at the bottom.

    For detailed information on adding a PostgreSQL database, see [Adding a PostgreSQL database for monitoring](#).

=== "Amazon RDS"

    You can use PA for monitoring [Amazon RDS](#). By using the PA web interface, you connect to the Amazon RDS DB instance.

    You only need to provide the [IAM user access key](#) or assign an [IAM role](#) and PA discovers the Amazon RDS DB instances available for monitoring.

    Before you add Amazon instance for monitoring you should have the following:

    - AWS RDS Access Key and RDS Secret Access Key. This key should have permission to monitor RDS.
    - Recommended: Enable Enhanced Monitoring option in the settings of your Amazon RDS DB instance.
    - Database username and password with access to login to the RDS instance.
    - Access to the RDS instance via a TCP port.

    Here are the steps to add an Amazon RDS database instance for monitoring:

    1. From the PA UI, go to **Configuration → PA Inventory → Add Instance**.
    2. Select **Amazon RDS – Add a remote instance**.
    3. Enter the **access key ID** and the **secret access key** of your IAM user or leave these fields empty if an IAM role was created.
    4. Click **Discover** for PA to retrieve the available Amazon RDS instances.
    5. For the instance that you would like to monitor, select **Start monitoring**.
    6. Enter your database credentials on the resulting page without changing any values.
    7. Optional: Enter the information on the **Labels** or **Additional Options** section.
    8. Click **Add Service** at the bottom.

    For detailed information, see Adding an Amazon RDS instance for monitoring.

## Next steps

Explore the following topics to gain a deeper understanding of PA:

- Configure - Learn how to configure PA via the interface.
- Manage users - Learn how to manage users in PA.
- Roles and permissions - Learn more about roles and permissions in PA.
- Backup and restore — Learn how to backup and to restore data in PA.

## Contact us

For free technical help, visit the Percona [Community Forum](#).

To report bugs or submit feature requests, open a [JIRA](#) ticket.

For paid [support](#) and [managed](#) or [consulting services](#), contact [Percona Sales](#).