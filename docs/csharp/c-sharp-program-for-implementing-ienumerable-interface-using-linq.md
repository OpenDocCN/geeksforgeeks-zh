# 使用 LINQ 实现可数接口的 C# 程序

> 原文:[https://www . geeksforgeeks . org/c-sharp-program-for-implementable-interface-use-linq/](https://www.geeksforgeeks.org/c-sharp-program-for-implementing-ienumerable-interface-using-linq/)

[LINQ](https://www.geeksforgeeks.org/linq-language-integrated-query/) 被称为语言集成查询，它是在。NET 3.5。它赋予了。NET 语言生成查询以从数据源检索数据。它消除了编程语言和数据库之间的不匹配，并且无论使用哪种类型的数据源，用于创建查询的语法都是相同的。在本文中，我们将使用 LINQ 实现一个 IEnumerable 接口。这个接口用于迭代像列表、堆栈、队列等集合。或者我们可以说这个接口是所有可以枚举的非泛型集合的基础接口。

**语法:**

```cs
IEnumerable<TSource>
```

使用 IEnumerable，我们将显示姓名以“D”开头的员工数据。

**例**:

```cs
Input : List of Employees:
        {{id = 201, name = "Druva", age = 12},
         {id = 202, name = "Deepu", age = 15},
         {id = 203, name = "Manoja", age = 13},
         {id = 204, name = "Sathwik", age = 12},
         {id = 205, name = "Suraj", age = 15}}
Output : {{id = 201, name = "Druva", age = 12},
          {id = 202, name = "Deepu", age = 15}}

Input : List of Employees:
        {{id = 301, name = "Sathwik", age = 12},
         {id = 302, name = "Saran", age = 15}}
Output : No Output
```

**接近**:

> 要查找姓名以字母“D”开头的员工列表，请执行以下步骤:
> 
> 1.  创建包含四个变量(身份证、姓名、部门和工资)的员工列表。
> 2.  使用 Where()函数迭代员工详细信息，并使用 s => s.name[0] == 'D '选择姓名以' D '开头的员工来获取员工详细信息。
> 3.  现在调用 ToString()方法。
> 4.  显示员工详细信息。

**示例:**

## C#

```cs
// C# program to display the details of those 
// employees whose name starts with character "D"
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
        new Employee{ id = 201, name = "Druva", 
                      salary = 12000, department = "HR" },
        new Employee{ id = 202, name = "Deepu", 
                      salary = 15000, department = "Development" },
        new Employee{ id = 203, name = "Manoja", 
                      salary = 13000, department = "HR" },
        new Employee{ id = 204, name = "Sathwik", 
                      salary = 12000, department = "Designing" },
        new Employee{ id = 205, name = "Suraj", 
                      salary = 15000, department = "Development" }
    };

    // Iterate the Employee by selecting Employee 
    // name starts with D
    // Using IEnumerable interface
    IEnumerable<Employee> result = emp.Where(x => x.name[0] == 'D');

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
201 Druva 12000 HR
202 Deepu 15000 Development
```