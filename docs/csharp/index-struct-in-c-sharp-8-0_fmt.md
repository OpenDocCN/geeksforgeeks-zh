# C# 8.0 中的索引结构

> 原文：[https://www.geeksforgeeks.org/index-struct-in-c-sharp-8-0/](https://www.geeksforgeeks.org/index-struct-in-c-sharp-8-0/)

C# 8.0 引入了一种新的预定义结构，称为索引结构。此结构用于表示可用作从开始或结束开始的集合或序列的索引的类型。它提供了一种新的索引样式来访问元素，即 `^` 运算符。该运算符用于查找指定集合或序列的最后一个元素。同样在索引结构的帮助下，您可以创建一个索引类型的变量。

例：

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

输出：

```cs
Starting Elements

Last Elements

Index as a variable: 7
```

## 构造器

| 构造器 | 描述 |
| --- | --- |
| `Index(int32, Boolean)` | 用于初始化一个新的索引，指定索引位置以及一个指示该索引是从集合的开始还是结束计算的布尔值。 |

## 属性

| 属性 | 描述 |
| --- | --- |
| `End` | 用于获取指向最后一个元素之后位置的索引。 |
| `IsFromEnd` | 用于获取一个值，该值指示索引是从集合的开头还是末尾计算的。 |
| `Start` | 用于获取指向集合第一个元素的索引。 |
| `Value` | 用于获取索引值。 |

## 方法

| 方法 | 描述 |
| --- | --- |
| `Equals()` | 用于检查给定的索引是否等于另一个索引。 |
| `FromEnd(Int32)` | 用于从集合末尾的指定索引位置创建一个索引。 |
| `FromStart(Int32)` | 用于从集合开头的指定索引位置创建一个索引。 |
| `GetHashCode()` | 返回给定索引实例的哈希代码。 |
| `GetOffset(Int32)` | 用于计算给定集合长度下的偏移量。 |
| `ToString()` | 返回当前 `Index` 实例的字符串表示形式。 |