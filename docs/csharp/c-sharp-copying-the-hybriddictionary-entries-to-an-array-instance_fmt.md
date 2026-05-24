# C# | 将混合字典条目复制到数组实例中

> 原文：[https://www.geeksforgeeks.org/c-sharp-copying-the-hybriddictionary-entries-to-an-array-instance/](https://www.geeksforgeeks.org/c-sharp-copying-the-hybriddictionary-entries-to-an-array-instance/)

`HybridDictionary.CopyTo(Array, Int32)` 方法用于将混合字典条目复制到指定索引处的一维数组实例。

## 语法：

```cs
public void CopyTo (Array array, int index);
```

## 参数：

- `array`：一维数组，是从混合字典中复制的字典条目对象的目的地。数组必须有零基索引。
- `index`：数组中开始复制的从零开始的索引。

## 异常：

- `ArgumentNullException`：如果 `array` 为空。
- `ArgumentOutOfRangeException`：如果 `index` 小于零。
- `InvalidCastException`：如果源混合字典的类型不能自动转换为目标数组的类型。
- `ArgumentException`：如果数组是多维的，或者源混合字典中的元素数量大于从 `index` 到目标数组末尾的可用空间。

以下程序说明了 `HybridDictionary.CopyTo(Array, Int32)` 方法的使用：

### 示例 1：

```cs
// C# code to copy the HybridDictionary
// entries to a one-dimensional Array
// instance at the specified index.
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a HybridDictionary named myDict
        HybridDictionary myDict = new HybridDictionary();

        // Adding key/value pairs in myDict
        myDict.Add("A", "Apple");
        myDict.Add("B", "Banana");
        myDict.Add("C", "Cat");
        myDict.Add("D", "Dog");
        myDict.Add("E", "Elephant");
        myDict.Add("F", "Fish");

        // Creating a one-dimensional Array named myArr
        DictionaryEntry[] myArr = new DictionaryEntry[myDict.Count];

        // copying the HybridDictionary entries
        // to a one-dimensional Array instance
        // at the specified index
        myDict.CopyTo(myArr, 0);

        for (int i = 0; i < myArr.Length; i++)
            Console.WriteLine(myArr[i].Key + " --> " + myArr[i].Value);
    }
}
```

**输出：**

```cs
A --> Apple
B --> Banana
C --> Cat
D --> Dog
E --> Elephant
F --> Fish
```

### 示例 2：

```cs
// C# code to copy the HybridDictionary
// entries to a one-dimensional Array
// instance at the specified index.
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a HybridDictionary named myDict
        HybridDictionary myDict = new HybridDictionary();

        // Adding key/value pairs in myDict
        myDict.Add("I", "first");
        myDict.Add("II", "second");
        myDict.Add("III", "third");
        myDict.Add("IV", "fourth");
        myDict.Add("V", "fifth");

        // Creating a one-dimensional Array named myArr
        DictionaryEntry[] myArr = new DictionaryEntry[myDict.Count];

        // copying the HybridDictionary entries
        // to a one-dimensional Array instance
        // at the specified index
        // This should raise "ArgumentOutOfRangeException"
        // as index is less than 0
        myDict.CopyTo(myArr, -2);

        for (int i = 0; i < myArr.Length; i++)
            Console.WriteLine(myArr[i].Key + " --> " + myArr[i].Value);
    }
}
```

**运行时错误：**

> 未处理异常:
> System.ArgumentOutOfRangeException: 索引小于零。
> 参数名称: index

## 注：

- 元素以枚举器遍历混合字典的相同顺序复制到数组中。
- 要仅复制混合字典中的键，请使用 `HybridDictionary.Keys.CopyTo`。
- 要仅复制混合字典中的值，请使用 `HybridDictionary.Values.CopyTo`。
- 这个方法是一个 O(n) 运算，其中 n 是 `Count`。

## 参考：

- [https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.hybriddictionary.copyto?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.hybriddictionary.copyto?view=netframework-4.7.2)