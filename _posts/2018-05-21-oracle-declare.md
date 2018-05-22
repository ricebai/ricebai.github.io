---
layout:     post
title:      Oracle Declare 变量声明
subtitle:   Oracle Declare 变量声明和使用
date:       2018-05-21
author:     ricebai
header-img: img/posts/plsql/post-bg-plsql.png
catalog: true
tags:
    - Oracle
---

# DECLARE

`declare` 在 Oracle 一般是用在函数、存储过程和块结构及简单的事务中。

### 普通变量

#### 声明

``` SQL
declare v_number number(10); -- 长度10
        v_char varchar2(20); -- 长度20
```

#### 带默认值

``` SQL
declare v_number number(10) := 10; -- 长度10
        v_char varchar2(20) := 'ABC'; -- 长度20
```

### 数组变量

在 ORQCLE 中的数组变量都是以 1 为初始下标，并不是 0。

#### 非自增声明

定义一个 `name_arr` 数组类型，`varchar2(10)` 字符类型长度为10。

``` SQL
type name_arr is table of varchar2(10);
```

初始化数组。

``` SQL
-- 初始化数组
names name_arr := name_arr();
```

示例如下，在未设置 `index by binary_integer` 情况下，必须初始化数组并每次调用 `names.extend` 手动增加数组空间。

``` SQL
declare
  type name_arr is table of varchar2(10);
  -- 初始化数组
  names name_arr  := name_arr();
begin
  -- 增加数组空间
  names.extend;
  names(1) := 'AAA';
  names.extend;
  names(2) := 'BBB';
end;
```

`.extend` 还可以直接定义创建的空间数。

``` SQL
declare
  type name_arr is table of varchar2(10);
  -- 初始化数组
  names name_arr  := name_arr();
begin
  -- 增加 2 个数组空间
  names.extend(2);
  names(1) := 'AAA';
  names(2) := 'BBB';
end;
```

初始化带默认值数组。

``` SQL
-- 初始化带默认值数组
names name_arr := name_arr('AAA','BBB');
```

示例如下。

``` SQL
declare
  type name_arr is table of varchar2(10);
  -- 初始化数组
  names name_arr  := name_arr('AAA','BBB');
begin
  for i in 1 .. names.count
  loop
    -- 循环输出
    dbms_output.put_line('name :' || names(i));
  end loop;
end;
```

#### 自增声明

增加 `index by binary_integer` ， 下标自增长。

``` SQL
type name_arr is table of varchar2(10) index by binary_integer;
```

示例如下，使用后无需初始化 `:= name_arr();` 和 `.extend` 增加数组空间。

``` SQL
declare
  type name_arr is table of varchar2(10) index by binary_integer;
  names name_arr;
begin
  -- 赋值
  names(1) := 'AAA';
  names(2) := 'BBB';

  for i in 1 .. names.count
  loop
    -- 循环输出
    dbms_output.put_line('name :' || names(i));
  end loop;
end;
```

### 查询赋值

这种查询赋值必须使用 `index by binary_integer` 下标自增长实现。

``` SQL
declare
  type name_arr is table of varchar2(10)  index by binary_integer;
  names name_arr ;
begin
  -- 将字段 name 数据集合存放在 names 变量中
  select a.name
    bulk collect into names
  from my_tabel a;

  for i in 1 .. names.count
  loop
    -- 循环输出
    dbms_output.put_line('name :' || names(i));
  end loop;
end;
```

### 多信息封装

#### 定义

定义数据类型为 `user_info`，创建子类型：`u_name`、`u_age`、`u_sex`。

``` SQL
declare
type user_info is record(
    u_name varchar2(20),
    u_age  number(3),
    u_sex  varchar2(5));
```

#### 声明

声明 `user_info_arr` 自定义可自增数据数组类型。

``` SQL
type user_info_arr is table of user_info index by binary_integer;
```
#### 示例

``` SQL
declare
type user_info is record( -- 定义user_info 数据类型
    u_name varchar2(20),
    u_age  number(3),
    u_sex  varchar2(5));

 -- 声明 user_info_arr 数组类型
 type user_info_arr is table of user_info index by binary_integer;

 -- 创建 user_infos 数组变量
  user_infos user_info_arr;
begin

  user_infos(1).u_name := 'AAA';
  user_infos(1).u_age := '19';
  user_infos(1).u_sex := '女';

 for i in 1 .. user_infos.count
  loop
    -- 输出
    dbms_output.put_line('name :' || user_infos(i).u_name);
    dbms_output.put_line('age :' || user_infos(i).u_age);
    dbms_output.put_line('sex :' || user_infos(i).u_sex);
  end loop;
end;
```
