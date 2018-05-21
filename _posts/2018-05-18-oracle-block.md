---
layout:     post
title:      Oracle Begin...End 语句块
subtitle:   Oracle Begin...End 语句块的使用
date:       2018-05-18
author:     ricebai
header-img: img/posts/plsql/post-bg-plsql.png
catalog: true
tags:
    - Oracle
---

### 语句块

`begin` ... `end` 块结构 SQL

``` SQL
declare
    v_id varchar2(50); -- 定义变量
    v_no varchar2(50);

begin
    v_id := '31'; -- 变量赋值

    select t1.supplier_no into v_no -- 查询赋值
      from srm_supplier t1
    where t1.id = '31';

    update srm_supplier t2
      set t2.supplier_name = '测试32'
    where t2.supplier_no = v_no; -- 调用变量
end;
```
