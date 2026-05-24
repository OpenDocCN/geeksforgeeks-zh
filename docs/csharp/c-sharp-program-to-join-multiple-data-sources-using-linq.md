# 使用 LINQ 连接多个数据源的 C# 程序

> 原文:[https://www . geesforgeks . org/c-sharp-program-to-join-multi-data-sources-use-linq/](https://www.geeksforgeeks.org/c-sharp-program-to-join-multiple-data-sources-using-linq/)

LINQ 被称为语言集成查询，它是在年引入的。NET 3.5。它提供了。NET 语言创建查询以从数据源检索数据。在本文中，我们将讨论如何使用 LINQ 连接多个数据源。这里的数据源是指列表。因此，我们使用列表集合创建三个具有学生详细信息的数据源，然后基于 id 连接数据，这在使用[连接](https://www.geeksforgeeks.org/linq-join-inner-join)关键字的所有列表中都很常见。

**语法:**

> 来自数据 1 中的迭代器 1
> 
> 在数据 2 中连接迭代器 2
> 
> 迭代器 1.column_name 等于迭代器 2.column_name
> 
> 在数据 3 中连接迭代器 3
> 
> 迭代器 1.column_name 等于迭代器 3.column_name
> 
> ————————————————–
> 
> ————————————————–
> 
> 数据中的连接迭代
> 
> 在迭代器 1 上，column_name 等于 iteratorn.column_name

其中数据是数据源列表，迭代器用于从特定数据源获取数据

**返回:**将根据比较的 column _ names 返回匹配的行。

**示例:**

```cs
Input:

Student
new Student{id = 7058, name = "sravan kumar", dept_id = 1, add_id = 21},
new Student{id = 7059, name = "jyothika", dept_id = 2, add_id = 22},
new Student{id = 7072, name = "harsha", dept_id = 1, add_id = 22},
new Student{id = 7076, name = "khyathi", dept_id = 4, add_id = 27},

Department
new Department{dept_id = 1, dept_name = "CSE"},
new Department{dept_id = 2, dept_name = "CSE"},
new Department{dept_id = 3, dept_name = "IT"},  

Address
new Address{add_id = 21, address_name = "hyd"},
new Address{add_id = 22, address_name = "railu-peta"},
new Address{add_id = 24, address_name = "chenchu-peta"},

Output:
ID: 7058--> Name: sravan kumar--> Department: CSE--> Address: hyd
ID: 7059--> Name: jyothika--> Department: CSE--> Address: railu-peta
ID: 7072--> Name: harsha--> Department: CSE--> Address: railu-peta
```

### 方法

**1。**通过声明变量，使用名为学生、部门和地址的列表创建三个数据源。

**2。**给这些列表添加值。

**3。**根据学生证、学部证、地址证进行加入。

```cs
var result = (from stu in students

join dept in departments on stu.dept_id equals dept.dept_id

join add in addresses on stu.add_id equals add.add_id).ToList();
```

**4。**使用 Select()方法选择数据。

```cs
select new
{
    ID = stu.id,
    Name = stu.name,
    DeptName = dept.dept_name,
    address = add.address_name
}
```

**5。**显示每个循环的使用情况。

```cs
foreach (var e in result)
{
    Console.WriteLine("\tID: " + e.ID + "--> Name: " + 
                               e.Name + "--> Department: " + 
                           e.DeptName + "--> Address: " + e.address);
}
```

**示例:**

## C#

```cs
// C# program to join multiple data sources
// Using LINQ
using System;
using System.Linq;
using System.Collections.Generic;

// Variables for Student list
public class Student
{
    public int id;
    public string name;
    public int dept_id;
    public int add_id;
}

// Variables for Department list
public class Department
{
    public int dept_id;
    public string dept_name;
}

// Variables for Address list
public class Address 
{
    public int add_id;
    public string address_name;
}

class GFG{

// Driver code   
static void Main(string[] args)
{

    // Enter data for Student list
    List<Student> students = new List<Student>()
    {
        new Student{ id = 7058, name = "sravan kumar",
                     dept_id = 1, add_id = 21 },
        new Student{ id = 7059, name = "jyothika",
                     dept_id = 2, add_id = 22 },
        new Student{ id = 7072, name = "harsha",
                     dept_id = 1, add_id = 22 },
        new Student{ id = 7076, name = "khyathi",
                     dept_id = 4, add_id = 27 },
    };

    List<Department> departments = new List<Department>()
    {
        new Department{ dept_id = 1, dept_name = "CSE" },
        new Department{ dept_id = 2, dept_name = "CSE" },
        new Department{ dept_id = 3, dept_name = "IT " },
    };

    List<Address> addresses = new List<Address>()
    {
        new Address{ add_id = 21, address_name = "hyd" },
        new Address{ add_id = 22, address_name = "railu-peta" },
        new Address{ add_id = 24, address_name = "chenchu-peta" },
    };

    // Join the students and other two tables
    var result = (from stu in students

                join dept in departments on stu
                .dept_id equals dept
                .dept_id

                join add in addresses on stu
                .add_id equals add.add_id

                select new 
                {
                    ID = stu.id, Name = stu.name,
                    DeptName = dept.dept_name,
                    address = add.address_name 

                }).ToList();

    // Display the result
    foreach(var e in result)
    {
        Console.WriteLine("\tID: " + e.ID + "--> Name: " + 
                                   e.Name + "--> Department: " + 
                               e.DeptName + "--> Address: " + e.address);
    }
}
}
```

**输出:**

```cs
ID: 7058--> Name: sravan kumar--> Department: CSE--> Address: hyd
ID: 7059--> Name: jyothika--> Department: CSE--> Address: railu-peta
ID: 7072--> Name: harsha--> Department: CSE--> Address: railu-peta
```