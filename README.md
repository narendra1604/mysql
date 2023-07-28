
Setting environment for using XAMPP for Windows.
pavan@DESKTOP-AP8KEL0 c:\xampp
# mysql.exe -u root
Welcome to the MariaDB monitor.  Commands end with ; or \g.
Your MariaDB connection id is 9
Server version: 10.4.28-MariaDB mariadb.org binary distribution

Copyright (c) 2000, 2018, Oracle, MariaDB Corporation Ab and others.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

MariaDB [(none)]> create database nari;
Query OK, 1 row affected (0.002 sec)

MariaDB [(none)]> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| nari               |
| performance_schema |
| phpmyadmin         |
| test               |
+--------------------+
6 rows in set (0.016 sec)

MariaDB [(none)]> use nari;
Database changed
MariaDB [nari]> create table employe(empid int(10),name varchar(9),salary int(9));
Query OK, 0 rows affected (0.024 sec)

MariaDB [nari]> desc employe;
+--------+------------+------+-----+---------+-------+
| Field  | Type       | Null | Key | Default | Extra |
+--------+------------+------+-----+---------+-------+
| empid  | int(10)    | YES  |     | NULL    |       |
| name   | varchar(9) | YES  |     | NULL    |       |
| salary | int(9)     | YES  |     | NULL    |       |
+--------+------------+------+-----+---------+-------+
3 rows in set (0.014 sec)

MariaDB [nari]> alter table employe add(phoneno int(9));
Query OK, 0 rows affected (0.018 sec)
Records: 0  Duplicates: 0  Warnings: 0

MariaDB [nari]> desc employe;
+---------+------------+------+-----+---------+-------+
| Field   | Type       | Null | Key | Default | Extra |
+---------+------------+------+-----+---------+-------+
| empid   | int(10)    | YES  |     | NULL    |       |
| name    | varchar(9) | YES  |     | NULL    |       |
| salary  | int(9)     | YES  |     | NULL    |       |
| phoneno | int(9)     | YES  |     | NULL    |       |
+---------+------------+------+-----+---------+-------+
4 rows in set (0.018 sec)

MariaDB [nari]> alter table employe drop salary;
Query OK, 0 rows affected (0.034 sec)
Records: 0  Duplicates: 0  Warnings: 0

MariaDB [nari]> desc salary;
ERROR 1146 (42S02): Table 'nari.salary' doesn't exist
MariaDB [nari]> desc employe;
+---------+------------+------+-----+---------+-------+
| Field   | Type       | Null | Key | Default | Extra |
+---------+------------+------+-----+---------+-------+
| empid   | int(10)    | YES  |     | NULL    |       |
| name    | varchar(9) | YES  |     | NULL    |       |
| phoneno | int(9)     | YES  |     | NULL    |       |
+---------+------------+------+-----+---------+-------+
3 rows in set (0.019 sec)

MariaDB [nari]> truncate table nari;
ERROR 1146 (42S02): Table 'nari.nari' doesn't exist
MariaDB [nari]> truncate table employe;
Query OK, 0 rows affected (0.041 sec)

MariaDB [nari]> desc employe;
+---------+------------+------+-----+---------+-------+
| Field   | Type       | Null | Key | Default | Extra |
+---------+------------+------+-----+---------+-------+
| empid   | int(10)    | YES  |     | NULL    |       |
| name    | varchar(9) | YES  |     | NULL    |       |
| phoneno | int(9)     | YES  |     | NULL    |       |
+---------+------------+------+-----+---------+-------+
3 rows in set (0.014 sec)

MariaDB [nari]> insert into employe values(1,'nari',852);
Query OK, 1 row affected (0.005 sec)

MariaDB [nari]> insert into employe values(2,'praveen',741);
Query OK, 1 row affected (0.005 sec)

MariaDB [nari]> insert into employe values(3,'bose',963);
Query OK, 1 row affected (0.008 sec)

MariaDB [nari]> select*from employe;
+-------+---------+---------+
| empid | name    | phoneno |
+-------+---------+---------+
|     1 | nari    |     852 |
|     2 | praveen |     741 |
|     3 | bose    |     963 |
+-------+---------+---------+
3 rows in set (0.000 sec)

MariaDB [nari]> update employe set phoneno=234 where phoneno=852;
Query OK, 1 row affected (0.008 sec)
Rows matched: 1  Changed: 1  Warnings: 0

MariaDB [nari]> select*from employe;
+-------+---------+---------+
| empid | name    | phoneno |
+-------+---------+---------+
|     1 | nari    |     234 |
|     2 | praveen |     741 |
|     3 | bose    |     963 |
+-------+---------+---------+
3 rows in set (0.000 sec)

MariaDB [nari]> select empid,name from employe;
+-------+---------+
| empid | name    |
+-------+---------+
|     1 | nari    |
|     2 | praveen |
|     3 | bose    |
+-------+---------+
3 rows in set (0.001 sec)

MariaDB [nari]> delete from employe where empid=1;
Query OK, 1 row affected (0.004 sec)

MariaDB [nari]> select*from employe;
+-------+---------+---------+
| empid | name    | phoneno |
+-------+---------+---------+
|     2 | praveen |     741 |
|     3 | bose    |     963 |
+-------+---------+---------+
2 rows in set (0.000 sec)

MariaDB [nari]>
