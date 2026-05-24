# 如何在 C# 中比较枚举值？

> 原文:[https://www . geesforgeks . org/如何比较-enum-values-in-c-sharp/](https://www.geeksforgeeks.org/how-to-compare-enum-values-in-c-sharp/)

**枚举。比较(对象)方法**用于将当前实例与指定的对象进行比较，并返回它们的相对值的指示。

**语法:**

```cs
public int CompareTo (object target);
```

这里*目标*是比较的对象，也可以为空。

**返回:**该方法返回一个带符号的数字，该数字显示当前实例和目标的相对值，如下所示:

*   **小于零:**如果当前实例的值小于目标的值。
*   **零:**如果当前实例的值等于目标的值。
*   **大于零:**如果当前实例的值大于目标的值或者目标为*空*。

**异常:**

*   **参数异常**:如果目标和当前实例不是同一类型。
*   **无效操作异常**:如果实例不是类型 *SByte、Int16、Int32、Int64、Byte、UInt16、UInt32 或 UInt64* 。
*   **NullReferenceException** :如果当前实例为空。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# program to demonstrate the 
// Enum.CompareTo(Object) Method
using System;

public class GFG 
{ 

    enum Color 
    { 
        RED, GREEN, BLUE
    };

    // Driver method 
    public static void Main(String[] args) 
    { 
        Color c1 = Color.RED; 
        Color c2 = Color.GREEN; 
        Color c3 = Color.RED; 
        Color c4 = Color.BLUE; 

        Console.Write("Comparing {0} with {1} : ", c1, c2); 

        // CompareTo method 
        Console.WriteLine(c1.CompareTo(c2)); 

        Console.Write("Comparing {0} with {1} : ", c1, c3); 

        // CompareTo method 
        Console.WriteLine(c1.CompareTo(c3)); 

        Console.Write("Comparing {0} with {1} : ", c4, c2); 

        // CompareTo method 
        Console.WriteLine(c4.CompareTo(c2)); 

    } 
} 
```

**Output:**

```cs
Comparing RED with GREEN : -1
Comparing RED with RED : 0
Comparing BLUE with GREEN : 1

```

**例 2:**

```cs
// C# program to demonstrate the 
// Enum.CompareTo(Object) Method
using System;

public class GFG 
{ 

    enum Color{Red, Blue};

    enum Seasons {Winter, Summer};

    // Driver method 
    public static void Main(String[] args) 
    { 
        Color c1 = Color.Red; 
        Color c2 = Color.Blue; 

        Seasons s1 = Seasons.Winter;
        Seasons s2 = Seasons.Summer;

        Console.Write("Comparing {0} with {1} : ", c1, c2); 

        // CompareTo method 
        Console.WriteLine(c1.CompareTo(c2)); 

        Console.Write("Comparing {0} with {1} : ", c1, s1); 

        // using CompareTo method
        // it will give exception
        // as target and the current
        // instance are not the same
        // types
        Console.WriteLine(c1.CompareTo(s1)); 

    } 
} 
```

**运行时错误:**

> 未处理异常:
> 系统。参数异常:对象必须与枚举类型相同。传入的类型是“GFG+季节”；枚举类型是“GFG+颜色”。
> 在系统中。枚举。比较(系统。目标)<0x7ff 9d 1544610+0x 000 da<0f8 aeac 9d 63d 4 b8 aa 575761 bb4 e 65 b 79>:00f8 aeac 9d 63d 4 b8 aa 575761 bb4 e 65 b 79>0x7ff 9d 1544610>

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . enum . compare to？视图=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.enum.compareto?view=netframework-4.8)