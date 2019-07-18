# MySQL Shell Notes

### Run the MySQL shell environment

```shell
mysql -h [HOST] -u [USERNAME] -p
```
### Type in your password after:
`Pasword: `

### The MySQL shell should appear like so:
`mysql> `

### To show all databases, type the following command:

```sql
SHOW DATABASES;
```

### To run commands from a specific database, type the following command: {#use}

```sql
USE [DB_NAME]
```

### To create a database, type the following command:

```sql
CREATE DATABASE [DB_NAME];
```

### To create a new user, type the following command:

```sql
CREATE USER '[USER_NAME]'@'[HOST]' IDENTIFIED BY '[PASSWORD]';
```

### To view all users, type the following command:

```sql
SELECT User, Host, Password FROM mysql.user;
```

### To grant a user access to a specific database, type the following command

```sql
GRANT ALL PRIVILEGES ON `[DB_NAME]`.* TO '[USER_NAME'@'[HOST]';
```

#### Then flush privileges using the following command:

```sql
FLUSH PRIVILEGES;
```

#### The preceeding command shows you how to add `ALL PRIVILEGES` for the given user, but you can also add limited privileges by replacing `ALL PRIVILEGES` with one of the following:
* `CREATE`
* `DROP`
* `DELETE`
* `INSERT`
* `SELECT`
* `UPDATE`

#### Warning: notice the use of backticks ` ` in the `GRANT` command.
* If you database name contains an under score `my_database` the command should look as follows:

```sql
GRANT ALL PRIVILEGES ON `my\_database`.* TO '[USER_NAME]'@'[HOST]';
```

#### Then flush privileges using the following command:

```sql
FLUSH PRIVILEGES;
```

### To view privileges of a given user, type the following command:

```sql
SHOW GRANTS FOR '[USER_NAME]'@'[HOST]';
```

### To revoke privileges from a user, type the following command:

```sql
REVOKE ALL PRIVILEGES ON [DB_NAME].* FROM '[USER_NAME]'@'[HOST]';
```

### To create a table, make sure you are running this command from the [correct database](#use) and type the following command:

```sql
CREATE TABLE [TABLE_NAME] (
	id INT AUTO_INCREMENT PRIMARY KEY,
	username VARCHAR(100),
	password VARCHAR(100),
	email VARCHAR(100),
	phone VARCHAR(100)
);
```