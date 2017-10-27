# Essential Dev Hacks

## MySQL Hacks

### Recovering _root_ user and its privileges

1. Stop MySQL service 

`$ service mysql stop`

2. Create directory for **mysqld**

`$ sudo mkdir -p /var/run/mysqld`
`$ sudo chown mysql:mysql /var/run/mysqld`

3. Access mysqld

`$ mysqld_safe --skip-grant-tables &`
`mysql -u root -p`
Enter your password
At the mysql command line enter: use mysql;


First, connect in sudo mysql
sudo mysql -u root
Check your accounts present in your db
SELECT User,Host FROM mysql.user;
+------------------+-----------+
| User             | Host      |
+------------------+-----------+
| admin            | localhost |
| debian-sys-maint | localhost |
| magento_user     | localhost |
| mysql.sys        | localhost |
| root             | localhost |
Delete current root@localhost account
mysql> DROP USER 'root'@'localhost';
Query OK, 0 rows affected (0,00 sec)
Recreate your user
mysql> CREATE USER 'root'@'%' IDENTIFIED BY '';
Query OK, 0 rows affected (0,00 sec)
Give permissions to your user (don't forget to flush privileges)
mysql> GRANT ALL PRIVILEGES ON *.* TO 'root'@'%';
Query OK, 0 rows affected (0,00 sec)

mysql> FLUSH PRIVILEGES;
Query OK, 0 rows affected (0,01 sec)
