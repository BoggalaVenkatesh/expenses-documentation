# MySQL

Developer has chosen the database MYSQL. Heance, we are trying to install it up configure it.

**Versions of the DB Software i will get context from the developer, Meaning we need to check with developer.**

Install MySQL Server 8.0.x

```

dnf install mysql-server -y
```
Start MySQL Service

```
systemctl enable mysqld
```
```
systemctl start mysqld
```
Next, We need to change the default root password in order to start using the database service. Use password ExpenseApp@1(XXXXXXX) or any other as per your choice.

```

mysql_secure_installation --set-root-pass ExpenseApp@1
```

## Verfication

we can check data by using client package called mysql.

Usually command to connect mysql server is

```
mysql -h <host-address> -u root -p<password>
```

But if you client and server both are in a single server, you can simply issue.

```
mysql
```

