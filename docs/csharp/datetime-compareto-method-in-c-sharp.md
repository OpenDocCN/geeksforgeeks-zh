# 日期时间。C# 中的 CompareTo()方法

> 原文:[https://www . geesforgeks . org/datetime-compare to-method-in-c-sharp/](https://www.geeksforgeeks.org/datetime-compareto-method-in-c-sharp/)

此方法用于将此实例的值与指定的日期时间值进行比较，并指示此实例是早于、等于还是晚于指定的日期时间值。*该方法的重载列表中有两种方法如下:*

*   **比较到（日期时间）**
*   **比较(对象)**

##### **比较日期时间方法**

**此方法用于将此实例的值与指定的日期时间值进行比较，并返回一个整数，该整数指示此实例是早于、等于还是晚于指定的日期时间值。**

****语法:****

```cs
public int CompareTo (DateTime value);
```

**这里，参数*值*是要与当前实例进行比较的对象。**

****返回值:**这个方法返回一个带符号的数字，表示这个实例和值参数的相对值。**

*   ****小于零**:如果该实例早于值。**
*   ****零**:如果该实例与值相同。**
*   ****大于零**:如果该实例晚于值。**

****示例:****

```cs
// C# code to demonstrate
// CompareTo(DateTime) function
using System;

public class GFG {

    // Main Method
    public static void Main()
    {

        // Taking two DateTime Objects
        DateTime d1 = new DateTime(2018, 12,
                              31, 16, 0, 0);

        DateTime d2 = new DateTime(2018, 12,
                              31, 20, 0, 0);

        // Using the method
        int res = d1.CompareTo(d2);

        string r;

        if (res > 0)
            r = "is later than";

        else if (res == 0)
            r = "is the same time as";
        else
            r = "is earlier than";

        Console.WriteLine("{0} {1} {2}", d1, r, d2);
    }
}
```

****Output:**

```cs
12/31/2018 16:00:00 is earlier than 12/31/2018 20:00:00

```** 

##### **比较对象方法**

**此方法用于将此实例的值与包含指定日期时间值的指定对象进行比较，并返回一个整数，该整数指示此实例是早于、等于还是晚于指定日期时间值。**

****语法:****

```cs
public int CompareTo (object value);
```

**这里参数*值*是要比较的装箱对象，或者为空。**

****返回值:**这个方法返回一个带符号的数字，表示这个实例和值参数的相对值。**

*   ****小于零**:如果该实例早于值。**
*   ****零**:如果该实例与值相同。**
*   ****大于零**:如果该实例晚于值。**

****异常:**如果*值*不是日期时间，此方法将给出*参数异常*。**

****示例:****

```cs
// C# code to demonstrate
// CompareTo(Object) function
using System;

public class GFG {

    // Main Method
    public static void Main()
    {

        // Taking a DateTime Object
        DateTime d1 = new DateTime(2018, 12,
                              31, 16, 0, 0);

        // Using the method
        // Here, "DateTime.Today" is
        // the property of DateTime struct
        int res = d1.CompareTo(DateTime.Today);

        string r;

        if (res > 0)
            r = "is later than";

        else if (res == 0)
            r = "is the same time as";
        else
            r = "is earlier than";

        Console.WriteLine("{0} {1} {2}", d1, r, 
                                DateTime.Today);
    }
}
```

****输出:****

```cs
12/31/2018 16:00:00 is earlier than 01/21/2019 00:00:00
```

****参考:****

*   **[https://docs . Microsoft . com/en-us/dotnet/API/system . datetime . compare to？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.datetime.compareto?view=netframework-4.7.2)**