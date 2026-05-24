# C# |如何创建堆栈

> 原文:[https://www . geeksforgeeks . org/c-sharp-如何创建堆栈/](https://www.geeksforgeeks.org/c-sharp-how-to-create-a-stack/)

`Stack()`构造函数用于初始化 `Stack` 类的一个新实例，该实例将为空，并具有默认的初始容量。[堆栈](https://www.geeksforgeeks.org/c-sharp-stack-class/)代表后进先出的对象集合。当您需要后进先出访问项目时，可以使用它。当您在列表中添加一个项目时，它被称为推送项目，当您删除它时，它被称为弹出项目。这个类属于`System.Collections` 命名空间。

## 语法:

```cs
public Stack ();
```

## 要点:

*   堆栈中可以容纳的元素数量称为堆栈容量。如果要向堆栈添加元素，容量将通过重新分配内部数组自动增加。
*   如果可以估计集合的大小，指定初始容量将消除在向堆栈添加元素时执行大量调整大小操作的需要。
*   此构造函数是一个 `O(1)` 操作。

## 例 1:

```cs
// C# Program to illustrate how
// to create a Stack
using System;
using System.Collections;

class Geeks {

// Main Method
    public static void Main(String[] args)
    {

// st is the Stack object
        // Stack() is the constructor
        // used to initializes a new
        // instance of the Stack class
        Stack st = new Stack();

// Count property is used to get the
        // number of elements in Stack
        // It will give 0 as no elements
        // are present currently
        Console.WriteLine(st.Count);
    }
}
```

## 输出:

```cs

```