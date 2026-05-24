# c# 中的对象和动态数组

> 原文:[https://www . geesforgeks . org/object-and-dynamic-array-in-c-sharp/](https://www.geeksforgeeks.org/object-and-dynamic-array-in-c-sharp/)

一个 ***[数组](https://www.geeksforgeeks.org/c-sharp-arrays/)*** 是一组相似类型的变量，用一个共同的名字来指代。每个数据项被称为数组的一个元素。元素的数据类型可以是任何有效的数据类型，如 char、int、float 等。并且元素被存储在连续的位置。

#### 对象数组

对象数组用于在单个数组中存储不同类型的元素。在 C# 中，对象引用可以指向任何派生类型实例。

**对象数组的缺点:**

*   It makes the code more complicated.
*   It reduces the running time of the program.

**例:**

```cs
// C# program to illustrate the
// concept of object array
using System;

class GFG {

    // Main method
    static public void Main()
    {

        // Creating and initializing 
        // object array
        object[] arr = new object[6];

        arr[0] = 3.899;
        arr[1] = 3;
        arr[2] = 'g';
        arr[3] = "Geeks";

        // it will display 
        // nothing in output
        arr[4] = null;

        // it will show System.Object
        // in output
        arr[5] = new object();

        // Display the element of 
        // an object array
        foreach(var item in arr)
        {
            Console.WriteLine(item);
        }
    }
}
```

**输出:**

```cs
3.899
3
g
Geeks

System.Object

```