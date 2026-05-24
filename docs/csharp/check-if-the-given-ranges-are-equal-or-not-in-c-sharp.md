# 检查 C# 中给定的范围是否相等

> 原文:[https://www . geeksforgeeks . org/check-如果给定范围等于或不等于 c-sharp/](https://www.geeksforgeeks.org/check-if-the-given-ranges-are-equal-or-not-in-c-sharp/)

在 C# 8.0 中引入了[范围结构](https://www.geeksforgeeks.org/range-structure-in-c-sharp-8-0/)。它表示一个有开始和结束索引的范围。您可以借助 Range 结构提供的以下方法来检查给定的范围是否相等:

**1。等于(对象):**这个方法是[对象类](https://www.geeksforgeeks.org/c-sharp-object-class/)方法，它返回一个值，显示给定的范围对象等于另一个范围对象。如果返回 true，则当前 range 对象等于另一个 range 对象；如果返回 false，则当前 range 对象不等于另一个 range 对象。

**语法:**

```cs
public override bool Equals(System::Object ^ value);
```

**示例:**

```cs
// C# program to illustrate how to 
// check the given ranges is equal or not
// Using Equals(object) method of Range struct
using System;

namespace range_example {

class GFG {

    // Main Method
    static void Main(string[] args)
    {

        // Creating a range
        // using StartAt() method
        var r1 = Range.StartAt(3);
        var r2 = Range.StartAt(4);

        // Checking the ranges
        // are equal or not
        // Using Equals(Object) method
        if (r1.Equals(r2)) {

            Console.WriteLine("Both range 1{0} and range"+
                              " 2 {1} are equal", r1, r2);
        }

        else {

            Console.WriteLine("Both ranges are not equal");
        }
    }
}
}
```

**输出:**

```cs
Both ranges are not equal
```

**2。等于(范围):**这个方法返回一个值，显示给定的对象等于另一个对象。如果返回 true，则当前对象等于另一个 range 对象；如果返回 false，则当前对象不等于另一个 range 对象。

**示例:**

```cs
// C# program to illustrate how to 
// check the given ranges is equal or not
// Using Equals(Range) method of Range struct
using System;

namespace range_example {

class GFG {

    // Main Method
    static void Main(string[] args)
    {

        // Creating a ranges
        Range r1 = 1..8;
        Range r2 = 1..8;

        // Checking the ranges
        // are equal or not
        // Using Equals(Range) method
        if (r1.Equals(r2)) {

            Console.WriteLine("Both ranges are equal");
        }

        else {

            Console.WriteLine("Both ranges are not equal");
        }
    }
}
}
```

**输出:**

```cs
Both ranges are equal
```