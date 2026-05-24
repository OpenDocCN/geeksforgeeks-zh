# C#-嵌套循环

> 原文:[https://www.geeksforgeeks.org/c-sharp-nested-loops/](https://www.geeksforgeeks.org/c-sharp-nested-loops/)

嵌套循环是存在于另一个循环中的循环。在 C# 中，for、while 和 do-while 循环的嵌套是允许的，您还可以将任何嵌套循环放入  任何其他类型的循环中，如 for 循环中，您可以将嵌套 if 循环放入其中。

**for Loop:**for Loop 的功能与 while loop 非常相似。当循环语句的执行次数事先已知时，基本上使用它。允许对 for 循环进行估计，这意味着您可以在另一个 for 循环中使用 for 循环。

**语法:**

```cs
for(variable initialization; testing condition; increment / decrement)
{
    for(variable initialization; testing condition; 
                                 increment / decrement)
    {
        // Statements 
    }
}

```

**示例:**

## C#

```cs
// C# program to illustrate nested for loop 
using System; 

class GFG{

public static void Main() 
{ 

    // for loop within another for loop 
    // printing GeeksforGeeks 
    for(int i = 0; i < 4; i++) 
        for(int j = 1; j < i; j++) 
            Console.WriteLine("GeeksforGeeks!!"); 
} 
}
```

**输出:**

```cs
GeeksforGeeks!!
GeeksforGeeks!!
GeeksforGeeks!!

```

**while 循环:**在 while 循环中，在循环的开始、给定测试条件，执行所有语句，直到给定的布尔条件满足并且 当条件变为假时，控制将从 while 循环中退出。允许嵌套一个 while 循环，这意味着您可以在另一个 while 循环中使用 while 循环。但是，不建议使用嵌套 while 循环，因为它很难维护和调试。

**语法:**

```cs
while(condition) 
{
   while(condition)
   {
      // Statements 
   }

  // Statements 
}

```

**示例:**

## C#

```cs
// C# program to illustrate nested while loop 
using System; 

class GFG{

public static void Main() 
{ 
    int x = 1, y = 2;

    while (x < 4)
    {
        Console.WriteLine("Outer loop = {0}", x);
        x++;

        while (y < 4)
        {
            Console.WriteLine("Inner loop = {0}", y);
            y++;
        }
    }
} 
}
```

**输出:**

```cs
Outer loop = 1
Inner loop = 2
Inner loop = 3
Outer loop = 2
Outer loop = 3

```

**do-while 循环:**在 c#**中，do-while 循环与和 while 循环相似，唯一的区别是，它在执行语句后检查条件。N 允许估计边做边循环，这意味着您可以在另一个边做边循环中使用边做边循环。**

****语法:****

```cs
do
{
   // Statements
   do 
   {
      // Statements
   }
   while(condition);
}
while(condition); 
```

****示例:****

## **C#**

```cs
// C# program to illustrate nested do-while loop 
using System; 

class GFG{

public static void Main() 
{ 
    int x = 1;
    do
    {
        Console.WriteLine("Outer loop = {0}", x);
        int y = x;

        x++;

        do
        {
            Console.WriteLine("Inner loop: {0}", y);
            y++;
        } while (y < 4);

    } while (x < 4);
} 
}
```

****输出:****

```cs
Outer loop = 1
Inner loop: 1
Inner loop: 2
Inner loop: 3
Outer loop = 2
Inner loop: 2
Inner loop: 3
Outer loop = 3
Inner loop: 3 
```