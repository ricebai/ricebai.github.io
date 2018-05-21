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
declare v_number number(10);
        v_char varchar2(20);
```

#### 带默认值

``` SQL
declare v_number number(10) := 10;
        v_char varchar2(20) := 'ABC';
```

### 数组变量

#### 非自增声明

定义一个 `name_arr` 数组类型，`varchar2(10)` 字符类型长度为10。

``` SQL
type name_arr is table of varchar2(10);
```

``` SQL
declare
  type name_arr is table of varchar2(10);
  -- 初始化数组
  names name_arr := name_arr();
begin
  --
  names.extend;
  names(1) := 'AAA';
  names.extend;
  names(2) := 'BBB';
end;
```


#### 自增声明

　　增加 `index by binary_integer` 后，numbers 类型的下表自增长。可以自动根据下标找到对应的值。numbers 类型在插入元素时，不需要初始化，不需要每次 `extend` 增加一个空间。


``` SQL
type name_arr is table of varchar2(10) index by binary_integer;
```
