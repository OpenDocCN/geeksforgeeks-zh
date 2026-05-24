# C# |获取整个数组列表的枚举数

> 原文：[https://www.geeksforgeeks.org/c-sharp-getting-an-enumerator-for-the-entire-arraylist/](https://www.geeksforgeeks.org/c-sharp-getting-an-enumerator-for-the-entire-arraylist/)

`ArrayList.GetEnumerator` 方法用于获取整个 [`ArrayList`](https://www.geeksforgeeks.org/c-arraylist-class/) 的枚举器。

## 语法：

```cs
public virtual System.Collections.IEnumerator GetEnumerator ();
```

**返回值：** 它为整个数组列表返回一个 `IEnumerator`。

以下程序说明了上述方法的使用：

## 例 1：

```cs
// C# code to get an enumerator
// for the entire ArrayList
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating an ArrayList
        ArrayList myList = new ArrayList();

        // adding elements in myList
        myList.Add("Geeks");
        myList.Add("GFG");
        myList.Add("C#");
        myList.Add("Tutorials");

        // To get an Enumerator
        // for the ArrayList
        IEnumerator enumerator = myList.GetEnumerator();

        // If MoveNext passes the end of the
        // collection, the enumerator is positioned
        // after the last element in the ArrayList
        // and MoveNext returns false.
        while (enumerator.MoveNext()) {

            Console.WriteLine(enumerator.Current);
        }
    }
}
```

## Output：

```cs
Geeks
GFG
C#
Tutorials
```

## 例 2：

```cs
// C# code to get an enumerator
// for the entire ArrayList
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating an ArrayList
        ArrayList myList = new ArrayList();

        // adding elements in myList
        myList.Add(14);
        myList.Add(45);
        myList.Add(78);
        myList.Add(57);

        // To get an Enumerator
        // for the ArrayList
        IEnumerator enumerator = myList.GetEnumerator();

        // If MoveNext passes the end of the
        // collection, the enumerator is positioned
        // after the last element in the ArrayList
        // and MoveNext returns false.
        while (enumerator.MoveNext()) {

            Console.WriteLine(enumerator.Current);
        }
    }
}
```

## Output：

```cs

```

## 注：

*   C# 语言的 `foreach` 语句隐藏了枚举器的复杂性。因此，建议使用 `foreach` ，而不是直接操作枚举器。
*   枚举数可用于读取集合中的数据，但不能用于修改基础集合。
*   `Current` 返回相同的对象，直到调用 `MoveNext` 或 `Reset`。`MoveNext` 将 `Current` 设置为下一个元素。
*   只要集合保持不变，枚举数就保持有效。如果对集合进行了更改，例如添加、修改或删除元素，枚举数将无法恢复地失效，并且其行为未定义。
*   这个方法是一个 O(1) 运算。

## 参考：

*   [https://docs.microsoft.com/en-us/dotnet/api/system.collections.arraylist.getenumerator?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.arraylist.getenumerator?view=netframework-4.7.2)