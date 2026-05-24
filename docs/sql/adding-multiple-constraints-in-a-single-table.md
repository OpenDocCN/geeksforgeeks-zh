# 在单个表中添加多个约束

> 原文:[https://www . geesforgeks . org/add-多约束单表/](https://www.geeksforgeeks.org/adding-multiple-constraints-in-a-single-table/)

**先决条件–**[SQL 约束](https://www.geeksforgeeks.org/sql-constraints/)

我们可以创建一个列中有多个约束的表。下面的例子展示了我们如何在一个表上定义不同的约束。

**在创建命令中添加约束:**

*   Sr_no 是主键。
*   分支编号是引用分支表的外键。
*   公司类型将包含以下值之一:“1C”、“2C”、“3C”

**语法:**

```sql
Create table Fd_master(Sr_no varchar2(10), 
Branch_no varchar2(10), account_no varchar2(20),
company_type varchar2(20), constraint pk primary key(Sr_no),  
constraint fk foreign key (Branch_no) references Branch,
constraint chk check(company_type in (‘1C’, ’2C’, ’3C’)));
```

1.  **主键约束–**
    Fd _ master 中的 Sr_no，其中 pk 是用户定义的给主键的名称。
2.  **外键约束–**
    Fd _ master 中的分支号，其中 fk 是引用分支表的外键的名称。
3.  **检查约束–**
    Fd _ master 中的公司类型，其中 chk 是将检查给定值的名称，即“1C”、“2C”、“3C”

**在 alter 命令中添加约束:**
可以通过 Alter 命令添加多列级约束。可以按顺序添加到父子表中。

**约束 1(默认):**
创建两个表–

*   对默认值为 1 的标识具有默认约束的父级。给约束的名称是 DF_ParentTable。
*   带有标识列的外部表。

两个表中的标识都为“非空”。

**语法:**

```sql
CREATE TABLE ParentTable (ID int not null constraint DF_ParentTable default (1), 
name varchar2(5));
```

```sql
CREATE TABLE ForeignTable (ID int not null, Col2 VARCHAR(5));
```

**约束 2(检查):**

```sql
ALTER TABLE ParentTable ADD CONSTRAINT CK_ParentTable_ID CHECK(ID<100);
```

**约束 3(外键):**
外键

```sql
ALTER TABLE ParentTable 
ADD CONSTRAINT FK_parent_foreign FOREIGN KEY (ID) REFERENCES ForeignTable(ID);
```