# Create a database

Your Percona Server for MySQL comes with a database called `defaultdb`. This is used for testing and some internal databases.

To create a new database, use `CREATE DATABASE` followed by a database name:

```bash
CREATE DATABASE example-database
```

Database names must follow these identifier rules. To avoid an error in case the database already exists, use the `IF NOT EXISTS` clause:

```bash
CREATE DATABASE IF NOT EXISTS example-database
```