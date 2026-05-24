# 数据库管理系统中断言和触发器的区别

> 原文:[https://www . geesforgeks . org/DBMS 中断言和触发器的区别/](https://www.geeksforgeeks.org/difference-between-assertions-and-triggers-in-dbms/)

**1。什么是断言？**
当一个约束涉及 2 个(或更多)表时，表约束机制有时会很难，结果可能不会像预期的那样。为了覆盖这种情况 [SQL](https://www.geeksforgeeks.org/sql-tutorial/) 支持创建断言，这些断言是不仅仅与一个表相关联的约束。断言语句应该确保数据库中始终存在某个条件。每当在相应的表中进行修改时，数据库管理系统总是检查断言。

**语法–**

```sql
CREATE ASSERTION  [ assertion_name ]
CHECK ( [ condition ] );
```

**示例–**

```sql
CREATE TABLE sailors (sid int,sname varchar(20), rating int,primary key(sid),
CHECK(rating >= 1 AND rating <=10)
CHECK((select count(s.sid) from sailors s) + (select count(b.bid)from boats b)<100) ); 
```

在上面的例子中，我们强制执行 CHECK 约束，即船只和水手的数量应该少于 100。因此，在这里，我们能够同时检查两个平板电脑的约束。

**2。什么是** [**触发**](https://www.geeksforgeeks.org/sql-trigger-student-database/) **？**
触发器是与表相关联的数据库对象，当对表执行定义的操作时，它将被激活。当我们运行以下语句时，可以执行触发器:

1.  插入
2.  更新
3.  删除

并且可以在事件之前或之后调用。

**语法–**

```sql
create trigger [trigger_name]       
[before | after]          
{insert | update | delete} 
on [table_name]  
[for each row]    
[trigger_body]  
```

**示例–**

```sql
create trigger t1  before  UPDATE on sailors
for each row
begin
   if new.age>60 then
      set new.age=old.age;
   else
      set new.age=new.age;
   end if;
end;
$ 
```

在上面的例子中，我们在更新之前创建了触发器。所以，如果新时代大于 60 岁我们就不应该更新，否则我们就应该更新。我们可以使用“{content}”来调用这个触发器。符号。

**断言与触发器的区别:**

<figure class="table">

| s。不 | affirm | trigger |
| --- | --- | --- |
| 1。 | When we know that a given specific condition is always true, we can use assertions. | We can use triggers, even if certain conditions may be true or false. |
| 2。 | When the SQL condition is not met, the whole table or even the database may be locked. | If the query condition is not true, the trigger can catch the error. |
| 3。 | Assertions are not linked to specific tables or events. It performs tasks specified or defined by users. | It helps to maintain integrity constraints in database tables, especially when primary key and foreign key constraints are undefined. |
| 4。 | Assertions do not maintain any track of changes made in the table. | The trigger keeps track of all changes in the table. |
| 5。 | Compared with triggers, the syntax of assertions is very small. | They have a big syntax to indicate every detail of the created trigger. |
| 6。 | Modern databases do not use assertions. | Triggers are used very well in modern databases. |

</figure>

断言不能修改数据，也不能链接到数据库中的任何特定表或事件，但是触发器更强大，因为它们可以检查条件，也可以修改数据库中表内的数据，这与断言不同。