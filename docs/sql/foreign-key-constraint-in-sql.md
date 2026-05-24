# SQL 中的外键约束

> 原文:[https://www . geesforgeks . org/foreign-key-constraint-in-SQL/](https://www.geeksforgeeks.org/foreign-key-constraint-in-sql/)

[外键](https://practice.geeksforgeeks.org/problems/what-is-a-foreign-key)是指其他表的主键/唯一键的列。因此，它展示了表之间的关系，并充当它们之间的交叉引用。定义了外键的表称为外键表/引用表。定义主键/唯一键并被外键引用的表称为主键表/主表/被引用表。它在创建表/更改表语句中定义。

对于包含外键的表，每行都应该与引用表中的主键匹配。这被称为参照完整性。外键确保引用完整性。

**属性:**

*   被引用的父项必须是唯一的/主键。
*   子级可能有重复项和空项。
*   如果不存在子记录，可以删除父记录。
*   如果存在子表，则无法更新主表。
*   必须引用主键表中的主键。
*   外键列和约束列应该具有匹配的数据类型。
*   如果主表中相应的记录不存在，则不能在子表中插入记录。
*   如果子表中相应的记录存在，则不能删除主表的记录。

1.  **SQL Foreign key At column level :**

    **语法–**

    ```sql
    Create table people (no int references person, 
                              Fname varchar2(20));
                    OR
    Create table people (no int references person(id), 
                                  Fname varchar2(20));            

    ```

    此处人员表应该具有类型为 int 的主键。如果表中只有一个列主键，语法中的列名可以省略。所以以上两种语法都是正确的。

    要检查约束，

    *   如果父表没有主键。

        ```sql
        OUTPUT : 
        Error at line 1 : referenced table does not have a primary key.

        ```

    *   如果父表具有不同数据类型的主键。

        ```sql
        OUTPUT : 
        Error at line 1 : column type incompatible with referenced column type.

        ```

2.  **SQL Foreign key At table level :**

    **语法–**

    ```sql
    create table people(no varchar2(10), 
                         fname varchar2(20), 
                         foreign key(no) references person);
                            OR
    create table people(no varchar2(10), 
                         fname varchar2(20), 
                         foreign key(no) references person(id));

    ```

    引用表的列名可以忽略。

3.  **外键表中的插入操作:**
    如果外键表中没有对应的值，则不能插入子表中的记录。

    ```sql
    OUTPUT : 
    Error at line 1 : integrity constraint violated - parent key not found.

    ```

4.  **外键表中的删除操作:**
    当主表中的一条记录被删除，并且子表中存在相应的记录时，会显示一条错误消息，阻止删除操作的进行。

    ```sql
    OUTPUT : 
    Error at line 1 : integrity constraint violated - child record found.

    ```

5.  **Foreign Key with ON DELETE CASCADE :**
    The default behavior of foreign key can be changed using ON DELETE CASCADE. When this option is specified in foreign key definition, if a record is deleted in master table, all corresponding record in detail table will be deleted.

    **语法–**

    ```sql
    create table people(no varchar2(10), 
                       fname varchar2(20), 
                       foreign key(no) 
    references person on delete cascade);

    ```

    现在从人员中删除记录将从子表中删除所有相应的记录。

    ```sql
    OUTPUT :
    select * from person;
    no rows selected 

    select * from people;
    no rows selected 
    ```

6.  **Foreign Key with ON DELETE SET NULL :**
    A Foreign key with SET NULL ON DELETE means if record in parent table is deleted, corresponding records in child table will have foreign key fields set to null. Records in child table will not be deleted.

    **语法–**

    ```sql
    create table people(no varchar2(10), 
                     fname varchar2(20), 
                        foreign key(no)
    references person on delete set null);

    ```

    ```sql
    OUTPUT :
    select * from person;
    no rows selected

    select * from people;
    NO Fname
    pqr 

    ```

    请注意人员表中引用人员表主键的字段“否”。删除人员数据时，会在子表人员中设置为空。但是记录不会被删除。