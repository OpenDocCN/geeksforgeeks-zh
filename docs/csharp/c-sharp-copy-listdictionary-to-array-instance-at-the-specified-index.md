# C# |将列表字典复制到指定索引处的数组实例

> 原文:[https://www . geesforgeks . org/c-sharp-copy-list dictionary-to-array-instance-at-the-specific-index/](https://www.geeksforgeeks.org/c-sharp-copy-listdictionary-to-array-instance-at-the-specified-index/)

**列表词典。CopyTo(Array，Int32)** 方法用于将列表字典条目复制到指定索引处的一维数组实例。

**语法:**

```cs
public void CopyTo (Array array, int index);

```

**参数:**

> **数组:**是一维数组，是从列表字典中复制的字典条目对象的目的地。数组必须有*从零开始的*索引。
> 
> **索引:**数组中开始复制的从零开始的索引。

**异常:**

*   **ArgumentNullException :** 如果数组为空。
*   **argumentoutofrangerexception:**如果索引小于零。
*   **InvalidCastException :** 如果源列表字典的类型不能自动转换为目标数组的类型。
*   **ArgumentException :** 如果数组是多维的 ***或*** 源列表字典中的元素数量大于从索引到目标数组末尾的可用空间。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to copy ListDictionary to
// Array instance at the specified index
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a ListDictionary named myDict
        ListDictionary myDict = new ListDictionary();

        myDict.Add("Australia", "Canberra");
        myDict.Add("Belgium", "Brussels");
        myDict.Add("Netherlands", "Amsterdam");
        myDict.Add("China", "Beijing");
        myDict.Add("Russia", "Moscow");
        myDict.Add("India", "New Delhi");

        DictionaryEntry[] myArr = new DictionaryEntry[myDict.Count];

        // Copying ListDictionary to Array
        // instance at the specified index
        myDict.CopyTo(myArr, 0);

        // Displaying elements in myArr
        for (int i = 0; i < myArr.Length; i++) {
            Console.WriteLine(myArr[i].Key + "-->" + myArr[i].Value);
        }
    }
}
```

**输出:**

```cs
Australia-->Canberra
Belgium-->Brussels
Netherlands-->Amsterdam
China-->Beijing
Russia-->Moscow
India-->New Delhi

```

**例 2:**

```cs
// C# code to copy ListDictionary to
// Array instance at the specified index
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a ListDictionary named myDict
        ListDictionary myDict = new ListDictionary();

        myDict.Add("Australia", "Canberra");
        myDict.Add("Belgium", "Brussels");
        myDict.Add("Netherlands", "Amsterdam");
        myDict.Add("China", "Beijing");
        myDict.Add("Russia", "Moscow");
        myDict.Add("India", "New Delhi");

        DictionaryEntry[] myArr = new DictionaryEntry[myDict.Count];

        // Copying ListDictionary to Array
        // instance at the specified index
        // This should raise "ArgumentOutOfRangeException"
        // as index is less than 0
        myDict.CopyTo(myArr, -2);

        // Displaying elements in myArr
        for (int i = 0; i < myArr.Length; i++) {
            Console.WriteLine(myArr[i].Key + "-->" + myArr[i].Value);
        }
    }
}
```

**运行时错误:**

> 未处理异常:
> 系统。ArgumentOutOfRangeException:索引小于零。
> 参数名称:索引

**注:**

*   元素按照枚举器遍历列表字典的相同顺序复制到数组中。
*   要仅复制列表词典中的**键，请使用 ***列表词典。按键.复制到*** 。**
*   **要仅复制列表字典中的 ***值*** ，请使用 ***列表字典。价值观.文案*** 。**
*   **这个方法是一个 O(n)运算，其中 n 是 Count。**

****参考:****

*   **[https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . list dictionary . copy to？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.listdictionary.copyto?view=netframework-4.7.2)**