# C# |在字符串集合

中的指定索引处获取或设置

> 原文:[https://www . geeksforgeeks . org/c-sharp-get-or-set-at-specified-index-in-string collection/](https://www.geeksforgeeks.org/c-sharp-get-or-set-at-specified-index-in-stringcollection/)

StringCollection 类是。表示字符串集合的. NET Framework 类库。在 ***系统中定义了 StringCollection 类。收藏.专门**命名空间*。

**属性:**

*   StringCollection 接受 **null** 作为有效值，并允许重复元素。
*   字符串比较区分大小写。
*   可以使用整数索引访问此集合中的元素。
*   此集合中的索引从零开始。

下面的程序说明了如何在 StringCollection 中的指定索引处获取或设置元素:

**例 1:**

```cs
// C# code to get or set the element at the
// specified index in StringCollection
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
        String[] myArr = new String[] { "G", "e", "E", "k", "s" };

        // Copying the elements of a string
        // array to the end of the StringCollection.
        myCol.AddRange(myArr);

        // To get element at index 2
        Console.WriteLine(myCol[2]);
    }
}
```

**Output:**

```cs
E

```

**例 2:**

```cs
// C# code to get or set the element at the
// specified index in StringCollection
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
        String[] myArr = new String[] { "3", "5", "7", "11", "13" };

        // Copying the elements of a string
        // array to the end of the StringCollection.
        myCol.AddRange(myArr);

        // To get element at index 3
        Console.WriteLine(myCol[3]);

        // Set the value at index 3 to "8"
        myCol[3] = "8";

        // To get element at index 3
        Console.WriteLine(myCol[3]);
    }
}
```

**Output:**

```cs
11
8

```