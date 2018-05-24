---
layout:     post
title:      Oracle 语句块和存储过程
subtitle:   Oracle Begin...End 语句块、IF 与存储过程的应用
date:       2018-05-18
author:     ricebai
header-img: img/posts/plsql/post-bg-plsql.png
catalog: true
tags:
    - Oracle
---

### 语句块

#### 组成

语句块由 `begin` ... `end` 组成。

``` SQL
begin
    dbms_output.put_line('这是语句块');
end;
```

语句块可以包含多条 SQL 语句，顺序处理。

``` SQL
declare
    v_name varchar2(50); -- 定义变量
begin
    -- 查询动态获得值
    select t1.name into v_name -- 查询赋值
      from t_table t1
    where t1.id = '31';

    -- 执行更新操作
    update t_table t2
      set t2.no = '测试32'
    where t2.name = v_name; -- 调用变量
end;
```

#### IF

语句块中使用 `if` ... `else`

``` SQL



```

#### 逻辑符

语句块中使用逻辑符

``` SQL



```
