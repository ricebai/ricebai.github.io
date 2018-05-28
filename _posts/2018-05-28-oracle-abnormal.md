---
layout:     post
title:      Oracle 异常
subtitle:   Oracle 异常的分类与使用
date:       2018-05-21
author:     ricebai
header-img: img/posts/plsql/post-bg-plsql.png
catalog: true
tags:
    - Oracle
---

# 异常

异常情况处理( EXCEPTION )是用来处理正常执行过程中未预料的事件,程序块的异常处理预定义的错误和自定义错误,由于 PL/SQL 程序块一旦产生异常而没有指出如何处理时,程序就会自动终止整个程序运行。

Oracle 异常错误传播:

- 在执行部分引发异常错误
- 在声明部分引发异常错误


### 预定义异常

预定义错误，ORACLE预定义的异常情况大约有24个。对这种异常情况的处理，无需在程序中定义，由ORACLE自动将其引发。

> 预定义说明的部分 ORACLE 异常错误

<TABLE WIDTH="100%">
  <TR>
    <TD WIDTH="120">错误号</TD>
    <TD>异常错误信息名称</TD>
    <TD>说明</TD>
  </TR>
  <TR>
    <TD>ORA-0001</TD>
    <TD>DUP_VAL_ON_INDEX</TD>
    <TD>违反了唯一性限制</TD>
  </TR>
  <TR>
    <TD>ORA-0051</TD>
    <TD>TIMEOUT-ON-RESOURCE</TD>
    <TD>在等待资源时发生超时</TD>
  </TR>
  <TR>
    <TD>ORA-0061</TD>
    <TD>TRANSACTION-BACKED-OUT</TD>
    <TD>由于发生死锁事务被撤消</TD>
  </TR>
  <TR>
    <TD>ORA-1001</TD>
    <TD>INVALID-CURSOR</TD>
    <TD>试图使用一个无效的游标</TD>
  </TR>
  <TR>
    <TD>ORA-1012</TD>
    <TD>NOT-LOGGED-ON</TD>
    <TD>没有连接到ORACLE</TD>
  </TR>
  <TR>
    <TD>ORA-1017</TD>
    <TD>LOGIN-DENIED</TD>
    <TD>无效的用户名/口令</TD>
  </TR>
  <TR>
    <TD>ORA-1403</TD>
    <TD>NO_DATA_FOUND</TD>
    <TD>SELECT INTO没有找到数据</TD>
  </TR>
  <TR>
    <TD>ORA-1422</TD>
    <TD>TOO_MANY_ROWS</TD>
    <TD>SELECT INTO 返回多行</TD>
  </TR>
  <TR>
    <TD>ORA-1476</TD>
    <TD>ZERO-DIVIDE</TD>
    <TD>试图被零除</TD>
  </TR>
  <TR>
    <TD>ORA-1722</TD>
    <TD>INVALID-NUMBER</TD>
    <TD>转换一个数字失败</TD>
  </TR>
  <TR>
    <TD>ORA-6500</TD>
    <TD>STORAGE-ERROR</TD>
    <TD>内存不够引发的内部错误</TD>
  </TR>
  <TR>
    <TD>ORA-6501</TD>
    <TD>PROGRAM-ERROR</TD>
    <TD>内部错误</TD>
  </TR>
  <TR>
    <TD>ORA-6502</TD>
    <TD>VALUE-ERROR</TD>
    <TD>转换或截断错误</TD>
  </TR>
  <TR>
    <TD>ORA-6504</TD>
    <TD>ROWTYPE-MISMATCH</TD>
    <TD>宿主游标变量与 PL/SQL变量有不兼容行类型</TD>
  </TR>
  <TR>
    <TD>ORA-6511</TD>
    <TD>CURSOR-ALREADY-OPEN</TD>
    <TD>试图打开一个已处于打开状态的游标</TD>
  </TR>
  <TR>
    <TD>ORA-6530</TD>
    <TD>ACCESS-INTO-NULL</TD>
    <TD>试图为NULL 对象的属性赋值</TD>
  </TR>
  <TR>
    <TD>ORA-6531</TD>
    <TD>COLLECTION-IS-NULL</TD>
    <TD>试图将EXISTS 以外的集合( COLLECTION)方法应用于一个NULL PL/SQL 表上或VARRAY上</TD>
  </TR>
  <TR>
    <TD>ORA-6532</TD>
    <TD>SUBSCRIPT-OUTSIDE-LIMIT</TD>
    <TD>对嵌套或VARRAY索引得引用超出声明范围以外</TD>
  </TR>
  <TR>
    <TD>ORA-6533</TD>
    <TD>SUBSCRIPT-BEYOND-COUNT</TD>
    <TD>对嵌套或VARRAY 索引得引用大于集合中元素的个数.</TD>
  </TR>
</TABLE>

#### 示例

通过 `id` 查询表数据，并捕获 `ORA-1403` 错误。

``` SQL
declare
  -- 定义变量
  v_no demo_budget.pid%type ;
begin
  -- 查询值
  select pid INTO v_no from demo_budget where id = 'B' ;
exception
  -- ORA-1403 错误
  when no_data_found then
       dbms_output.put_line('v_no is null!');
end;
```

### 非预定义异常

非预定义错误，将其定义好的异常与标准的 ORACLE 错误关联起来，使用 `exception_init` 语句。

#### 语法

pragma exception_init(异常, SQL错误代码);

#### 示例

``` SQL
declare

  -- 定义变量
  v_no demo_budget.pid%type;

  -- 自定义异常
  e_1403 exception;

  -- ora-1403 对应sqlcode 100
  -- 将 e_1403 与 ora-1403 错误关联起来
  pragma exception_init(e_1403, 100);
begin

  -- 查询值
  select pid into v_no from demo_budget where id = 'B';
exception

  -- ora-1403 错误
  when e_1403 then
    dbms_output.put_line('1403 error !');
end;
```

### 用户定义异常

用户定义错误是通过显式使用 `raise` 语句来触发。当引发一个异常错误时，控制就转向到 `exception` 块异常错误部分执行错误处理代码。

#### 示例

``` SQL
declare
  -- 自定义异常
  e_result exception;
begin
  -- 查询值
  update demo_budget set pid = 'A' where id = 'B';

  -- 判断
  if sql%notfound then
    -- 触发异常
    raise e_result;
  end if;

  exception
  when e_result then
       dbms_output.put_line('not find result !');
end;
```

#### sql%

`sql%notfound` 是一个布尔值。与最近的sql语句（`update`，`insert`，`delete`，`select`）发生交互，当最近的一条sql语句没有涉及任何行的时候，则返回 `true`。否则返回 `false`。这样的语句在实际应用中，是非常有用的。

`sql%found` 的用法与 `sql%notfound` 用法相反，也是与最近的 sql 语句发生交互，如果影响行数大于 0 条，则为 `true` 否则为 `false`。

`sql%rowcount` 在 dml 语句执行前是 null，执行后，对于 `select into` 语句，执行成功则值为 1，不成功则值为 0。
