# Mysql leanring

数据库是按照数据结构来组织，储存和管理数据的仓库

RDBMS即关系数据库管理系统（Relational Database Management System）的特点：
- 数据以表格形式出现
- 每行为各种记录名称
- 每列为记录名称所对应的数据域
- 许多的行和列组成一张表单
- 若干的表单组成database

## RDBMS 术语：

- **数据库**：数据库是一些关联表的集合
- **数据表**：表是数据的矩阵。在一个数据库中的表看起来像一个电子表格
- **行**：一行（=元组，或记录）是一组相关的数据，例如一条用户订阅的数据
- **冗余**：储存两倍数据，冗余降低了性能，但提高了数据的安全性
- **主键**：主键是唯一的。。一个数据表中只能包含一个主键。你可以使用主键来查询数据
- **外键**：关键用于关联两个表。
- **复合键**：复合见将多个列作为一个索引键，一般用于复合索引
- **索引**：使用索引可以快速访问数据库表中的特定信息。索引是对数据库表中的一列或者多列的值进行排序的一种结构。类似于书籍的目录
- **参照完整性**：参照的完整性要求关系中不允许引用不存在的实体。与实体完整性是关系模型必须满足的完整性条件约束，目的是保证数据的一致性

## SQL-数据库语言

SQL代表结构化查询预言（structured Query Language）。sql是用于访问数据库的标准化预言

SQL包含三个部分：
- 数据库定义预言包含定义数据库及其对象的语句，例如表，师徒，触发器，储存过程
- 数据操作预言包含允许跟新和查询数据的预言
- 数据控制预言允许授予用户权限访问数据库中特定的数据权限

## MySAL 用户设置

如果我需要添加Mysql用户，你只需要在mysql数据库中的user表添加新用户即可

```bash
oot@host# mysql -u root -p
Enter password:*******
mysql> use mysql;
Database changed

mysql> INSERT INTO user 
          (host, user, password, 
           select_priv, insert_priv, update_priv) 
           VALUES ('localhost', 'guest', 
           PASSWORD('guest123'), 'Y', 'Y', 'Y');
Query OK, 1 row affected (0.20 sec)

mysql> FLUSH PRIVILEGES;
Query OK, 1 row affected (0.01 sec)

mysql> SELECT host, user, password FROM user WHERE user = 'guest';
+-----------+---------+------------------+
| host      | user    | password         |
+-----------+---------+------------------+
| localhost | guest | 6f8c114b58f2ce9e |
+-----------+---------+------------------+
1 row in set (0.00 sec)
```

## /etc/mt.cnf 文件配置
一般情况下，不需要修改配置文件，该文件的默认配置如下

```bash
[mysqld]
datadir=/var/lib/mysql
socket=/var/lib/mysql/mysql.sock

[mysql.server]
user=mysql
basedir=/var/lib

[safe_mysqld]
err-log=/var/log/mysqld.log
pid-file=/var/run/mysqld/mysqld.pid
```

## 管理MySQL的命令

- **USE 数据库名**
选择要操作的Mysql数据库，使用该命令猴所有的MYqsl命令都只针对该数据库。

- **SHOW DATABASWS**
列出MySQL数据库管理系统的数据列表。

- **SHOW TABLES**
显示指定数据库的所有表，使用该命令钱需要使用use命令来选择要操作的数据库


