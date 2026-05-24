# C# 程序查找姓名以“S”开头的学生名单使用 where()方法使用 LINQ 列表收集

> 原文:[https://www . geeksforgeeks . org/c-sharp-program-to-find-the-list-of-studies-name-开头是-s-using-where-method-list-collection-using-linq/](https://www.geeksforgeeks.org/c-sharp-program-to-find-the-list-of-students-whose-name-starts-with-s-using-where-method-of-list-collection-using-linq/)

LINQ 被称为语言集成查询，它是在年引入的。NET 3.5。它赋予*能力。NET* 语言生成查询，从数据源中检索数据。它消除了编程语言和数据库之间的不匹配，并且无论使用哪种类型的数据源，用于创建查询的语法都是相同的。在本文中，我们将学习如何使用列表收集的 where()方法打印姓名以“S”开头的学生列表。这里，where 方法根据谓词过滤给定的值序列或数组。要使用 where()方法，您需要导入*系统。临朐*和*系统。集合。程序中的通用*命名空间。

**语法:**

> 其中 <tsource>(IEnumerable <tsource>，Func <tsource boolean="">)</tsource></tsource></tsource>

**示例:**

```cs
Input : List of Students:
        {{id = 101, name = "Sravan", age = 12},
         {id = 102, name = "deepu",  age = 15},
         {id = 103, name = "manoja", age = 13},
         {id = 104, name = "Sathwik", age = 12},
         {id = 105, name = "Saran",  age = 15}}
Output: {{id = 105, name = "sravan", age = 15},
         {id = 104, name = "Sathwik",age = 12},
         {id = 105, name = "Saran",  age = 15}}

Input: List of Students:
       {{id = 102, name = "deepu",  age = 15},
        {id = 103, name = "manoja", age = 13}}
Output: No Output
```

**进场:**

> 要查找姓名以“S”开头的学生列表，请执行以下步骤:
> 
> 1.  创建一个包含三个变量(身份证、姓名和年龄)的学生列表。
> 2.  使用 Where()函数迭代学生详细信息，并通过选择学生姓名以 S 开头并使用 s => s.name[0] == 'S '来获取学生详细信息。
> 3.  现在调用 ToString()方法。
> 4.  显示学生详细信息。

**示例:**

## C#

```cs
// C# program to display the list of students whose 
// name starts with 'S'. Using Where() function 
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

class Student{

// Declare 3 variables - id, age and name
int id; 
int age;
string name;

// Get the to string method that returns 
// id , name and age
public override string ToString()
{
    return id + " " + name + " " + age;
}

// Driver code
static void Main(string[] args)
{

    // Declare a list variable 
    List<Student> student = new List<Student>()
    {

        // Create 5 Student details
        new Student{ id = 101, name = "Sravan", age = 12  },
        new Student{ id = 102, name = "deepu", age = 15 },
        new Student{ id = 103, name = "manoja", age = 13 },
        new Student{ id = 104, name = "Sathwik", age = 12 },
        new Student{ id = 105, name = "Saran", age = 15 }

    };

    // Iterate the Student by selecting Student 
    // name starts with S
    // Using Where() function
    IEnumerable<Student> Query = student.Where(s => s.name[0] == 'S');

    // Display employee details
    Console.WriteLine("ID  Name  Age");
    Console.WriteLine("+++++++++++++");
    foreach (Student e in Query)
    {

        // Call the to string method
        Console.WriteLine(e.ToString());
    }    
}
}
```

**输出:**

```cs
ID  Name  Age
+++++++++++++
101 Sravan 12
104 Sathwik 12
105 Saran 15
```