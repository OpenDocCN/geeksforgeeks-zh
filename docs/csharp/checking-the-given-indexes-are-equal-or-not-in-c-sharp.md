# 在 C# 中检查给定的索引是否相等

> 原文:[https://www . geeksforgeeks . org/checking-给定的索引是否等于 c-sharp/](https://www.geeksforgeeks.org/checking-the-given-indexes-are-equal-or-not-in-c-sharp/)

在 C# 8.0 中引入了[索引结构](https://www.geeksforgeeks.org/index-struct-in-c-sharp-8-0/)。它表示可用于索引集合或序列的类型，并且可以从开始或结束开始。您可以通过索引结构提供的以下方法(**相等方法**)来比较两个索引是否相等:

### 1.等于(索引)

此方法返回一个值，该值显示给定对象等于另一个对象。如果返回 true，则当前对象等于另一个对象，如果返回 false，则当前对象不等于另一个对象，则结果为 bool 形式。

**语法:**

```cs
public virtual bool Equals(Index other);
```

**示例:**

```cs
// C# program to illustrate the
// concept of the Equals(index) method
using System;

namespace example {

class GFG {

    // Main Method
    static void Main(string[] args)
    {

        // Creating and initializing an array
        string[] greetings = new string[] {"Hello", "Hola", "Namaste",
                                "Bonjour", "Ohayo", "Ahnyounghaseyo"};

        // Get the end index
        var res = Index.Start;

        // Checking the given index 
        // is the start index or not
        // Using Equals(index) method
        if (res.Equals(0) == true) {

            Console.WriteLine("The given index is start index"+
                      " and the element is " + greetings[res]);
        }
        else {

            Console.WriteLine("The given index is not the start index ");
        }
    }
}
}
```

**输出:**

```cs
The given index is start index and the element is Hello
```

### 2.等于(对象)

此方法返回一个值，该值显示给定的索引对象等于另一个索引对象。如果返回 true，则当前索引对象等于另一个索引对象；如果返回 false，则当前索引对象不等于另一个索引对象，则结果为 bool 形式。

**语法:**

```cs
public override bool Equals(System::Object ^ value);
```

**示例:**

```cs
// C# program to illustrate the concept
// of the Equals(object) method
using System;

namespace example {

class GFG {

    // Main Method
    static void Main(string[] args)
    {
        // Creating and initializing an array
        string[] greetings = new string[] {"Hello", "Hola", "Namaste",
                                "Bonjour", "Ohayo", "Ahnyounghaseyo"};

        // Creating index
        // Using Index() constructor
        var val1 = new Index(1, true);
        var val2 = new Index(2, false);

        // Checking the given both the
        // index values are equal or not
        // Using Equals(object)
        if (val1.Value.Equals(val2.Value) == true) {

            Console.WriteLine("Both the indexes are equal and"+
              " their elements are :{0}, {1}", greetings[val1], 
                                              greetings[val2]);
        }
        else {

            Console.WriteLine("Both the indexes are not equal and"+
                  " their elements are: {0}, {1}", greetings[val1],
                                                  greetings[val2]);
        }
    }
}
}
```

**输出:**

```cs
Both the indexes are not equal and their elements are: Ahnyounghaseyo, Namaste
```