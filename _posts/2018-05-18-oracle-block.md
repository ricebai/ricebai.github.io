---
layout:     post
title:      Oracle 语句块
subtitle:   Oracle Begin...End 语句块、IF 的应用
date:       2018-05-18
author:     ricebai
header-img: img/posts/plsql/post-bg-plsql.png
catalog: true
tags:
    - Oracle
---

### 语句块

#### 逻辑运算符

|运算符|说明|运算符|说明|
| :- | :- | :- | :- |
| = | 等于 | >|大于|
|<> |	不等于	|<=	|小于等于|
|<	|小于	|>=	|大于等于|

#### 组成

语句块由 `begin` ... `end` 组成。

```SQL
begin
    dbms_output.put_line('这是语句块');
end;
```

语句块中也可以包含多条 SQL 语句顺序执行。

```SQL
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

语句块中使用 `if` 组合使用逻辑运算符判断一个条件是否成立。

`set serveroutput on` 这个只能在 SQL PLUS 里面使用，意思是在窗口里显示服务器输出信息。

```SQL
-- 窗口中输出信息
set serveroutput on
declare
    -- 定义带默认值变量
    v_name varchar2(1) := 'A';
begin
    -- 判断 v_name 是否等于字符 A
    if v_name = 'A' then
        -- 判断成功
        dbms_output.put_line('v_name 等于 A');
    end if;
end;
```

运行结果

![=a](https://ricebai.github.io/img/posts/oracle-block/=a.jpg)

#### ELSE

在语句块中，`if` 条件不成立则会进入 `else`。

```SQL
declare
    -- 定义带默认值变量
    v_name varchar2(1) := 'B';
begin
    -- 判断 v_name 是否等于字符 A
    if v_name = 'A' then
        -- 判断成功
        dbms_output.put_line('v_name 等于 A');
    else
        -- 判断失败
        dbms_output.put_line('v_name 不等于 A');
    end if;
end;
```

运行结果

![!=a](https://ricebai.github.io/img/posts/oracle-block/!=a.jpg)

当然也有 `elsif` 判断多次。

```SQL
declare
    -- 定义带默认值变量
    v_name varchar2(1) := 'B';
begin
    -- 判断 v_name 是否等于字符 A
    if v_name = 'A' then
        dbms_output.put_line('v_name 等于 A');
    -- 判断 v_name 是否等于字符 B
    elsif v_name = 'B' then
        dbms_output.put_line('v_name 等于 B');
    end if;
end;
```

运行结果

![=b](https://ricebai.github.io/img/posts/oracle-block/=b.jpg)
