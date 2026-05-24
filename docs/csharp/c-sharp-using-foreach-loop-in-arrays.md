# C# |在数组中使用 foreach 循环

> 原文:[https://www . geeksforgeeks . org/c-sharp-using-foreach-loop-in-arrays/](https://www.geeksforgeeks.org/c-sharp-using-foreach-loop-in-arrays/)

C# 语言提供了几种读取项目集合的技术。其中一个是**[foreach loop](https://www.geeksforgeeks.org/c-foreach-loop/)T4。foreach 循环提供了一种简单、干净的方式来遍历*集合或项目数组*的元素。有一点我们必须知道，在使用 foreach 循环之前，我们必须在程序中声明数组或集合。因为 foreach 循环只能迭代之前声明的任何数组或任何集合。我们无法像 for loop 一样使用 foreach 循环打印数字或字符序列，请参见下面的:**

```cs
for(i = 0; i <= 10; i++)
// we cannot use foreach loop in this way to print 1 to 10
// to print 1 to 10 using foreach loop we need to declare 
// an array or a collection of size 10 and a variable that 
// can hold 1 to 10 integer 
```

**foreach 循环的语法:**

```cs
foreach (Data_Type variable_name in Collection_or_array_Object_name)
 {
   //body of foreach loop
 }
// here "in" is a keyword

```

这里*数据类型*是变量的数据类型，*变量名称*是将迭代循环条件的变量(例如，对于(int I = 0；一<10；i++)，这里 I 相当于 variable_name)。在 foreach 循环中使用的关键字中的**来迭代可迭代项(这里是数组或集合)。**关键字中的**在每次迭代中从 iterable-item 或数组或集合中选择一个项目，并将其存储在变量(这里是 variable_name)中。**

**示例 1:** 下面是使用数组

```cs
// C# program to show the use of
// "for" loop and "foreach" loop
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        // initialize the array
        char[] arr = {'G', 'e', 'e', 'k', 's', 
                        'f', 'o', 'r', 'G', 'e', 
                                 'e', 'k', 's'};

        Console.Write("Array printing using for loop = ");

        // simple "for" loop
        for (int i = 0; i < arr.Length; i++)
        {
            Console.Write(arr[i]);
        }

        Console.WriteLine();

        Console.Write("Array printing using foreach loop = ");

        // "foreach" loop
        // "ch" is the variable
        // of type "char"
        // "arr" is the array 
        // which is going to iterates
        foreach(char ch in arr)
        {
            Console.Write(ch);
        }
    }
}
```

**实现“for”和“foreach”循环输出:**

```cs
Array printing using for loop = GeeksforGeeks
Array printing using foreach loop = GeeksforGeeks

```