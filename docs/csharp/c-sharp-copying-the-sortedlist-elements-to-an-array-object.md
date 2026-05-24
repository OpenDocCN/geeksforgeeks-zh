# C# |将排序列表元素复制到数组对象中

> 原文:[https://www . geeksforgeeks . org/c-sharp-copy-the-sorted list-elements-to-array-object/](https://www.geeksforgeeks.org/c-sharp-copying-the-sortedlist-elements-to-an-array-object/)

**排序列表。CopyTo(Array，Int32)方法**用于将 SortedList 元素复制到一维[数组](https://www.geeksforgeeks.org/c-sharp-arrays/)对象中，从数组中指定的索引处开始。

**语法:**

```cs
public virtual void CopyTo (Array array, int arrayIndex);
```

**参数:**

> **数组:**是一维数组对象，是从 SortedList 复制的 DictionaryEntry 对象的目标。数组必须具有从零开始的索引。
> 
> **arrayindex:** 是*数组*中开始复制的从零开始的索引。

**异常:**

*   **参数空异常:**如果*数组*为空。
*   **argumentoutofrangerexception:**如果*数组索引*小于零。
*   **参数异常:**如果*数组*是多维的或者源 SortedList 对象中的元素数量大于从*数组索引*到目标数组末尾的可用空间。
*   **InvalidCastException:** 如果源 SortedList 的类型不能自动转换为目标*数组*的类型。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# code to copy the SortedList elements
// to a 1-D Array object, starting at the
// specified index in the array
using System;
using System.Collections;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {

        // Creating a SortedList of integers
        SortedList mylist = new SortedList();

        // Adding elements to SortedList
        mylist.Add("1", "C#");
        mylist.Add("2", "Java");
        mylist.Add("3", "DSA");
        mylist.Add("4", "Python");
        mylist.Add("5", "C");

        // creating a 1-D array
        DictionaryEntry[] myArr = new DictionaryEntry[mylist.Count];

        // Copying SortedList to Array
        // instance at the specified index
        mylist.CopyTo(myArr, 0);

        // Displaying elements in myArr
        for (int i = 0; i < myArr.Length; i++) {
            Console.WriteLine(myArr[i].Key + "-->" + myArr[i].Value);
        }
    }
}
```

**输出:**

```cs
1-->C#
2-->Java
3-->DSA
4-->Python
5-->C

```

**例 2:**

```cs
// C# code to copy the SortedList elements
// to a 1-D Array object, starting at the
// specified index in the array
using System;
using System.Collections;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {

        // Creating a SortedList of integers
        SortedList mylist = new SortedList();

        // Adding elements to SortedList
        mylist.Add("1st", "Ram");
        mylist.Add("2nd", "Shyam");
        mylist.Add("3rd", "Rohit");
        mylist.Add("4th", "Manish");
        mylist.Add("5th", "Vikas");

        // creating a 1-D array
        DictionaryEntry[] myArr = new DictionaryEntry[mylist.Count];

        // Copying SortedList to Array
        // instance at the specified index
        // This will raise "ArgumentOutOfRangeException"
        // as index is less than 0
        mylist.CopyTo(myArr, -2);

        // Displaying elements in myArr
        for (int i = 0; i < myArr.Length; i++) {
            Console.WriteLine(myArr[i].Key + "-->" + myArr[i].Value);
        }
    }
}
```

**运行时错误:**

> 未处理异常:
> 系统。ArgumentOutOfRangeException:要求非负数。
> 参数名称:arrayIndex

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . sorted list . copy to？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.sortedlist.copyto?view=netframework-4.7.2)