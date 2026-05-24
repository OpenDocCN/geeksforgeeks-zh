# C # 8.0 中的索引结构

> 原文:[https://www.geeksforgeeks.org/index-struct-in-c-sharp-8-0/](https://www.geeksforgeeks.org/index-struct-in-c-sharp-8-0/)

C# 8.0 引入了一种新的预定义结构，称为索引结构。此结构用于表示可用作从开始或结束开始的集合或序列的索引的类型。它提供了一种新的索引样式来访问元素，即 **^** 运算符。该运算符用于查找指定集合或序列的最后一个元素。同样在索引结构的帮助下，您可以创建一个索引类型的变量。

**例:**

```cs
// C# program to illustrate 
// the concept of index
using System;

namespace example {

class GFG {

    // Main Method
    static void Main(string[] args)
    {

        // Creating and initializing an array
        int[] num = new int[] {1, 2, 3, 4, 5, 6, 7};

        // Accessing the starting
        // elements of the array
        Console.WriteLine("Starting Elements");
        Console.WriteLine(num[1]);
        Console.WriteLine(num[2]);
        Console.WriteLine(num[3]);

        // Accessing the last
        // elements of the array
        Console.WriteLine("Last Elements");
        Console.WriteLine(num[^2]);
        Console.WriteLine(num[^3]);
        Console.WriteLine(num[^4]);
        Console.WriteLine();

        // Index as a variable
        Index i = ^1;
        Console.WriteLine("Index as a variable: " + num[i]);
    }
}
}
```

**输出:**

```cs
Starting Elements
2
3
4
Last Elements
6
5
4

Index as a variable: 7

```

#### 建造师

| 构造器 | Description |
| **[Index (int32, Boolean)](https://www.geeksforgeeks.org/index-constructor-in-c-sharp/)** | It is used to initialize a new index with the specified index position and the value indicating whether the index starts or ends from the set. |

### 属性

| attribute | Description |
| **[End](https://www.geeksforgeeks.org/finding-the-index-which-points-beyond-the-last-element-in-c-sharp/)** | It is used to get an index that points to something other than the last element. |
| **[Is from end](https://www.geeksforgeeks.org/how-to-check-whether-the-index-is-from-start-or-end-in-c-sharp/)** | It is used to obtain a value indicating whether the index is from the beginning or the end. |
| **Start** | is used to obtain the Index pointing to the first element of the set. |
| **[Value](https://www.geeksforgeeks.org/how-to-get-the-index-value-in-c-sharp/)** | It is used to get the index value. |

### 方法

| way | Description |
| **[equals ()](https://www.geeksforgeeks.org/checking-the-given-indexes-are-equal-or-not-in-c-sharp/)** | is used to check whether a given indicator is equal to another indicator. |
| **[【 From End (Int32) 】](https://www.geeksforgeeks.org/creating-an-index-from-the-end-of-a-collection-at-a-specified-index-position-in-c-sharp/)** | It is used to create an index from the specified index position at the end of the set. |
| **[From start (int32)](https://www.geeksforgeeks.org/creating-an-index-from-the-specified-index-at-the-start-of-a-collection-in-c-sharp/)** | is used to create an index from the index specified at the beginning of the collection. |
| **[Gethashcode ()](https://www.geeksforgeeks.org/getting-the-hash-code-of-the-given-index-in-c-sharp/)** | It returns the hash code of a given instance. |
| **Getoffset (Int32)** | It is used to calculate the offset from the set with a given set length. |
| **Tostring ()** | The string representation used to return the current Index instance. |