# 使用 LINQ 打印姓名以“S”开头且年龄大于 23 岁的员工的 C# 程序

> 原文:[https://www . geeksforgeeks . org/c-sharp-program-to-print-the-employees-with-s-age-大于-23-using-linq/](https://www.geeksforgeeks.org/c-sharp-program-to-print-the-employees-whose-name-started-with-s-and-age-is-greater-than-23-using-linq/)

LINQ 被称为语言集成查询，它是在年引入的。NET 3.5。它赋予了。NET 语言生成查询以从数据源检索数据。它消除了编程语言和数据库之间的不匹配，并且无论使用哪种类型的数据源，用于创建查询的语法都是相同的。在本文中，我们将学习如何使用 LINQ 打印姓名以“S”开头且年龄大于 23 岁的员工的详细信息。

**示例:**

```cs
Input : List of Employees:
         {{id = 101, name = "Sravan", age = 32},
          {id = 102, name = "deepu",  age = 15},
          {id = 103, name = "manoja", age = 13},
          {id = 104, name = "Sathwik", age = 12},
          {id = 105, name = "Saran",  age = 25}}
Output : {{id = 105, name = "sravan", age = 32},
          {id = 105, name = "Saran",  age = 25}}

Input : List of Employees:
        {{id = 102, name = "deepu",  age = 15},
         {id = 103, name = "manoja", age = 13}}
Output : No Output
```

**进场:**

> 要查找姓名以“S”开头且年龄大于 23 岁的员工列表，请执行以下步骤:
> 
> 1.  创建包含四个变量(身份证、姓名、部门和年龄)的员工列表。
> 2.  使用 where 子句循环查看员工详细信息，并通过选择员工姓名以“S”开头且年龄大于 23 岁来获取员工详细信息。所以我们写电磁脉冲。名称[0] == 'S' && emp。年龄> 23 岁。
> 3.  现在调用 ToString()方法。
> 4.  显示员工详细信息。

**示例:**

## C#

```cs
// C# program to display the details of 
// those employees whose name is starts 
// with S and their age is greater than 23
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

class Employee{

// Declare four variables - id, age, department, and name
int id; 
int age;
string department;
string name;

// Get the to string method that returns 
// id, age, department, and name
public override string ToString()
{
    return id + " " + name + " " + age + " " + department;
}

// Driver code
static void Main(string[] args)
{

    // Declare a list variable 
    List<Employee> emp = new List<Employee>()
    {

        // Create 5 Employee details
        new Employee{ id = 101, name = "Sravan",  
                      age = 32, department = "HR" },
        new Employee{ id = 102, name = "deepu", 
                      age = 15, department = "Development" },
        new Employee{ id = 103, name = "manoja", 
                      age = 13, department = "Development" },
        new Employee{ id = 104, name = "Sathwik", 
                      age = 12, department = "HR" },
        new Employee{ id = 105, name = "Saran", 
                      age = 25, department = "Designing" }
    };

    // Iterate the Employee by selecting Employee 
    // name starts with S and age is greater than 23
    IEnumerable<Employee> result = from e in emp 
                                   where e.name[0] == 'S' && e.age > 23 
                                   select e;

    // Display employee details
    Console.WriteLine("ID  Name  Age Department");
    Console.WriteLine("+++++++++++++++++++++++++");
    foreach (Employee x in result)
    {

        // Call the to string method
        Console.WriteLine(x.ToString());
    }    
}
}
```

**输出:**

```cs
ID  Name  Age Department
+++++++++++++++++++++++++
101 Sravan 32 HR
105 Saran 25 Designing
```