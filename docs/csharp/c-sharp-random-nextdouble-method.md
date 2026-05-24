# C# |随机。NextDouble()方法

> 原文:[https://www . geesforgeks . org/c-sharp-random-next double-method/](https://www.geeksforgeeks.org/c-sharp-random-nextdouble-method/)

**系统的 **NextDouble()** 方法。C# 中的 Random** 类用于返回一个大于等于 0.0，小于 1.0 的随机浮点数。

**语法:**

```cs
public virtual double NextDouble();
```

**返回值:**该方法返回大于等于 0.0 且小于 1.0 的双精度浮点数。

下面的程序说明了 **NextDouble()** 方法的使用:

**例 1:**

```cs
// C# program to illustrate the 
// Random.NextDouble() Method
using System;

class GFG {

    // Driver code
    public static void Main()
    {
        // Instantiate random number generator
        Random rand = new Random();

        // Print 10 random floating point numbers
        Console.WriteLine("Printing 10 random floating point numbers");
        for (int i = 0; i < 10; i++)
            Console.WriteLine("{0} -> {1}", i, rand.NextDouble());
    }
}
```

**Output:**

```cs
Printing 10 random floating point numbers
0 -> 0.0227202852362396
1 -> 0.624568469647583
2 -> 0.0145442797870116
3 -> 0.646489209330869
4 -> 0.967497945748036
5 -> 0.839329582098559
6 -> 0.873648912121378
7 -> 0.16200648022909
8 -> 0.66018275761054
9 -> 0.0837694853934317

```

**例 2:**

```cs
// C# program to illustrate the 
// Random.NextDouble() Method
using System;

class GFG {

    // Driver code
    public static void Main()
    {
        // Instantiate random number generator
        Random rand = new Random();

        // Instantiate an array of double
        double[] a = new double[10];

        // Store random floating point 
        // numbers in the array
        for (int i = 0; i < 10; i++)
            a[i] = rand.NextDouble();

        // Print 10 random floating point numbers
        Console.WriteLine("Printing 10 random "+
                      "floating point numbers");

        for (int i = 0; i < 10; i++)
            Console.WriteLine("{0} -> {1}", i, a[i]);
    }
}
```

**Output:**

```cs
Printing 10 random floating point numbers
0 -> 0.853536825558886
1 -> 0.741455778359182
2 -> 0.496043408986201
3 -> 0.0975164361752181
4 -> 0.120282317567748
5 -> 0.57163705703413
6 -> 0.749181974562435
7 -> 0.684014179596684
8 -> 0.691246760865323
9 -> 0.888019556127498

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . random . next double？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.random.nextdouble?view=netframework-4.7.2)