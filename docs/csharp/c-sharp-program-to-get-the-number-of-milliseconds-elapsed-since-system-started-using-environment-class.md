# C# 程序获取系统使用环境类

启动后经过的毫秒数

> 原文:[https://www . geesforgeks . org/c-sharp-程序获取系统启动后经过的毫秒数-使用环境-类/](https://www.geeksforgeeks.org/c-sharp-program-to-get-the-number-of-milliseconds-elapsed-since-system-started-using-environment-class/)

在 C# 中，环境类提供关于当前平台的信息，并操纵当前平台。它对于获取和设置各种操作系统相关信息非常有用。我们可以这样使用它:它检索命令行参数信息、退出代码信息、环境变量设置信息、调用堆栈信息的内容以及自上次系统启动以来的时间(以毫秒为单位)信息。通过使用一些预定义的方法，我们可以使用环境类获得操作系统的信息。在本文中，我们将获得毫秒数，因此我们使用环境类的 **TickCount** 属性。TickCount 属性用于获取环境类从开始的毫秒数。它将以整数格式返回秒

**语法**:

> 内部环境。TickCount

**返回类型:**返回经过的秒数，为整数

**例 1:**

## C#

```cs
// C# program to evaluate the sum and then find the time
// that elapsed since system started
using System;

class GFG{

static public void Main()
{

    // Evaluate the expression
    int summ = 2 + 3;
    Console.WriteLine("Sum is: " + summ);

    // Count the elapsed seconds
    Console.WriteLine("So, the tick count is : " + 
                      Environment.TickCount);
}
}
```

**输出:**

```cs
Sum is: 5
So, the tick count is : 12173138
```

**例 2:**

## C#

```cs
// C# program to find the time with out 
// any delay (With out no operation)
using System;

class GFG{

static public void Main()
{

    // Count the elapsed seconds
    Console.WriteLine("The tick count is : " + 
                      Environment.TickCount);
}
}
```

**输出:**

```cs
The tick count is : 11475417
```