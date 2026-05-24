# 生成学生成绩单的 C# 程序

> 原文: [https://www.geeksforgeeks.org/c-sharp-program-to-generate-marksheet-of-student/](https://www.geeksforgeeks.org/c-sharp-program-to-generate-marksheet-of-student/)

给定学生的分数，现在我们通过输入学生姓名和卷号来计算学生的三个学科分数，从而生成学生的分数表。

**示例:**

```cs
Input:
Enter Student Roll-Number: 1
Enter Student Name: manoj
Enter Subject-1 Marks :90
Enter Subject-2 Marks :78
Enter Subject-3 Marks :96

Output:
Total Marks: 264
Percentage: 88
Grade is A
```

## 方法

- 声明将用于保存三个科目分数的变量，即科目一、科目二和科目三（即分数一、分数二和分数三）。
- 从用户处读取学生数据。
- 计算三个科目的总分。

```cs
total = marks1 + marks2 + marks3;
```

- 计算百分比。

```cs
percentage = total / 3.0f;
```

- 显示学生的最终百分比。
- 类似地，根据学生的百分比计算并显示学生的分数。

## C# 代码示例

```cs
// C# program to create marksheet for students.
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;

class GFG{

static void Main(string[] args)
{

// Declare variables for marks and total
    int r, marks1, marks2, marks3, total;

// Declare percentage variable
    float percentage;
    string n;

// Enter student roll number
    Console.WriteLine("Enter Student Roll Number :");
    r = Convert.ToInt32(Console.ReadLine());

// Enter student name
    Console.WriteLine("Enter Student Name :");
    n = Console.ReadLine();

// Enter student subject 1 marks
    Console.WriteLine("Enter Subject-1 Marks : ");
    marks1 = Convert.ToInt32(Console.ReadLine());

// Enter student subject 2 marks
    Console.WriteLine("Enter Subject-2 Marks : ");
    marks2 = Convert.ToInt32(Console.ReadLine());

// Enter student subject 3 marks
    Console.WriteLine("Enter Subject-3 Marks :");
    marks3 = Convert.ToInt32(Console.ReadLine());

// Calculate total marks
    total = marks1 + marks2 + marks3;

// Calculate percentage
    percentage = total / 3.0f;

// Display the final result
    Console.WriteLine("Final result of {0} is:", n);
    Console.WriteLine("Total Marks : " + total);
    Console.WriteLine("Percentage : " + percentage);

// Calculate grades
    if (percentage <= 35)
    {
        Console.WriteLine("Grade is F");
    }
    else if (percentage >= 34 && percentage <= 39)
    {
        Console.WriteLine("Grade is D");
    }
    else if (percentage >= 40 && percentage <= 59)
    {
        Console.WriteLine("Grade is C");
    }
    else if (percentage >= 60 && percentage <= 69)
    {
        Console.WriteLine("Grade is B");
    }
    else if (percentage >= 70 && percentage <= 79)
    {
        Console.WriteLine("Grade is B+");
    }
    else if (percentage >= 80 && percentage <= 90)
    {
        Console.WriteLine("Grade is A");
    }
    else if (percentage >= 91)
    {
        Console.WriteLine("Grade is A+");
    }
}
}
```

## 输出示例

```cs
Enter Student Roll Number :

Enter Student Name :
Hitesh
Enter Subject-1 Marks :

Enter Subject-2 Marks :

Enter Subject-3 Marks :

Final result of Hitesh is:
Total Marks : 221
Percentage : 73.66666
Grade is B+
```