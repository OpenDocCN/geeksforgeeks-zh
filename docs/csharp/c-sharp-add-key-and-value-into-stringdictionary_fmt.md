# C# 将键和值添加到字符串中

> 原文：[`https://www.geeksforgeeks.org/c-sharp-add-key-and-value-into-stringdictionary/`](https://www.geeksforgeeks.org/c-sharp-add-key-and-value-into-stringdictionary/)

`StringDictionary.Add(String, String)` 方法用于将具有指定键和值的条目添加到 `StringDictionary` 中。

## 语法

```cs
public virtual void Add (string key, string value);
```

## 参数

*   `key`：是要添加的条目的键。
*   `value`：是要添加的条目的值。该值可以为 `null`。

## 异常

*   `ArgumentNullException`：如果 `key` 为 `null`。
*   `ArgumentException`：`StringDictionary` 中已经存在具有相同 `key` 的条目。
*   `NotSupportedException`：如果 `StringDictionary` 是只读的。

下面的程序说明了 `StringDictionary.Add(String, String)` 方法的使用：

### 例 1

```cs
// C# code to add key and value
// into the StringDictionary
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a StringDictionary named myDict
        StringDictionary myDict = new StringDictionary();

        // Adding key and value into the StringDictionary
        myDict.Add("A", "Apple");
        myDict.Add("B", "Banana");
        myDict.Add("C", "Cat");
        myDict.Add("D", "Dog");
        myDict.Add("E", "Elephant");

        // Displaying the keys and values in StringDictionary
        foreach(DictionaryEntry dic in myDict)
        {
            Console.WriteLine(dic.Key + "  " + dic.Value);
        }
    }
}
```

**输出：**

```cs
d  Dog
b  Banana
c  Cat
e  Elephant
a  Apple
```

### 例 2

```cs
// C# code to add key and value
// into the StringDictionary
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a StringDictionary named myDict
        StringDictionary myDict = new StringDictionary();

        // Adding key and value into the StringDictionary
        myDict.Add("A", "Apple");
        myDict.Add("B", "Banana");
        myDict.Add("C", "Cat");
        myDict.Add("D", "Dog");

        // It should raise "ArgumentException"
        // as an entry with the same key
        // already exists in the StringDictionary.
        myDict.Add("C", "Code");

        // Displaying the keys and values in StringDictionary
        foreach(DictionaryEntry dic in myDict)
        {
            Console.WriteLine(dic.Key + "  " + dic.Value);
        }
    }
}
```

**运行时错误：**

> 未处理异常：
> System.ArgumentException: 项目已添加。字典中的关键字:“c” 正在添加的关键字:“c”

## 注

*   该键以不区分大小写的方式处理，即在添加到 `StringDictionary` 之前将其转换为小写。
*   这个方法是一个 O(1) 运算。

## 参考

*   [`https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.stringdictionary.add?view=netframework-4.7.2`](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.stringdictionary.add?view=netframework-4.7.2)