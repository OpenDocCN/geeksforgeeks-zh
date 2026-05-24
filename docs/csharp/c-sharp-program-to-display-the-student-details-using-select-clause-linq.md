# 使用 LINQ 选择条款显示学生详细信息的 C# 程序

> 原文:[https://www . geesforgeks . org/c-sharp-program-to-display-the-student-details-use-select-子句-linq/](https://www.geeksforgeeks.org/c-sharp-program-to-display-the-student-details-using-select-clause-linq/)

LINQ 被称为语言集成查询，它是在年引入的。NET 3.5。它赋予了。NET 语言生成查询以从数据源检索数据。它消除了编程语言和数据库之间的不匹配，并且无论使用哪种类型的数据源，用于创建查询的语法都是相同的。在本文中，我们将学习如何使用 LINQ 的 [select](https://www.geeksforgeeks.org/linq-projection-operator-select/) 子句打印学生名单及其详细信息。当我们想从给定的集合中选择一些特定的值时，使用 Select 子句。

**语法:**

> IEnumerable <student>查询=从学生中选择学生；</student>

**示例:**

```cs
Input :
{ stu_id = 101, stu_name = "bobby", 
  stu_dept = "cse", stu_salary = 8900 },
{ stu_id = 102, stu_name = "sravan", 
  stu_dept = "ece", stu_salary = 8900 },
{ stu_id = 103, stu_name = "deepu", 
  stu_dept = "mba", stu_salary = 8900 }};
Output :
{ stu_id = 101, stu_name = "bobby", 
  stu_dept = "cse", stu_salary = 8900 },
{ stu_id = 102, stu_name = "sravan", 
  stu_dept = "ece", stu_salary = 8900 },
{ stu_id = 103, stu_name = "deepu", 
  stu_dept = "mba", stu_salary = 8900 }};

Input :
{ stu_id = 101, stu_name = "bobby", 
  stu_dept = "cse", stu_salary = 8900 }
Output:
{ stu_id = 101, stu_name = "bobby", 
  stu_dept = "cse", stu_salary = 8900 }

```

**接近**

> 要显示学生列表，请执行以下步骤:
> 
> 1.  创建一个包含四个变量(身份证、姓名、部门和学期)的学生列表。
> 2.  使用 for 循环遍历学生详细信息，并使用 select 子句获取学生详细信息
> 3.  显示学生详细信息。

**示例:**

## C#

```cs
// C# program to print the list of students
// details using select clause

using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

class Student{

// Declare 4 variables - id, age, department and semester
int stu_id; 
string stu_dept;
string stu_name;
int stu_semester;

// Get the to string method that returns
// id, age, department and semester
public override string ToString()
{
    return stu_id + " " + stu_name + " " + 
           stu_dept + " " + stu_semester;
}

// Driver code
static void Main(string[] args)
{

    // Declare a list variable 
    List<Student> stu = new List<Student>()
    {

        // Create 3 Student details
        new Student{ stu_id = 101, stu_name = "bobby", 
                     stu_dept = "CSE", stu_semester = 2 },
        new Student{ stu_id = 102, stu_name = "sravan", 
                     stu_dept = "ECE", stu_semester = 1 },
        new Student{ stu_id = 103, stu_name = "deepu", 
                     stu_dept = "EEE", stu_semester = 4},
    };

    // Iterate the Employee 
    // using select function
    IEnumerable<Student> Query = from student in stu select student;

    // Display student details
    Console.WriteLine("ID  Name  Department Semester");
    Console.WriteLine("+++++++++++++++++++++++++++");
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
ID  Name  Department Semester
+++++++++++++++++++++++++++
101 bobby CSE 2
102 sravan ECE 1
103 deepu EEE 4
```