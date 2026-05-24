# C# |将哈希表元素复制到数组实例中

> 原文:[https://www . geesforgeks . org/c-sharp-copy-the-hashtable-elements-to-array-instance/](https://www.geeksforgeeks.org/c-sharp-copying-the-hashtable-elements-to-an-array-instance/)

**哈希表。CopyTo(Array，Int32)方法**用于将哈希表的元素复制到指定索引处的一维数组实例中。
**语法:**

```cs
public virtual void CopyTo (Array array, int arrayIndex);
```

**参数:**

> **数组:**一维数组，是从哈希表中复制的字典条目对象的目标。数组必须具有从零开始的索引。
> **索引:**数组中从零开始复制的索引。

**例外:**

*   **ArgumentNullException :** 如果数组为空。
*   **argumentoutofrangerexception:**如果索引小于零。
*   **InvalidCastException :** 如果源哈希表的类型不能自动转换为目标数组的类型。
*   **ArgumentException :** 如果数组是多维 OR，则源哈希表中的元素数量大于从 arrayIndex 到目标数组末尾的可用空间。

下面的程序说明了**哈希表的使用。CopyTo(Array，Int32)** 方法:
**例 1:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# code to copy the Hashtable
// elements to a one-dimensional Array
// instance at the specified index.
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Hashtable named myhash
        Hashtable myhash = new Hashtable();

        // Adding key/value pairs in myhash
        myhash.Add("A", "Apple");
        myhash.Add("B", "Banana");
        myhash.Add("C", "Cat");
        myhash.Add("D", "Dog");
        myhash.Add("E", "Elephant");
        myhash.Add("F", "Fish");

        // Creating a one-dimensional Array named myArr
        DictionaryEntry[] myArr = new DictionaryEntry[myhash.Count];

        // copying the Hashtable entries
        // to a one-dimensional Array instance
        // at the specified index
        myhash.CopyTo(myArr, 0);

        for (int i = 0; i < myArr.Length; i++)
            Console.WriteLine(myArr[i].Key + " --> "
                              + myArr[i].Value);
    }
}
```

**输出:**

```cs
B --> Banana
C --> Cat
A --> Apple
F --> Fish
D --> Dog
E --> Elephant
```

**例 2:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# code to copy the Hashtable
// elements to a one-dimensional Array
// instance at the specified index.
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Hashtable named myhash
        Hashtable myhash = new Hashtable();

        // Adding key/value pairs in myhash
        myhash.Add("A", "Apple");
        myhash.Add("B", "Banana");
        myhash.Add("C", "Cat");
        myhash.Add("D", "Dog");
        myhash.Add("E", "Elephant");
        myhash.Add("F", "Fish");

        // Creating a one-dimensional Array named myArr
        DictionaryEntry[] myArr = new DictionaryEntry[myhash.Count];

        // copying the HybridDictionary entries
        // to a one-dimensional Array instance
        // at the specified index
        // This should raise "ArgumentOutOfRangeException"
        // as index is less than 0
        myhash.CopyTo(myArr, -2);

        for (int i = 0; i < myArr.Length; i++)
            Console.WriteLine(myArr[i].Key + " --> "
                              + myArr[i].Value);
    }
}
```

**运行时错误:**

> 未处理异常:
> 系统。ArgumentOutOfRangeException:要求非负数。
> 参数名称:arrayIndex

**注:**

*   元素以枚举数遍历哈希表的相同顺序复制到数组中。
*   要仅复制哈希表中的键，请使用**哈希表。钥匙。复制到**。
*   要仅复制哈希表中的值，请使用**哈希表。值。复制到**。
*   这个方法是一个 O(n)运算，其中 n 是 Count。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . hashtable . copy to？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.hashtable.copyto?view=netframework-4.7.2)