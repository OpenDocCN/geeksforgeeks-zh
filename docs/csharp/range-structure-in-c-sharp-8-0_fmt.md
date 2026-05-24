# C# 8.0 中的范围结构

> 原文：[https://www.geeksforgeeks.org/range-structure-in-c-sharp-8-0/](https://www.geeksforgeeks.org/range-structure-in-c-sharp-8-0/)

C# 8.0 引入了一种新的预定义结构，称为范围结构。此结构用于表示具有开始和结束索引的范围。它提供了一种使用创建范围的新样式 `..` 运算符。此运算符用于创建一个具有起始索引和结束索引的范围。同样，在范围结构的帮助下，您可以创建一个范围类型的变量。

## C\#

```cs
// C# program to illustrate how to create ranges
using System;

namespace range_example {

class GFG {

    // Main Method
    static void Main(string[] args)
    {
        int[] marks = new int[] {23, 45, 67, 88, 99,
                            56, 27, 67, 89, 90, 39};

        // Creating variables of range type
        // And initialize the range
        // variables with a range
        // Using .. operator
        Range r1 = 1..5;
        Range r2 = 6..8;

        var a1 = marks[r1];
        Console.Write("Marks List 1: ");
        foreach(var st_1 in a1)
            Console.Write($" {st_1} ");

        var a2 = marks[r2];
        Console.Write("\nMarks List 2: ");
        foreach(var st_2 in a2)
            Console.Write($" {st_2} ");

        // Creating a range
        // Using .. operator
        var a3 = marks[2..4];
        Console.Write("\nMarks List 3: ");
        foreach(var st_3 in a3)
            Console.Write($" {st_3} ");

        var a4 = marks[4..7];
        Console.Write("\nMarks List 4: ");
        foreach(var st_4 in a4)
            Console.Write($" {st_4} ");
    }
}
}
```

**输出：**

```cs
Marks List 1:  45  67  88  99 
Marks List 2:  27  67 
Marks List 3:  67  88 
Marks List 4:  99  56  27
```

### 构造器

| 构造器 | 描述 |
| --- | --- |
| [`Range(Index, Index)`](https://www.geeksforgeeks.org/range-constructor-in-c-sharp/) | 此构造函数用于使用指定的开始和结束索引创建新的范围实例。 |

### 属性

| 属性 | 描述 |
| --- | --- |
| [`All`](https://www.geeksforgeeks.org/finding-all-the-elements-of-a-range-from-start-to-end-in-c-sharp/) | 此属性用于获取从第一个元素开始到结束的范围对象。 |
| [`End`](https://www.geeksforgeeks.org/finding-the-end-index-of-the-specified-range-in-c-sharp/) | 此属性用于获取一个索引，该索引表示该范围的独占结束索引。 |
| [`Start`](https://www.geeksforgeeks.org/finding-the-start-index-of-the-specified-range-in-c-sharp/) | 此属性用于获取范围的包含起始索引。 |

### 方法

| 方法 | 描述 |
| --- | --- |
| [`EndAt(Index)`](https://www.geeksforgeeks.org/how-to-create-a-range-to-a-specified-end-in-c-sharp/) | 此方法用于创建从集合中的第一个元素开始到指定结束索引的范围对象。 |
| [`Equals()`](https://www.geeksforgeeks.org/check-if-the-given-ranges-are-equal-or-not-in-c-sharp/) | 此方法用于检查当前范围是否等于指定范围。 |
| [`GetHashCode()`](https://www.geeksforgeeks.org/getting-the-hash-code-of-the-specified-range-in-c-sharp/) | 此方法用于查找此实例的哈希代码。 |
| [`GetOffsetAndLength(Int32)`](https://www.geeksforgeks.org/getting-the-hash-code-of-the-specified-range-in-c-sharp/) | 此方法用于在集合长度的帮助下计算给定范围对象的起始偏移量和长度。 |
| [`Start(Index)`](https://www.geeksforgeeks.org/how-to-create-a-range-from-a-specified-start-in-c-sharp/) | 此方法用于创建一个新的范围实例，从指定的起始索引开始到集合的结尾。 |
| [`ToString()`](https://www.geeksforgeeks.org/getting-the-hash-code-of-the-specified-range-in-c-sharp/) | 此方法返回当前范围对象的字符串表示形式。 |