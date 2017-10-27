# Essential Dev Hacks

## MySQL Hacks

### Recovering _root_ user's privileges

1. Stop MySQL service 

```
$ service mysql stop
```

2. Create directory for **mysqld**

```
$ sudo mkdir -p /var/run/mysqld

$ sudo chown mysql:mysql /var/run/mysqld
```

3. Access mysqld

```
$ sudo mysqld_safe --skip-grant-tables &

mysql -u root -p
```

4. Give permissions 

```
mysql> UPDATE mysql.user SET Grant_priv='Y', Super_priv='Y' WHERE User='root';

mysql> FLUSH PRIVILEGES;

mysql> GRANT ALL PRIVILEGES ON *.* TO 'root'@'localhost';

Query OK, 0 rows affected (0,00 sec)

mysql> FLUSH PRIVILEGES;

Query OK, 0 rows affected (0,01 sec)
```
