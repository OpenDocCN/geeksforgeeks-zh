# 翻倍。C# 中的 Equals()方法及示例

> 原文:[https://www . geesforgeks . org/double-equals-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/double-equals-method-in-c-sharp-with-examples/)

**翻倍。Equals()方法**用于获取一个值，该值指示 Double 的两个实例是否表示相同的值。该方法的重载列表中总共有两种方法，如下所示:

*   **等于(双倍)法**
*   **等于(对象)法**

#### 双倍。等于(双倍)

此方法用于返回一个值，该值指示此实例和指定的 Double 对象是否表示相同的值。

> **语法:**public bool Equals(double obj)；
> 在这里，需要一个 Double 对象来与这个实例进行比较。
> **返回值:**如果 obj 等于这个实例，这个方法返回 true 否则，为假。

以下程序说明了 **Double 的使用。Equals()** 方法:

**例 1:**

## C#

```cs
// C# program to demonstrate the
// Double.Equals(Double)
// Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // Declaring and initializing value1
        double value1 = 10d;

        // Declaring and initializing value2
        double value2 = 20d;

        // compare both double value
        // using Equals(Double) method
        bool status = value1.Equals(value2);

        // checking the status
        if (status)
            Console.WriteLine("{0} is equal to {1}",
                                    value1, value2);
        else
            Console.WriteLine("{0} is not equal to {1}",
                                        value1, value2);
    }
}
```

**Output:** 

```cs
10 is not equal to 20
```

**例 2:**

## C#

```cs
// C# program to demonstrate the
// Double.Equals(Double)
// Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {

        // calling get() method
        get(5d, 5d);
        get(5.5d, 4.5d);
        get(10d, 20d);
        get(7.5d, 19.5d);
    }

    // defining get() method
    public static void get(double value1, double value2)
    {

        // compare both double value
        // using Equals(Double) method
        bool status = value1.Equals(value2);

        // checking the status
        if (status)
            Console.WriteLine("{0} is equal to {1}",
                                    value1, value2);
        else
            Console.WriteLine("{0} is not equal to {1}",
                                        value1, value2);
    }
}
```

**Output:** 

```cs
5 is equal to 5
5.5 is not equal to 4.5
10 is not equal to 20
7.5 is not equal to 19.5
```

#### 双倍。等于(对象)方法

此方法用于返回一个值，该值指示此实例是否等于指定的对象。

> **语法:**公共覆盖 bool Equals(对象 obj)；
> 在这里，需要一个对象来与这个实例进行比较。
> **返回值:**如果 *obj* 是 Double 的实例，并且等于该实例的值，则该方法返回 true 否则，为假。

以下程序说明了上述方法的使用:

**例 1:**

## C#

```cs
// C# program to demonstrate the
// Double.Equals(Object)
// Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // Declaring and initializing value1
        double value1 = 10d;

        // Declaring and initializing value2
        object value2 = 1 / 36;

        // compare both double value
        // using Equals(object) method
        bool status = value1.Equals(value2);

        // checking the status
        if (status)
            Console.WriteLine("{0} is equal to {1}",
                                   value1, value2);
        else
            Console.WriteLine("{0} is not equal to {1}",
                                        value1, value2);
    }
}
```

**Output:** 

```cs
10 is not equal to 0
```

**例 2:**

## C#

```cs
// C# program to demonstrate the
// Double.Equals(object)
// Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // calling get() method
        get(5d, 1 / 3);
        get(5.5d, 1 / 3);
        get(10d, 1 / 24);
        get(7.5d, 2 / 5);
    }

    // defining get() method
    public static void get(double value1, object value2)
    {

        // compare both double value
        // using Equals(object) method
        bool status = value1.Equals(value2);

        // checking the status
        if (status)
            Console.WriteLine("{0} is equal to {1}",
                                    value1, value2);
        else
            Console.WriteLine("{0} is not equal to {1}",
                                        value1, value2);
    }
}
```

**Output:** 

```cs
5 is not equal to 0
5.5 is not equal to 0
10 is not equal to 0
7.5 is not equal to 0
```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . double . equals？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.double.equals?view=netframework-4.7.2)