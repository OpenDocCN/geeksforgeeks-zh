# 演示结构数组的 C# 程序

> 原文: [https://www.geeksforgeeks.org/c-sharp-program-to-demonstrate-the-array-of-structures/](https://www.geeksforgeeks.org/c-sharp-program-to-demonstrate-the-array-of-structures/)

结构数组意味着每个数组索引都包含结构作为值。在本文中，我们将使用带有特定索引的数组来创建结构和访问结构成员的数组。

**语法**

`数组[索引].结构(细节);`

其中 `index` 指定要插入的特定位置，`details` 是结构中的值。

**示例:**

```cs
Input:
Insert three values in an array
Student[] student = { new Student(), new Student(), new Student() };
student[0].SetStudent(1, "ojaswi", 20);
student[1].SetStudent(2, "rohith", 21);
student[2].SetStudent(3, "rohith", 21);

Output:
(1, "ojaswi", 20)
(2, "rohith", 21)
(3, "rohith", 21)
```

**进场:**

1.  声明三个变量 `id`、`name` 和 `age`。
2.  在 `SetStudent()` 方法中设置详细信息。
3.  为三个学生创建一个结构数组。
4.  将结构分别传递给三个学生的数组索引。
5.  通过调用 `DisplayStudent()` 方法显示学生。

**示例:**

## C\#

```cs
// C# program to display the array of structure
using System;

public struct Employee
{

// Declare three variables
    // id, name and age
    public int Id;
    public string Name;
    public int Age;

// Set the employee details
    public void SetEmployee(int id, string name, int age)
    {
        Id = id;
        Name = name;
        Age = age;
    }

// Display employee details
    public void DisplayEmployee()
    {
        Console.WriteLine("Employee:");
        Console.WriteLine("\tId    : " + Id);
        Console.WriteLine("\tName   : " + Name);
        Console.WriteLine("\tAge   : " + Age);
        Console.WriteLine("\n");
    }
}

class GFG{

// Driver code
static void Main(string[] args)
{

// Create array of structure
    Employee[] emp = { new Employee(),
                       new Employee(),
                       new Employee() };

// Pass the array indexes with values as structures
    emp[0].SetEmployee(1, "Ojaswi", 20);
    emp[1].SetEmployee(2, "Rohit", 21);
    emp[2].SetEmployee(3, "Mohit", 23);

// Call the display method
    emp[0].DisplayEmployee();
    emp[1].DisplayEmployee();
    emp[2].DisplayEmployee();
}
}
```

**输出:**

```cs
Employee:
    Id    : 1
    Name   : Ojaswi
    Age   : 20

Employee:
    Id    : 2
    Name   : Rohit
    Age   : 21

Employee:
    Id    : 3
    Name   : Mohit
    Age   : 23
```