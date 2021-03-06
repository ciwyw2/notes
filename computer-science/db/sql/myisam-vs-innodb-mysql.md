# MyISAM vs InnoDB: mysql 的两种存储引擎的区别


wp_id: 172
Status: publish
Date: 2018-03-27 16:50:51
Modified: 2020-05-16 11:31:08


* InnoDB 有行级别的锁，而 MyISAM 只能锁定到表级别。
* InnoDB 有更好的故障恢复机制.
* InnoDB 实现了事务、外键和关系限制, MyISAM 没有.

总的来说，引用完整性和事物才是数据库的本质，所以说：“MyISAM is a file system that understands SQL. There’s no comparison. If you want a database engine with MySQL, use InnoDB.”

## 聚簇索引

MyISAM 没有使用聚簇索引，InnoDB 使用了聚簇索引。

## 参考

1. https://dba.stackexchange.com/questions/1/what-are-the-main-differences-between-innodb-and-myisam

2. https://jeremystein.com/journal/innodb-versus-myisam-no-comparison/