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

|错误号|异常错误信息名称|说明|
|:-|:-|:-|
|ORA-0001|Dup_val_on_index|违反了唯一性限制|
|ORA-0051|Timeout-on-resource|在等待资源时发生超时|
|ORA-0061|Transaction-backed-out|由于发生死锁事务被撤消|
|ORA-1001|Invalid-CURSOR|试图使用一个无效的游标|
|ORA-1012|Not-logged-on|没有连接到ORACLE|
|ORA-1017|Login-denied|无效的用户名/口令|
|ORA-1403|No_data_found|SELECT INTO没有找到数据|
|ORA-1422|Too_many_rows|SELECT INTO 返回多行|
|ORA-1476|Zero-divide|试图被零除|
|ORA-1722|Invalid-NUMBER|转换一个数字失败|
|ORA-6500|Storage-error|内存不够引发的内部错误|
|ORA-6501|Program-error|内部错误|
|ORA-6502|Value-error|转换或截断错误
|ORA-6504|Rowtype-mismatch|宿主游标变量与 PL/SQL变量有不兼容行类型|
|ORA-6511|CURSOR-already-OPEN|试图打开一个已处于打开状态的游标|
|ORA-6530|Access-INTO-null|试图为null 对象的属性赋值|
|ORA-6531|Collection-is-null|试图将Exists 以外的集合( collection)方法应用于一个null pl/sql 表上或varray上|
|ORA-6532|Subscript-outside-limit|对嵌套或varray索引得引用超出声明范围以外|
|ORA-6533|Subscript-beyond-count|对嵌套或varray 索引得引用大于集合中元素的个数.|

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
