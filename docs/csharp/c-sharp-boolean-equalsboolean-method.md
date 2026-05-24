# C# |布尔型。等于(布尔)法

> 原文:[https://www . geesforgeks . org/c-sharp-boolean-equals boolin-method/](https://www.geeksforgeeks.org/c-sharp-boolean-equalsboolean-method/)

此方法用于返回一个值，该值指示此实例是否等于指定的布尔对象。
**语法:**

```cs
public bool Equals (bool obj);
```

这里， *obj* 是一个布尔值，用于与该实例进行比较。
**返回值:**如果 obj 与该实例具有相同的值，则该方法返回 *true* ，否则返回 *false* 。
下面的程序说明了**布尔值的使用。Equals(bool obj)** 方法:
**示例 1:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to demonstrate
// Boolean.Parse(String)
// Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        // passing different values
        // to the method to check
        check(true, true);
        check(true, false);
        check(false, true);
        check(false, false);
    }

    // Defining check method
    public static void check(bool input1, bool input2)
    {

        // declaring bool variable
        bool val;

        // getting parsed value
        val = input1.Equals(input2);

        // checking the equivalency
        if (val == true)
            Console.WriteLine("{0} is equal to {1}",
                                    input1, input2);

        else
            Console.WriteLine("{0} is not equal to {1}",
                                        input1, input2);
    }
}
```

**Output:** 

```cs
True is equal to True
True is not equal to False
False is not equal to True
False is equal to False
```

**例 2:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to demonstrate
// Boolean.Parse(String)
// Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        // Declaring the variable
        // input1 and input2
        bool input1, input2;

        // initializing the variables
        input1 = true;
        input2 = false;

        // checking the equality
        bool val = input1.Equals(input2);

        // checking the equivalency
        if (val == true)
            Console.WriteLine("input1 is equal to input2");

        else
            Console.WriteLine("input1 is not equal to input2");
    }
}
```

**Output:** 

```cs
input1 is not equal to input2
```

**注:**此方法实现系统。IEquatable < T >接口，性能比 Equals 略好，因为它不用把 obj 参数转换成对象。
T3【参考:T5】

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . boolean . equals？view = net framework-4 . 7 . 2 # System _ Boolean _ Equals _ System _ Boolean _](https://docs.microsoft.com/en-us/dotnet/api/system.boolean.equals?view=netframework-4.7.2# System_Boolean_Equals_System_Boolean_)