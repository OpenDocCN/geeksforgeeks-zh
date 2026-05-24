# c#–无限循环

> 原文:[https://www.geeksforgeeks.org/c-infinite-loop/](https://www.geeksforgeeks.org/c-infinite-loop/)

**无限循环**是一个永不终止或结束且无限重复的循环。或者换句话说，无限循环是这样一种循环，在这种循环中，测试条件不会评估为假，并且循环会一直持续下去，直到使用外力来结束它。您可以创建一个无限循环:

*   **用于循环**
*   **边循环边使用**

**例 1:**

在本例中，我们使用 ***while 循环*** 通过将条件设置为真来创建无限循环。它将使 while 循环永远不会计算为 false，并且循环无限期重复。

## C#

```cs
// C# program to illustrate
// infinite loop
using System;

class GFG{

static public void Main ()
{

    // Creating infinite loop
    // using while loop
    while (true)
    {

        // This statement will be printed
        // infinite times
        Console.WriteLine("Hey! GeeksforGeeks");
    }
}
}
```

**输出:**

```cs
Hey! GeeksforGeeks
Hey! GeeksforGeeks
Hey! GeeksforGeeks
Hey! GeeksforGeeks
Hey! GeeksforGeeks
Hey! GeeksforGeeks
Hey! GeeksforGeeks
Hey! GeeksforGeeks
Hey! GeeksforGeeks
.........
```

**例 2:**

在这个例子中，我们使用 ***进行循环*** 来创建一个无限循环。

## C#

```cs
// C# program to illustrate
// infinite loop
using System;

class GFG{

public static void Main()
{

    // Creating infinite loop
    // Using for loop
    for(;;)

    // This statement will be printed
    // infinite times
    Console.WriteLine("Welcome GFG!!");
}
}
```

**输出:**

```cs
Welcome GFG!!
Welcome GFG!!
Welcome GFG!!
Welcome GFG!!
Welcome GFG!!
Welcome GFG!!
Welcome GFG!!
Welcome GFG!!
........
```