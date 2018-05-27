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

预定义 ( Predefined )错误，ORACLE预定义的异常情况大约有24个。对这种异常情况的处理，无需在程序中定义，由ORACLE自动将其引发。

> 预定义说明的部分 ORACLE 异常错误

<table width="100%">
  <tr>
    <td width="120">错误号</td>
    <td>异常错误信息名称</td>
    <td>说明</td>
  </tr>
  <tr>
    <td>ORA-0001</td>
    <td>Dup_val_on_index</td>
    <td>违反了唯一性限制</td>
  </tr>
  <tr>
    <td>ORA-0051</td>
    <td>Timeout-on-resource</td>
    <td>在等待资源时发生超时</td>
  </tr>
  <tr>
    <td>ORA-0061</td>
    <td>Transaction-backed-out</td>
    <td>由于发生死锁事务被撤消</td>
  </tr>
  <tr>
    <td>ORA-1001</td>
    <td>Invalid-CURSOR</td>
    <td>试图使用一个无效的游标</td>
  </tr>
  <tr>
    <td>ORA-1012</td>
    <td>Not-logged-on</td>
    <td>没有连接到ORACLE</td>
  </tr>
  <tr>
    <td>ORA-1017</td>
    <td>Login-denied</td>
    <td>无效的用户名/口令</td>
  </tr>
  <tr>
    <td>ORA-1403</td>
    <td>No_data_found</td>
    <td>SELECT INTO没有找到数据</td>
  </tr>
  <tr>
    <td>ORA-1422</td>
    <td>Too_many_rows</td>
    <td>SELECT INTO 返回多行</td>
  </tr>
  <tr>
    <td>ORA-1476</td>
    <td>Zero-divide</td>
    <td>试图被零除</td>
  </tr>
  <tr>
    <td>ORA-1722</td>
    <td>Invalid-NUMBER</td>
    <td>转换一个数字失败</td>
  </tr>
  <tr>
    <td>ORA-6500</td>
    <td>Storage-error</td>
    <td>内存不够引发的内部错误</td>
  </tr>
  <tr>
    <td>ORA-6501</td>
    <td>Program-error</td>
    <td>内部错误</td>
  </tr>
  <tr>
    <td>ORA-6502</td>
    <td>Value-error</td>
    <td>转换或截断错误</td>
  </tr>
  <tr>
    <td>ORA-6504</td>
    <td>Rowtype-mismatch</td>
    <td>宿主游标变量与 PL/SQL变量有不兼容行类型</td>
  </tr>
  <tr>
    <td>ORA-6511</td>
    <td>CURSOR-already-OPEN</td>
    <td>试图打开一个已处于打开状态的游标</td>
  </tr>
  <tr>
    <td>ORA-6530</td>
    <td>Access-INTO-null</td>
    <td>试图为null 对象的属性赋值</td>
  </tr>
  <tr>
    <td>ORA-6531</td>
    <td>Collection-is-null</td>
    <td>试图将Exists 以外的集合( collection)方法应用于一个null pl/sql 表上或varray上</td>
  </tr>
  <tr>
    <td>ORA-6532</td>
    <td>Subscript-outside-limit</td>
    <td>对嵌套或varray索引得引用超出声明范围以外</td>
  </tr>
  <tr>
    <td>ORA-6533</td>
    <td>Subscript-beyond-count</td>
    <td>对嵌套或varray 索引得引用大于集合中元素的个数.</td>
  </tr>
</table>

### 非预定义异常

非预定义 ( Predefined )错误，即其他标准的ORACLE错误。对这种异常情况的处理，需要用户在程序中定义，然后由ORACLE自动将其引发。

### 用户定义异常

用户定义(User_define) 错误，程序执行过程中，出现编程人员认为的非正常情况。对这种异常情况的处理，需要用户在程序中定义，然后显式地在程序中将其引发。

异常处理部分一般放在 PL/SQL 程序体的后半部,结构为:

``` SQL
exception
   when first_exception then  
   when second_exception then  
   when others then  
end;
```
