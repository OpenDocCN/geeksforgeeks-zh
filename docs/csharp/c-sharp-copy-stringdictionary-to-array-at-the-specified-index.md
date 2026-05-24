# C# |将字符串复制到指定索引处的数组中

> 原文:[https://www . geeksforgeeks . org/c-sharp-copy-stringdictionary-to-array-at-the-specific-index/](https://www.geeksforgeeks.org/c-sharp-copy-stringdictionary-to-array-at-the-specified-index/)

**StringDictionary。CopyTo(Array，Int32)** 方法用于**将字符串字典值复制到指定索引处的一维数组实例**。

**语法:**

```cs
public virtual void CopyTo (Array array, int index);

```

**参数:**

*   **数组:**是一维数组，是从 StringDictionary 复制的值的目的地。
*   **索引:**是数组中开始复制的索引。

**异常:**

*   **ArgumentNullException :** 如果密钥为空。
*   **argumentoutofrangerexception:**如果索引小于数组的下界。
*   **ArgumentException :** 如果数组是多维的**或**StringDictionary 中的元素数量大于从索引到数组末尾的可用空间。

下面的程序说明了**字符串的使用。复制到(数组，Int32)** 方法:

**例 1:**

```cs
// C# code to copy StringDictionary
// to Array at the specified index
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

        // Creating an Array named myArr
        DictionaryEntry[] myArr = { new DictionaryEntry(),
                                    new DictionaryEntry(),
                                    new DictionaryEntry(),
                                    new DictionaryEntry(),
                                    new DictionaryEntry() };

        // Copying StringDictionary to
        // Array at the specified index
        myDict.CopyTo(myArr, 0);

        // Displaying key and value pairs in Array myArr
        for (int i = 0; i < myArr.Length; i++) {
            Console.WriteLine(myArr[i].Key + " " + myArr[i].Value);
        }
    }
}
```

**输出:**

```cs
d Dog
b Banana
c Cat
e Elephant
a Apple

```

**例 2:**

```cs
// C# code to copy StringDictionary
// to Array at the specified index
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

        // Creating an Array named myArr
        DictionaryEntry[] myArr = { new DictionaryEntry(),
                                    new DictionaryEntry(),
                                    new DictionaryEntry() };

        // Copying StringDictionary to
        // Array at the specified index
        // This should raise "ArgumentException" as
        // the number of elements in the StringDictionary
        // is greater than the available space from
        // index to the end of array.
        myDict.CopyTo(myArr, 0);

        // Displaying key and value pairs in Array myArr
        for (int i = 0; i < myArr.Length; i++) {
            Console.WriteLine(myArr[i].Key + " " + myArr[i].Value);
        }
    }
}
```

**运行时错误:**

> 未处理异常:
> 系统。参数异常:目标数组不够长，无法复制集合中的所有项。检查数组索引和长度。

**注:**

*   复制到数组的元素按照枚举器遍历 StringDictionary 的相同顺序进行排序。
*   这个方法是一个 O(n)运算，其中 n 是 Count。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . string dictionary . copy to？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.stringdictionary.copyto?view=netframework-4.7.2)