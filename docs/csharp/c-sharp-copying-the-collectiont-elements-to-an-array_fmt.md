# C# | 将集合<T>元素复制到数组

> 原文：[https://www.geeksforgeeks.org/c-sharp-copying-the-collectiont-elements-to-an-array/](https://www.geeksforgeeks.org/c-sharp-copying-the-collectiont-elements-to-an-array/)

`Collection<T>.CopyTo(T[], Int32)` 方法用于将整个集合 `<T>` 复制到兼容的一维数组中，从目标数组的指定索引开始。

## 语法：

```cs
public void CopyTo (T[] array, int index);
```

## 参数：

> **`array`**：一维数组，是从集合中复制的元素的目的地。数组必须具有从零开始的索引。
>
> **`index`**：数组中开始复制的从零开始的索引。

## 异常：

*   **`ArgumentNullException`**：如果 `array` 为 `null`。
*   **`ArgumentOutOfRangeException`**：如果 `index` 小于零。
*   **`ArgumentException`**：如果源集合 `<T>` 中的元素数量大于从 `index` 到目标数组末尾的可用空间。

下面给出了一些例子，以便更好地理解实现：

## 例 1：

```cs
// C# code to copy the entire Collection
// to a compatible one-dimensional Array,
// starting at the specified index of
// the target array
using System;
using System.Collections.Generic;
using System.Collections.ObjectModel;

class GFG {

    // Driver code
    public static void Main()
    {
        // Creating a collection of strings
        Collection<string> myColl = new Collection<string>();

        myColl.Add("A");
        myColl.Add("B");
        myColl.Add("C");
        myColl.Add("D");
        myColl.Add("E");

        // Creating a string array
        string[] myArr = new string[myColl.Count];

        // Copying the entire Collection to a
        // compatible one-dimensional Array,
        // starting at the specified index
        // of the target array
        myColl.CopyTo(myArr, 0);

        // Displaying the elements in myArr
        foreach(string str in myArr)
        {
            Console.WriteLine(str);
        }
    }
}
```

## 输出：

```cs
A
B
C
D
E
```

## 例 2：

```cs
// C# code to copy the entire Collection
// to a compatible one-dimensional Array,
// starting at the specified index of
// the target array
using System;
using System.Collections.Generic;
using System.Collections.ObjectModel;

class GFG {

    // Driver code
    public static void Main()
    {
        // Creating a collection of ints
        Collection<int> myColl = new Collection<int>();

        myColl.Add(2);
        myColl.Add(3);
        myColl.Add(4);
        myColl.Add(5);

        // Creating an integer array
        int[] myArr = new int[myColl.Count];

        // Copying the entire Collection to a
        // compatible one-dimensional Array,
        // starting at the specified index
        // of the target array
        // This should raise "ArgumentOutOfRangeException"
        // as index is less than 0
        myColl.CopyTo(myArr, -5);

        // Displaying the elements in myArr
        foreach(int i in myArr)
        {
            Console.WriteLine(i);
        }
    }
}
```

## 运行时错误：

> 未处理异常:
> System.ArgumentOutOfRangeException: 值必须大于或等于 0。
> 参数名: destinationIndex

## 注：

*   该方法使用 [`Array.Copy`](https://docs.microsoft.com/en-us/dotnet/api/system.array.copy?view=netframework-4.7.2) 复制元素。
*   元素以枚举器遍历集合 `<T>` 的相同顺序复制到数组中。
*   这个方法是一个 O(n) 运算，其中 n 是 `Count`。

## 参考：

*   [https://docs.microsoft.com/en-us/dotnet/api/system.collections.objectmodel.collection-1.copyto?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.objectmodel.collection-1.copyto?view=netframework-4.7.2)