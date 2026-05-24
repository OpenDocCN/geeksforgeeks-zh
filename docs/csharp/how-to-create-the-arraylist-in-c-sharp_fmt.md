# 如何在 C# 中创建数组列表

> 原文：[https://www.geeksforgeeks.org/how-to-create-the-arraylist-in-c-sharp/](https://www.geeksforgeeks.org/how-to-create-the-arraylist-in-c-sharp/)

`ArrayList()`构造函数用于初始化`ArrayList`类的一个新实例，该实例将为空，并具有默认的初始容量。[数组列表](https://www.geeksforgeeks.org/arraylist-in-c-sharp/)表示可以单独索引的对象的有序集合。它基本上是数组的替代。它还允许动态内存分配、添加、搜索和排序列表中的项目。

## 语法：

```cs
public ArrayList ();
```

## 要点：

*   数组列表可以容纳的元素数量称为其[容量](https://www.geeksforgeeks.org/c-sharp-get-or-set-the-number-of-elements-that-the-arraylist-can-contain/)。如果要向数组列表添加元素，容量将通过重新分配内部数组而自动增加。
*   如果可以估计集合的大小，指定初始容量将避免在向数组列表添加元素时执行大量调整大小的操作。
*   此构造函数是一个 O(1) 操作。

## 例 1：

```cs
// C# Program to illustrate how
// to create a ArrayList
using System;
using System.Collections;

class Geeks {

// Main Method
    public static void Main(String[] args)
    {

// arrlist is the ArrayList object
        // ArrayList() is the constructor
        // used to initializes a new
        // instance of the ArrayList class
        ArrayList arrlist = new ArrayList();

// Count property is used to get the
        // number of elements in ArrayList
        // It will give 0 as no elements
        // are present currently
        Console.WriteLine(arrlist.Count);
    }
}
```

## 输出：

```cs

```