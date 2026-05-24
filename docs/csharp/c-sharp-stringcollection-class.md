# C# | StringCollection 类

> 原文:[https://www . geesforgeks . org/c-sharp-string collection-class/](https://www.geeksforgeeks.org/c-sharp-stringcollection-class/)

StringCollection 类是。表示字符串集合的. NET Framework 类库。在 ***系统中定义了 StringCollection 类。收藏.专门**命名空间*。

**特征:**

*   StringCollection 类接受 **null** 作为有效值，并允许重复元素。
*   字符串比较区分大小写。
*   可以使用整数索引访问此集合中的元素。
*   此集合中的索引从零开始。

#### 构造器

| 构造器 | 描述 |
| 字符串集合() | 初始化 StringCollection 类的新实例。 |

**示例:**

```cs
// C# code to create a StringCollection
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {

        // creating a StringCollection named myCol
        StringCollection myCol = new StringCollection();

        // Adding elements in StringCollection
        myCol.Add("A");
        myCol.Add("B");
        myCol.Add("C");
        myCol.Add("D");
        myCol.Add("E");

        // Displaying objects in myCol
        foreach(Object obj in myCol)
        {
            Console.WriteLine(obj);
        }
    }
}
```

**输出:**

```cs
A
B
C
D
E

```

#### 性能

| 财产 | 描述 |
| **[计数](https://www.geeksforgeeks.org/c-get-the-number-of-strings-in-stringcollection/)** | 获取 StringCollection 中包含的字符串数。 |
| **[【isreadonly】](https://www.geeksforgeeks.org/c-check-if-the-stringcollection-is-read-only/)** | 获取一个值，该值指示 StringCollection 是否为只读。 |
| **[同步](https://www.geeksforgeeks.org/c-check-if-stringcollection-is-synchronized-thread-safe/)** | 获取一个值，该值指示对 StringCollection 的访问是否同步(线程安全)。 |
| **项目【Int32】** | 获取或设置指定索引处的元素。 |
| 同步根 | 获取一个对象，该对象可用于同步对 StringCollection 的访问。 |

**示例:**

```cs
// C# code to illustrate the StringCollection
// Class Properties
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
        String[] myArr = new String[] { "A", "B", "C", "D", "E" };

        // Copying the elements of a string
        // array to the end of the StringCollection.
        myCol.AddRange(myArr);

        // --------- Using IsReadOnly Property ---------

        // checking if StringCollection is
        // read-only
        Console.WriteLine(myCol.IsReadOnly);

        // --------- Using Count Property ---------

        // To get number of Strings contained
        // in the StringCollection
        Console.WriteLine("Number of strings in myCol are : " 
                                              + myCol.Count);
    }
}
```

**输出:**

```cs
False
Number of strings in myCol are : 5

```

#### 方法

| 方法 | 描述 |
| **[加(弦)](https://www.geeksforgeeks.org/c-add-a-string-to-the-end-of-the-stringcollection/)** | 将字符串添加到 StringCollection 的末尾。 |
| **[添加范围(字符串[])](https://www.geeksforgeeks.org/c-copy-the-elements-of-a-string-array-to-the-end-of-the-stringcollection/)** | 将字符串数组的元素复制到 StringCollection 的末尾。 |
| **[晴()](https://www.geeksforgeeks.org/c-remove-all-the-strings-from-the-stringcollection/)** | 从 StringCollection 中移除所有字符串。 |
| **[含(弦)](https://www.geeksforgeeks.org/c-check-if-the-specified-string-is-in-the-stringcollection/)** | 确定指定的字符串是否在 StringCollection 中。 |
| **[CopyTo(String[]，Int32)](https://www.geeksforgeeks.org/c-copy-stringcollection-at-the-specified-index-of-array/)** | 从目标数组的指定索引开始，将整个 StringCollection 值复制到一维字符串数组。 |
| **等于(对象)** | 确定指定的对象是否等于当前对象。 |
| **get numeric stepper()** | 返回一个 StringCollection 迭代的 StringEnumerator。 |
| **GetHashCode（）** | 用作默认哈希函数。 |
| **GetType()** | 获取当前实例的类型。 |
| 指数 | 搜索指定的字符串，并返回 StringCollection 中第一个匹配项的从零开始的索引。 |
| **[插入(Int32，String)](https://www.geeksforgeeks.org/c-insert-at-the-specified-index-in-stringcollection/)** | 将字符串插入指定索引处的 StringCollection。 |
| **MemberWiseCrone()** | 创建当前对象的浅拷贝。 |
| **[移除(弦)](https://www.geeksforgeeks.org/c-remove-the-first-occurrence-from-the-stringcollection/)** | 从 StringCollection 中移除特定字符串的第一个匹配项。 |
| **[移除 At(Int32)](https://www.geeksforgeeks.org/c-remove-from-the-specified-index-of-the-stringcollection/)** | 移除 StringCollection 指定索引处的字符串。 |
| **ToString()** | 返回表示当前对象的字符串。 |

**示例:**

```cs
// C# code to copy StringCollection to array,
// starting at the specified index of
// the target array
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {

        // creating a StringCollection named myCol
        StringCollection myCol = new StringCollection();

        // creating a string array named myArr1
        String[] myArr1 = new String[] { "A", "B", "C", "D", "E" };

        // Copying the elements of a string
        // array to the end of the StringCollection.
        myCol.AddRange(myArr1);

        // creating a String array named myArr2
        String[] myArr2 = new String[myCol.Count];

        // Copying StringCollection to array myArr2
        // starting from index 0
        myCol.CopyTo(myArr2, 0);

        // Displaying elements in array myArr2
        for (int i = 0; i < myArr2.Length; i++) {
            Console.WriteLine(myArr2[i]);
        }
    }
}
```

**输出:**

```cs
A
B
C
D
E

```

**示例:**

```cs
// C# code to insert a string into
// the StringCollection at the
// specified index
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
        String[] myArr = new String[] { "Hello", "Geeks",
                                        "for", "GeeksforGeeks" };

        // Copying the elements of a string
        // array to the end of the StringCollection.
        myCol.AddRange(myArr);

        Console.WriteLine("Initially elements in StringCollection are: ");

        // Displaying elements in StringCollection
        // named myCol
        foreach(Object obj in myCol)
            Console.WriteLine(obj);

        // Removing all the elements from StringCollection
        myCol.Clear();

        Console.WriteLine("After Removing: ");

        // Displaying elements in StringCollection
        // named myCol
        foreach(Object obj in myCol)
            Console.WriteLine(obj);
    }
}
```

**输出:**

```cs
Initially elements in StringCollection are: 
Hello
Geeks
for
GeeksforGeeks
After Removing:

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . string collection？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.stringcollection?view=netframework-4.7.2)