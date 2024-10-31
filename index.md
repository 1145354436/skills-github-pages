---
title: Welcome to my blog
---
2024-10-29
# 一、表结构
## （一）创建表结构
### 1.数据类型
#### （1）整数数据类型：
    int,bigint,smallint,tinyint
#### （2）小数数据类型：
    real,float，decimal(p,s)/numeric(p,s)
        1）p:总位数;	s:小数点位数
        2）decimal(5,2)
#### （3）字符数据类型：
    char(n),varchar(n|max)(最大200),nchar(n)，nvarchar(n|max)
        1）char(n):固定长度
        2）varchar(n):可变长度
#### （4）日期和时间数据类型：
    date，time，datetime，datetime2，smalldatetime
#### （5）文本和图形数据类型：
    text，ntext，image
#### （6）货币数据类型：
    money，smallmoney
#### （7）位数据类型：
    bit，只取0或1，True(1),False(0)
#### （8）二进制数据类型：
    binary(n)，varbinary(n|max)
#### （9）其他数据类型：
    rowversion，timestamp
### 2.格式
    use 数据库名
    create table 表名
    (
    列名1 数据类型(长度) not null/null,
    列名2 数据类型(长度) not null/null,
    列名3 数据类型(长度) not null/null
    )
### 3.例子
```
use Mewio
create table st
(
snum  char(10) not null,
sname char(10) not null,
sex bit null,
sbirthday date not null
)
```
## （二）查看表结构
### 1.格式
    exec sp_help 表名
### 2.例子
```
exec sp_help st
```
## （三）查看表数据
### 1.格式
    select * from 表名
### 2.例子    
```
select * from st
```
## （四）修改表结构
### 1.添加列
#### （1）格式
    alter table 表名
    add 列名 数据类型(长度) not null/null
#### （2）例子
```
alter table st
add sphone char(11) not null
```
### 2.修改列属性（数据类型，长度，是否为空）
#### （1）格式
    alter table 表名
    alter column 列名 新的数据类型(新的长度) not null/null
#### （2）例子
```
alter table st
alter column sname varchar(8) null
```
### 3.删除列
#### （1）格式
    alter table 表名
    drop column 列名
#### （2）例子
```
alter table st
drop column sex
```
## （五）复制表结构
### 1.mysql
#### （1）格式
    creat table 新表名
    as
    select * from 源表名
### 2.Sql Server
#### （1）格式
    1）select * into 新表名 from 源表名
    2）select * into 新表名 from 源表名 where 1=2(条件为假就行)
#### （2）例子    
```
1）select * into st from xsb
2）select * into st from xsb where 1=2

```
### 3.跨数据库表的复制
#### （1）格式
    use 目标数据库名
    select * into 目标表名 from 源数据库..源表名
#### （2）例子
```
--teacher下的course表-->Mewio
use Mewio
select * into course from teacher..course
```
## （六）删除表结构
### 1.格式
    drop table 表名
### 2.例子
```
drop table st
```
# 二.约束
# 三.表数据

