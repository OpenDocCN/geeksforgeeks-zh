# C# 创建具有指定初始大小和区分大小写的混合字典

> 原文：[https://www.geeksforgeeks.org/c-sharp-creating-a-hybrid-dictionary-with-specified-initial-size-case-sensitivity/](https://www.geeksforgeeks.org/c-sharp-creating-a-hybrid-dictionary-with-specified-initial-size-case-sensitivity/)

`HybridDictionary(Int32, Boolean)` 构造函数用于创建具有指定初始容量和大小写敏感性的混合字典。

## 语法

```cs
public HybridDictionary (int initialSize, bool caseInsensitive);
```

## 参数

*   `initialSize`：混合字典最初可以包含的条目的大致数量。
*   `caseInsensitive`：一个布尔值，指示混合字典是否不区分大小写。

以下程序说明了 `HybridDictionary(Int32, Boolean)` 构造函数的使用：

### 示例 1

```cs
// C# code to create a HybridDictionary
// with the specified initial size
// and case sensitivity.
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {
        // Creating a HybridDictionary with the
        // specified initial size and case sensitivity.
        HybridDictionary myDict = new HybridDictionary(10, false);

        // Adding key/value pairs in myDict
        myDict.Add("I", "first");

        // This will not raise exception as the
        // Collection is not case-insensitive
        myDict.Add("i", "first");
        myDict.Add("II", "second");
        myDict.Add("III", "third");
        myDict.Add("IV", "fourth");
        myDict.Add("V", "fifth");

        // Displaying the key/value pairs in myDict
        foreach(DictionaryEntry de in myDict)
            Console.WriteLine(de.Key + " " + de.Value);
    }
}
```

**输出：**

```cs
III third
V fifth
II second
i first
I first
IV fourth
```

### 示例 2

```cs
// C# code to create a HybridDictionary
// with the specified initial size
// and case sensitivity.
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {
        // Creating a HybridDictionary with the
        // specified initial size and case sensitivity.
        HybridDictionary myDict = new HybridDictionary(10, true);

        // Adding key/value pairs in myDict
        myDict.Add("A", "Apple");

        // This will raise exception as the
        // Collection is case-insensitive
        myDict.Add("a", "Air");
        myDict.Add("B", "Banana");
        myDict.Add("C", "Cat");
        myDict.Add("D", "Dog");
        myDict.Add("E", "Elephant");
        myDict.Add("F", "Fish");

        // Displaying the key/value pairs in myDict
        foreach(DictionaryEntry de in myDict)
            Console.WriteLine(de.Key + " " + de.Value);
    }
}
```

**运行时错误：**

> 未处理异常：
> System.ArgumentException: 项已添加。字典中的关键字:“A” 正在添加关键字:“A” (在 System.Collections.Hashtable.Insert)

## 备注

*   如果集合的初始大小大于 `ListDictionary` 的最佳大小，则集合存储在 `Hashtable` 中，以避免将元素从 `ListDictionary` 复制到 `Hashtable` 的开销。
*   这个构造函数是一个 O(n) 运算，其中 n 是 `initialSize`。