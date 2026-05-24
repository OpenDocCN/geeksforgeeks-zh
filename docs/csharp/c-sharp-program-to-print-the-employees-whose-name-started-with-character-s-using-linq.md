# 使用 LINQ 打印姓名以“S”开头的员工的 C# 程序

> 原文:[https://www . geeksforgeeks . org/c-sharp-program-to-print-the-employees-s-use-linq/](https://www.geeksforgeeks.org/c-sharp-program-to-print-the-employees-whose-name-started-with-character-s-using-linq/)

LINQ 被称为语言集成查询，它是在年引入的。NET 3.5。它赋予了。NET 语言生成查询以从数据源检索数据。它消除了编程语言和数据库之间的不匹配，并且无论使用哪种类型的数据源，用于创建查询的语法都是相同的。在本文中，我们将学习如何使用 LINQ 打印姓名以字母“S”开头的员工的详细信息。所以为了完成我们的任务，我们使用 Where()方法。此方法基于谓词过滤给定的值序列或数组，要使用此方法，您需要添加 System。临朐与系统。集合。程序中的通用命名空间。

**语法:**

> 其中 <tsource>(IEnumerable <tsource>，Func <tsource boolean="">)</tsource></tsource></tsource>

**示例:**

```cs
Input : List of Employees:
        {{id = 101, name = "Sravan", age = 12},
         {id = 102, name = "deepu",  age = 15},
         {id = 103, name = "manoja", age = 13},
         {id = 104, name = "Sathwik", age = 12},
         {id = 105, name = "Saran",  age = 15}}
Output : {{id = 105, name = "sravan", age = 15},
          {id = 104, name = "Sathwik",age = 12},
          {id = 105, name = "Saran",  age = 15}}

Input : List of Employees:
        {{id = 102, name = "deepu",  age = 15},
         {id = 103, name = "manoja", age = 13}}
Output : No Output
```

**进场:**

> 要查找姓名以字母“S”开头的员工列表，请执行以下步骤:
> 
> 1.  创建包含三个变量(身份证、姓名、部门和工资)的员工列表。
> 2.  通过使用 Where()函数迭代员工详细信息，并通过使用 s => s.name[0] == 'S '选择姓名以' S '开头的员工来获取员工详细信息。
> 3.  现在调用 ToString()方法。
> 4.  显示员工详细信息。

**示例:**

## C#

```cs
// C# program to display the details of those 
// employees whose name starts with character "S"
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

class Employee{

// Declare 4 variables - id, name, 
// department, and salary
int id; 
int salary;
string name;
string department;

// Get the to string method that returns 
// id, name, department, and salary
public override string ToString()
{
    return id + " " + name + " " + 
       salary + " " + department;
}

// Driver code
static void Main(string[] args)
{

    // Declare a list variable 
    List<Employee> emp = new List<Employee>()
    {

        // Create 5 Employee details
        new Employee{ id = 101, name = "Sravan", 
                      salary = 12000, department = "HR" },
        new Employee{ id = 102, name = "deepu", 
                      salary = 15000, department = "Development" },
        new Employee{ id = 103, name = "manoja", 
                      salary = 13000, department = "HR" },
        new Employee{ id = 104, name = "Sathwik", 
                      salary = 12000, department = "Designing" },
        new Employee{ id = 105, name = "Saran", 
                      salary = 15000, department = "Development" }
    };

    // Iterate the Employee by selecting Employee 
    // name starts with S
    IEnumerable<Employee> result = emp.Where(x => x.name[0] == 'S');

    // Display employee details
    Console.WriteLine("ID  Name  Salary  Department");
    Console.WriteLine("++++++++++++++++++++++++++++");
    foreach (Employee e in result)
    {

        // Call the to string method
        Console.WriteLine(e.ToString());
    }    
}
}
```

**输出:**

```cs
ID  Name  Salary  Department
++++++++++++++++++++++++++++
101 Sravan 12000 HR
104 Sathwik 12000 Designing
105 Saran 15000 Development
```