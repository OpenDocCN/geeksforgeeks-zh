# 如何计算 C# 中的代码执行时间？

> 原文:[https://www . geeksforgeeks . org/如何计算 c-sharp 中的代码执行时间/](https://www.geeksforgeeks.org/how-to-calculate-the-code-execution-time-in-c-sharp/)

任务的执行时间被定义为系统执行该任务所花费的时间。程序的执行时间等于其语句的执行时间之和。用 C# 计算程序执行时间的方法有很多。在本文中，我们将看到用 C# 测量执行时间的三种方法。

### 方法 1:使用 StartNew()和 Stop() 方法

我们可以使用 StartNew()和 Stop()方法计算代码的执行时间。StartNew()方法属于秒表类，它基本上用于初始化一个新的秒表实例。在内部，它将运行时间属性标记为零，然后开始测量运行时间。这个方法几乎与首先调用秒表构造函数，然后在新实例上调用类相同。

**语法:**

```cs
public static StartNew ();
```

Stop()方法也属于秒表类，用于在一个时间间隔内停止当前测量时间。首先我们可以在秒表中调用 StartNew()方法来开始经过的时间，最后我们可以调用这个方法来结束当前的测量时间间隔。最终，总的执行时间是在运行时间属性的帮助下计算出来的。每当秒表实例测量多个时间间隔时，这种方法类似于暂停经过时间测量。和 StartNew()方法一样，这个方法也是在 System 下定义的。诊断命名空间。

**语法:**

```cs
public void Stop ();
```

**示例:**

## C#

```cs
// C# program to find the execution time of the code
using System;
using System.Diagnostics;

class GFG{

static public void Main()
{

      // Starting the Stopwatch
    var watch = Stopwatch.StartNew();

      // Iterating using for loop
    for(int i = 0; i < 5; i++) 
    {

        // Print on console
        Console.WriteLine("GeeksforGeeks");
    }

      // Stop the Stopwatch
    watch.Stop();    

      // Print the execution time in milliseconds
      // by using the property elapsed milliseconds
      Console.WriteLine(
          {content}quot;The Execution time of the program is {watch.ElapsedMilliseconds}ms");
}
}
```

**Output**

```cs
GeeksforGeeks
GeeksforGeeks
GeeksforGeeks
GeeksforGeeks
GeeksforGeeks
The Execution time of the program is 37ms
```

### 方法 2:使用 GetTimestamp() 方法

我们还可以使用 GetTimestamp()方法找到代码的执行时间。这种方法对于在计时器机制中查找持续时间的刻度数非常有帮助。我们可以使用秒表类的高分辨率性能计数器来获取该计数器的当前值。我们也可以使用系统计时器来获取当前的日期时间。日期时间的刻度属性。UtcNow 实例。它的返回类型是一个长整数，表示计时器机制的滴答计数器值。

**语法:**

```cs
public static long GetTimestamp ();
```

**示例:**

## C#

```cs
// C# program to find the execution time of the code
using System;
using System.Diagnostics;

class GFG{

static public void Main()
{

      // Mark the start before the loop
      var start = Stopwatch.GetTimestamp();

      // Iterating using for loop
    for(int i = 0; i < 5; i++) 
    {

        // Print on console
        Console.WriteLine("GeeksforGeeks");
    }

      // Mark the end after the loop
    var end = Stopwatch.GetTimestamp();

      // Print the difference
    Console.WriteLine("Elapsed Time is {0} ticks", (end - start));
}
}
```

**Output**

```cs
GeeksforGeeks
GeeksforGeeks
GeeksforGeeks
GeeksforGeeks
GeeksforGeeks
Elapsed Time is 343095 ticks
```

### 方法 3:使用日期时间。现在的财产

我们可以使用 DateTime 计算代码的执行时间。现在是财产。该属性对于获取设备上最初标记有当前日期和时间(作为本地时间)的 DateTime 对象非常有帮助。此方法的属性值是 DateTime，它是一个值为当前本地数据和时间的对象。Now 属性返回一个描述设备或计算机上当前日期和时间的日期时间值。这是在系统命名空间下定义的。

**语法:**

```cs
public static DateTime Now { get; }
```

**示例:**

## C#

```cs
// C# program to find the execution time of the code
using System;

class GFG{

static public void Main()
{

      // Marking the start time
      DateTime start = DateTime.Now;

      // Iterating using for loop
       for(int i = 0 ; i < 5 ; i++)
    {
        Console.WriteLine("GeeksforGeeks");    
    }

      // Marking the end time
    DateTime end = DateTime.Now;

      // Total Duration 
    TimeSpan ts = (end - start);

      // Print the execution time in milliseconds
    Console.WriteLine("The execution time of the program is {0} ms", 
                      ts.TotalMilliseconds);
}
}
```

**输出:**

```cs
GeeksforGeeks
GeeksforGeeks
GeeksforGeeks
GeeksforGeeks
GeeksforGeeks
The execution time of the program is 176.095 ms
```