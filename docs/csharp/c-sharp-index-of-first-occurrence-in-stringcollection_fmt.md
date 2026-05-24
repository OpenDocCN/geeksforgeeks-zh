# C# 字符串集合中第一次出现的索引

> 原文：[Index of first occurrence in StringCollection](https://www.geeksforgeeks.org/c-sharp-index-of-first-occurrence-in-stringcollection/)

`StringCollection` 类是 .NET Framework 类库中表示字符串集合的类。`StringCollection` 类在 `System.Collections.Specialized` 命名空间中定义。

`StringCollection.IndexOf()` 方法用于搜索指定的字符串，并返回其在 `StringCollection` 中第一个匹配项的从零开始的索引。

## 语法

```cs
public int IndexOf (string value);
```

这里，`value` 是要定位的字符串。该值可以为 `null`。

## 返回值

该方法返回 `StringCollection` 中第一个出现的 `value` 的从零开始的索引，否则返回 `-1`。

## 注意

该方法执行[线性搜索](https://www.geeksforgeeks.org/linear-search/)。因此，这个方法的时间复杂度是 `O(n)`，其中 `n` 是 `Count`。

下面的程序说明了 `StringCollection.IndexOf()` 方法的使用：

### 例 1

```cs
// C# code to search string and returns
// the zero-based index of the first
// occurrence in StringCollection
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

// Driver code
    public static void Main()
    {

// creating a StringCollection named myCol
        StringCollection myCol = new StringCollection();

// creating a string array named myArr
        String[] myArr = new String[] { "A", "B", "C", "C", "D" };

// Copying the elements of a string
        // array to the end of the StringCollection.
        myCol.AddRange(myArr);

// To search string "C" and return
        // the zero-based index of the first
        // occurrence in StringCollection
        // Here, "C" exists at index 2 and 3.
        // But, the method should return 2
        Console.WriteLine(myCol.IndexOf("C"));
    }
}
```

**输出：**

```cs
2
```

### 例 2

```cs
// C# code to search string and returns
// the zero-based index of the first
// occurrence in StringCollection
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

// Driver code
    public static void Main()
    {

// creating a StringCollection named myCol
        StringCollection myCol = new StringCollection();

// creating a string array named myArr
        String[] myArr = new String[] { "2", "3", "4", "5", "6" };

// Copying the elements of a string
        // array to the end of the StringCollection.
        myCol.AddRange(myArr);

// To search string "9" and return
        // the zero-based index of the first
        // occurrence in StringCollection
        // Here, "9" does not exist in myCol
        // Hence, method returns -1
        Console.WriteLine(myCol.IndexOf("9"));
    }
}
```

**输出：**

```cs
-1
```

## 参考

*   [StringCollection.IndexOf 方法](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.stringcollection.indexof?view=netframework-4.7.2)