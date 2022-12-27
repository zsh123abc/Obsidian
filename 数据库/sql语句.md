创建数据库
创建一个叫db1的数据库MySQL命令：

create database db1;

删除数据库MySQL命令：
drop database db1;

创建数据库后查看该数据库基本信息MySQL命令：
show  database db1;

查询出MySQL中所有的数据库MySQL命令：
show databases;

将数据库的字符集修改为gbk MySQL命令：
alter database db1 character set gbk;

切换数据库 MySQL命令：
use db1;

查看当前使用的数据库 MySQL命令：
select database();



INSERT – 插入数据
插入新的行
```sql
INSERT INTO Persons VALUES (1, 'Gates', 'Bill', 'Xuanwumen 10', 'Beijing');
```
在指定的列中插入数据
```sql
INSERT INTO Persons (LastName, Address) VALUES ('Wilson', 'Champs-Elysees');
```


SELECT – 查询数据
查询表中所有数据
```sql
SELECT * FROM Persons;
```
查询表中指定列的数据
```sql
SELECT LastName,FirstName FROM Persons;
```


UPDATE – 更新数据：
(更新操作时可能报1175错误，解决办法：降低安全等级)
```SQL
set sql_safe_updates =0;
```
更新某一行中的一个列：
```sql
UPDATE Persons SET FirstName = 'Fred' WHERE LastName = 'Wilson';
```
更新某一行中的若干列：
```sql
UPDATE Persons SET ID_P = 6,city= 'London' WHERE LastName = 'Wilson';
```


DELETE – 删除数据：
删除某行：
```sql
DELETE FROM Persons WHERE LastName = 'Wilson';
```
删除所有行：
```sql
DELETE FROM table_name;
```