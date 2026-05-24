# C# | Char。比较()方法

> 原文:[https://www . geesforgeks . org/c-sharp-char-compare to-method/](https://www.geeksforgeeks.org/c-sharp-char-compareto-method/)

在 C# 中， ***Char。**T3 是一个*系统。Char* struct 方法，用于比较指定对象或值类型的此实例，并检查给定实例是否在指定对象或值类型之前、之后或出现在排序顺序中的相同位置。可以通过向该方法传递不同类型的参数来重载该方法。*

*   **Char。比较(充电)方法**
*   **Char。**
    比较法

#### 夏尔。比较(字符)方法

此方法用于将此实例与指定的 Char 对象进行比较，并检查此实例是否在指定的 Char 对象之前、之后或出现在排序顺序中的相同位置。

**语法:**

```cs
public int CompareTo(Char ch);
```

**参数:**

> **ch** :需要比较的是需要的 Char 对象。

**返回类型:**它返回一个带符号的数字，表示实例在排序顺序中相对于 *ch* 参数的位置。这种方法的返回类型是*系统。Int32* 。下表显示了返回值的不同情况:

<figure class="table">

| 返回值 | 描述 |
| --- | --- |
| 小于零 | 这个例子在 *ch* 之前。 |
| 零 | 该实例在排序中的位置与 *ch* 中的位置相同。 |
| 大于零 | 这个例子跟在 *ch* 后面。 |

</figure>

**示例:**

## C#

```cs
// C# program to demonstrate the
// Char.CompareTo(Char) Method
using System;

class CompareToSample {

    // Main Method
    public static void Main()
    {
        char ch1 = 'Z';
        char ch2 = 'g';
        char ch3 = 'A';

        // using Char.CompareTo(Char) Method
        // returns 0 as this instance has
        // same position in the sort as in ch1
        Console.WriteLine('Z'.CompareTo(ch1));

        // using Char.CompareTo(Char) Method
        // returns -13 as this instance
        // precedes ch2
        Console.WriteLine('Z'.CompareTo(ch2));

        // using Char.CompareTo(Char) Method
        // returns 25 as this instance follows
        // ch3
        Console.WriteLine('Z'.CompareTo(ch3));
    }
}
```

**Output:** 

```cs
0
-13
25
```

#### 夏尔。比较对象方法

此方法用于将此实例与指定的对象进行比较，并检查此实例是否在指定对象之前、之后或出现在排序顺序中的相同位置。任何 Char 实例的值都被认为大于 null。

**语法:**

```cs
public int CompareTo(object obj);
```

**参数:**

> **obj** :需要与该实例进行比较的对象，否则为空。

**返回类型:**它返回一个带符号的数字，表示实例在排序顺序中相对于*对象*参数的位置。这种方法的返回类型是*系统。Int32* 。下表显示了返回值的不同情况:

<figure class="table">

| 返回值 | 描述 |
| --- | --- |
| 小于零 | 这个例子在 *obj* 之前。 |
| 零 | 该实例在排序中的位置与*对象*中的位置相同。 |
| 大于零 | 这个例子跟随着 *obj* 或者 *obj* 是*空*。 |

</figure>

**异常:**如果对象不是 Char 对象，那么这个方法将给出*参数异常*。

**示例:**

## C#

```cs
// C# program to illustrate the
// Char.CompareTo(Object) Method
using System;

class GeeksforGeeks {

    // Main method
    public static void Main()
    {

        // declaration of data type
        char ch1 = 'G';
        char ch2 = 'a';
        char ch3 = 'B';
        int output;

        // compare ch1 with G, as they are
        // equal so output will be zero
        output = ch1.CompareTo('G');
        Console.WriteLine(output);

        // compare ch3 with ch2
        // output is -31 which means
        // ch3 is less than ch2 by -31
        output = ch3.CompareTo(ch2);
        Console.WriteLine(output);

        // compare ch1 with ch3
        // output is 5 which means
        // ch1 is greater then ch3 by 5
        output = ch1.CompareTo(ch3);
        Console.WriteLine(output);
    }
}
```

**Output:** 

```cs
0
-31
5
```

**参考:**T2？视图=netframework-4.7.2