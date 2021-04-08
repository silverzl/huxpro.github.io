---
layout:     post
title:      "数据库 SQL基础"
subtitle:   "DATABASE"
date:       2021-3-26 11:00:00
author:     "zl"
header-img: "img/post-bg-2019.jpg"
tags:
    - 数据库
---

## 入门

### Where语句

>SELECT * FROM Persons WHERE City='Beijing'


### insert语句

在 LastName Address两列，插入wilson cham-ely数据

>INSERT INTO Persons (LastName, Address) VALUES ('Wilson', 'Champs-Elysees')

### updata语句

更新某一行中的若干列：

修改地址，添加城市名：

> UPDATE Person **SET** Address = 'Zhongshan 23', City = 'Nanjing'
**WHERE LastName = 'Wilson'**

### DELET语句

删除某行：

> DELETE FROM Person WHERE LastName = 'Wilson' 

### distinct语句

去掉相同值，只返回不同值

>SELECT DISTINCT Company FROM Orders 

### order by 语句

以字母顺序显示,并以数字顺序显示序列号，降序排列(DESC)

>SELECT Company, OrderNumber FROM Orders ORDER BY Company,OrderNumber **DESC**

在字母顺序相同时，以数字顺序显示 


### top子句

返回person表中头两条子句

> SELECT TOP 2 * FROM Persons

选取50%记录

>SELECT TOP 50 PERCENT * FROM Persons

### 通配符 与 like运算符

必须与like运算符一起使用

- % ： 代替一个或多个字符

> SELECT * FROM Persons
WHERE City LIKE '%lond%'

选取person表中城市列 包含"lond"的人

- _ ：仅仅代替一个字符

>SELECT * FROM Persons
WHERE FirstName LIKE '_eorge'

选firstname 第一个字符之后是eorge的人

- [ ] ： 字符串中任何一个单个字符 （正则中的或[]）

> SELECT * FROM Persons
WHERE City LIKE '[ ALN ]%'

选取城市名以 A 或 L 或 N开头的的人


- [! ]:  不再字符串中的任何一个单个字符

> SELECT * FROM Persons
WHERE City LIKE '[ ALN ]%'

选取城市名以 A 或 L 或 N开头的的人

###  in操作符，between操作符，

IN 操作符允许我们在 WHERE 子句中规定多个值。

>SELECT * FROM Persons
WHERE LastName IN ('Adams','Carter')

选取 lastname中有adams与carter的人

between 操作符

between...and... 选取包含的值，这些值可以是数值，文本或日期

> SELECT * FROM Persons
WHERE LastName
BETWEEN 'Adams' AND 'Carter'

选取以字母顺序 结于adams与carter之间的人。

  


