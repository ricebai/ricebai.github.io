---
layout:     post
title:      Oracle 包
subtitle:   Oracle 包和包体以及与非包体定义函数、过程的区别
date:       2018-06-01
author:     ricebai
header-img: img/posts/plsql/post-bg-plsql.png
catalog: true
tags:
    - Oracle
---

# Package

包是一组相关过程、函数、变量、常量#SinaEditor_Temp_FontName、类型和游标等PL/SQL程序设计元素的组合。包具有面向对象设计的特点，是对这些PL/SQL程序设计元素的封装。

一个包由两个分开的部分组成：  

- 包，定义部分是创建包的规范说明，声明包内 [数据类型、变量、常量](https://ricebai.github.io/2018/05/21/oracle-declare/#declare)、游标等元素。这部分也是为使用者提供了透明的接口。
- 包体，是包定义部分的具体实现。

### 包

创建 `pgk_test` 包，并声明一个存储过程 `p_print`。

``` SQL
create or replace package pgk_test
is
    -- 定义一个存储过程
    procedure p_print;
end pgk_test;
```

### 包体

创建 `pgk_test` 包体，并实现存储过程 `p_print`。

``` SQL
create or replace package body pgk_test
is
    -- 实现存储过程
    procedure p_print
    is
    begin
        -- 输出
        dbms_output.put_line('hello package !');
    end p_print;

end;
```

### 运行

``` SQL
begin
  pgk_test.p_print;
end;
```

结果

![sql](https://ricebai.github.io/img/posts/oracle-package/1.jpg)

### 进阶

熟悉上面的简单介绍后，我们来看下面这个包。

创建包 `pgk_test`, 声明全局变量、存储过程、函数。

创建 `pgk_test` 包体，实现存储过程、实现函数。

``` SQL
-- 创建包
create or replace package pgk_test
is
    -- 声明全局变量
    v_a number ;
    -- 声明存储过程
    procedure p_set (i_a in number);
    -- 声明函数
    function f_add (i_b in number) return number;
end pgk_test;
/ -- 斜杠
-- 创建包体
create or replace package body pgk_test
is
    -- 实现存储过程
    procedure p_set(i_a in number)
    is
    begin
        if nvl(i_a, 0) > 0 then
          v_a := i_a;
        else
          v_a := 100;
        end if;
        dbms_output.put_line('赋值：'||v_a);
    end p_set;
    -- 实现函数
    function f_add (i_b in number) return number
    is
      v_result number;
    begin
       v_result := v_a + i_b;
       return v_result;
    end f_add;
end;
/ -- 斜杠
```

运行

``` SQL
begin
  -- 参数 null
  pgk_test.p_set(null);
  -- 参数 10
  pgk_test.p_set(10);
  -- 运行函数
  dbms_output.put_line('结果：'||pgk_test.f_add(5));
end;
```

结果

![sql](https://ricebai.github.io/img/posts/oracle-package/2.jpg)
