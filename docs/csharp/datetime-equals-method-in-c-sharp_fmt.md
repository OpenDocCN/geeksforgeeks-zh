# DateTime.Equals 方法在 C# 中

> 原文：[`https://www.geeksforgeeks.org/datetime-equals-method-in-c-sharp/`](https://www.geeksforgeeks.org/datetime-equals-method-in-c-sharp/)

此方法用于获取一个值，该值指示两个 `DateTime` 对象、一个 `DateTime` 实例和另一个对象或 `DateTime` 是否具有相同的值。该方法的重载列表中总共有 3 个方法：

*   `Equals(DateTime, DateTime)`
*   `Equals(DateTime)`
*   `Equals(Object)`

## Equals(DateTime, DateTime)

此方法用于返回一个值，该值指示两个 `DateTime` 实例是否具有相同的日期和时间值。

### 语法

```cs
public static bool Equals (DateTime t1, DateTime t2);
```

### 参数

*   `t1`: 第一个比较的对象。
*   `t2`: 要比较的第二个对象。

### 返回值

如果两个值相等，则该方法返回 `true`；否则，为 `false`。

以下程序说明了 `DateTime.Equals(DateTime, DateTime)` 方法的使用：

### 例 1

```cs
// C# program to demonstrate the
// DateTime.Equals(DateTime,
//  DateTime) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // creating object of DateTime
        DateTime date1 = new DateTime(2010, 1,
                                 1, 4, 0, 15);

        // creating object of DateTime
        DateTime date2 = new DateTime(2010, 1,
                                 1, 4, 0, 14);

        // comparing date1 and date2
        // using Equals() method;
        bool value = DateTime.Equals(date1, date2);

        // checking
        if (value)
            Console.Write("date1 is equals to date2. ");
        else
            Console.Write("date1 is not equals to date2. ");
    }
}
```

### 输出

```cs
date1 is not equals to date2.
```

### 例 2

```cs
// C# program to demonstrate the
// DateTime.Equals(DateTime,
// DateTime) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // calling check() method
        check(new DateTime(2010, 1, 3, 4, 0, 15),
              new DateTime(2010, 1, 4, 4, 0, 15));

        check(new DateTime(2010, 1, 5, 4, 0, 15),
              new DateTime(2010, 1, 4, 4, 0, 15));

        check(new DateTime(2010, 1, 5, 4, 0, 15),
              new DateTime(2010, 1, 5, 4, 0, 15));
    }
    public static void check(DateTime date1, DateTime date2)
    {

        // comparing date1 and date2
        // using Equals() method;
        bool value = DateTime.Equals(date1, date2);

        // checking
        if (value)
            Console.WriteLine(" {0:d} is equals to"+
                          " {1:d}. ", date1, date2);
        else
            Console.WriteLine(" {0:d} is not equals"+
                        " to {1:d}. ", date1, date2);
    }
}
```

### 输出

```cs
1/3/2010 is not equals to 1/4/2010. 
1/5/2010 is not equals to 1/4/2010. 
1/5/2010 is equals to 1/5/2010. 
```

## Equals(DateTime)

此方法用于返回一个值，该值指示此实例的值是否等于指定的 `DateTime` 实例的值。

### 语法

```cs
public bool Equals (DateTime value);
```

这里，它将对象与这个实例进行比较。

### 返回值

如果 `value` 参数等于该实例的值，则该方法返回 `true`；否则，为 `false`。

以下程序说明了 `DateTime.Equals(DateTime)` 方法的使用：

### 例 1

```cs
// C# program to demonstrate the
// DateTime.Equals(DateTime) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // creating object of DateTime
        DateTime date1 = new DateTime(2010, 1,
                                 1, 4, 0, 15);

        // creating object of DateTime
        DateTime date2 = new DateTime(2010, 1,
                                 1, 4, 0, 14);

        // comparing date1 and date2
        // using Equals() method;
        bool value = date1.Equals(date2);

        // checking
        if (value)
            Console.Write("date1 is equals to date2. ");
        else
            Console.Write("date1 is not equals to date2. ");
    }
}
```

### 输出

```cs
date1 is not equals to date2. 
```

### 例 2

```cs
// C# program to demonstrate the
// DateTime.Equals(DateTime) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // calling check() method
        check(new DateTime(2010, 1, 3, 4, 0, 15),
              new DateTime(2010, 1, 4, 4, 0, 15));

        check(new DateTime(2010, 1, 5, 4, 0, 15),
              new DateTime(2010, 1, 4, 4, 0, 15));

        check(new DateTime(2010, 1, 5, 4, 0, 15),
              new DateTime(2010, 1, 5, 4, 0, 15));
    }

    public static void check(DateTime date1,
                             DateTime date2)
    {

        // comparing date1 and date2
        // using Equals() method;
        bool value = date1.Equals(date2);

        // checking
        if (value)
            Console.WriteLine(" {0:d} is equals to"+
                          " {1:d}. ", date1, date2);
        else
            Console.WriteLine(" {0:d} is not equals "+
                          "to {1:d}. ", date1, date2);
    }
}
```

### 输出

```cs
01/03/2010 is not equals to 01/04/2010. 
01/05/2010 is not equals to 01/04/2010. 
01/05/2010 is equals to 01/05/2010. 
```

## Equals(Object)

此方法用于返回一个值，该值指示此实例是否等于指定的对象。

### 语法

```cs
public override bool Equals (object value);
```

这里，它将对象与这个实例进行比较。

### 返回值

如果 `value` 参数等于该实例的值，该方法返回 `true`，否则返回 `false`。

以下程序说明了 `DateTime.Equals(Object)` 方法的使用：

### 例 1

```cs
// C# program to demonstrate the
// DateTime.Equals(DateTime) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {

        // creating object of DateTime
        DateTime date1 = new DateTime(2010, 1,
                                  1, 4, 0, 15);

        // creating object of DateTime
        DateTime date2 = new DateTime(2010, 1,
                                 1, 4, 0, 14);

        // comparing date1 and date2
        // using Equals() method;
        bool value = date1.Equals(date2);

        // checking
        if (value)
            Console.Write("date1 is equals to date2. ");
        else
            Console.Write("date1 is not equals to date2. ");
    }
}
```

### 输出

```cs
date1 is not equals to date2. 
```

### 例 2

```cs
// C# program to demonstrate the
// DateTime.Equals(DateTime) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {

        // calling check() method
        check(new DateTime(2010, 1, 3, 4, 0, 15),
              new DateTime(2010, 1, 4, 4, 0, 15));

        check(new DateTime(2010, 1, 5, 4, 0, 15),
              new DateTime(2010, 1, 4, 4, 0, 15));

        check(new DateTime(2010, 1, 5, 4, 0, 15),
              new DateTime(2010, 1, 5, 4, 0, 15));
    }

    public static void check(DateTime date1,
                             DateTime date2)
    {

        // comparing date1 and date2
        // using Equals() method;
        bool value = date1.Equals(date2);

        // checking
        if (value)
            Console.WriteLine(" {0:d} is equals "+
                       "to {1:d}. ", date1, date2);
        else
            Console.WriteLine(" {0:d} is not equals"+
                          " to {1:d}. ", date1, date2);
    }
}
```

### 输出

```cs
 01/03/2010 is not equals to 01/04/2010. 
 01/05/2010 is not equals to 01/04/2010. 
 01/05/2010 is equals to 01/05/2010. 
```

### 参考

*   [`https://docs.microsoft.com/en-us/dotnet/api/system.datetime.equals?view=netframework-4.7.2`](https://docs.microsoft.com/en-us/dotnet/api/system.datetime.equals?view=netframework-4.7.2)