# C# |数组列表类

> 原文:[https://www.geeksforgeeks.org/c-sharp-arraylist-class/](https://www.geeksforgeeks.org/c-sharp-arraylist-class/)

**数组列表**表示可以单独索引的对象的有序集合。它基本上是数组的替代。它还允许动态内存分配、添加、搜索和排序列表中的项目。

**数组列表类的属性:**

*   可以随时在数组列表集合中添加或删除元素。
*   数组列表不能保证排序。
*   数组列表的容量是数组列表可以容纳的元素数量。
*   可以使用整数索引访问此集合中的元素。此集合中的索引从零开始。
*   它还允许重复元素。
*   不支持在数组列表集合中使用多维数组作为元素。

#### 构造器

| 构造器 | 描述 |
| **[数组列表()](https://www.geeksforgeeks.org/how-to-create-the-arraylist-in-c-sharp/)T3** | 初始化数组列表类的新实例，该实例为空并具有默认的初始容量。 |
| **数组列表(ICollection)** | 初始化数组列表类的新实例，该实例包含从指定集合复制的元素，并且具有与复制的元素数相同的初始容量。 |
| **[数组列表(Int32)](https://www.geeksforgeeks.org/c-sharp-creating-an-arraylist-having-specified-initial-capacity/)** | 初始化数组列表类的新实例，该实例为空并具有指定的初始容量。 |

**示例:**

```cs
// C# code to create an ArrayList
using System;
using System.Collections;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating an ArrayList
        ArrayList myList = new ArrayList();

        // Adding elements to ArrayList
        myList.Add("Hello");
        myList.Add("World");

        Console.WriteLine("Count : " + myList.Count);
        Console.WriteLine("Capacity : " + myList.Capacity);
    }
}
```

**输出:**

```cs
Count : 2
Capacity : 4

```

#### 性能

| 财产 | 描述 |
| **[运力](https://www.geeksforgeeks.org/c-get-or-set-the-number-of-elements-that-the-arraylist-can-contain/)** | 获取或设置数组列表可以包含的元素数量。 |
| **[计数](https://www.geeksforgeeks.org/c-get-the-number-of-elements-actually-contained-in-the-arraylist/)** | 获取数组列表中实际包含的元素数量。 |
| **[【is fixed DSI】](https://www.geeksforgeeks.org/c-check-if-the-arraylist-has-a-fixed-size/)** | 获取一个值，该值指示数组列表是否具有固定大小。 |
| **[【isreadonly】](https://www.geeksforgeeks.org/c-check-if-the-arraylist-is-read-only/)** | 获取一个值，该值指示数组列表是否为只读。 |
| **[同步](https://www.geeksforgeeks.org/c-sharp-check-if-arraylist-is-synchronized-thread-safe/)** | 获取一个值，该值指示对数组列表的访问是否同步(线程安全)。 |
| **[项【国际 32】](https://www.geeksforgeeks.org/c-sharp-get-or-set-the-element-at-the-specified-index-in-arraylist/)** | 获取或设置指定索引处的元素。 |
| **[【sync root】](https://www.geeksforgeeks.org/c-sharp-how-to-get-synchronize-access-to-the-arraylist/)** | 获取一个对象，该对象可用于同步对数组列表的访问。 |

**示例:**

```cs
// C# program to illustrate the 
// ArrayList Class Properties
using System; 
using System.Collections; 
using System.Collections.Generic; 

class GFG { 

    // Driver code 
    public static void Main() 
    { 

        // Creating an ArrayList 
        ArrayList myList = new ArrayList(); 

        // Adding elements to ArrayList 
        myList.Add("A"); 
        myList.Add("B"); 
        myList.Add("C"); 
        myList.Add("D"); 
        myList.Add("E"); 
        myList.Add("F"); 

        // -------- IsFixedSize Property --------

        // To check if the ArrayList has fixed size or not 
        Console.WriteLine(myList.IsFixedSize); 

        // -------- IsReadOnly Property --------

        // To check if the ArrayList is read-only or not 
        Console.WriteLine(myList.IsReadOnly); 
    } 
} 
```

**输出:**

```cs
False
False

```

#### 方法

| 方法 | 描述 |
| **适配器(IList)** | 为特定 IList 创建数组列表包装。 |
| **[添加(对象)](https://www.geeksforgeeks.org/c-add-an-object-to-the-end-of-the-arraylist/)** | 将对象添加到数组列表的末尾。 |
| **[【add range(icollion)](https://www.geeksforgeeks.org/c-sharp-adding-the-elements-to-the-end-of-the-arraylist/)** | 将 ICollection 的元素添加到数组列表的末尾。 |
| **BinarySearch(Int32，Int32，Object，IComparer)** | 使用指定的比较器在排序的数组列表中搜索某个元素的元素范围，并返回该元素的从零开始的索引。 |
| **二元搜索(对象)** | 使用默认比较器在整个排序数组列表中搜索元素，并返回元素的从零开始的索引。 |
| **BinarySearch(Object，IComparer)** | 使用指定的比较器在整个排序数组列表中搜索元素，并返回该元素的从零开始的索引。 |
| **[晴()](https://www.geeksforgeeks.org/c-remove-all-elements-from-the-arraylist/)** | 从数组列表中移除所有元素。 |
| **T1】克隆()T3】** | 创建数组列表的浅拷贝。 |
| **[包含(对象)](https://www.geeksforgeeks.org/c-check-whether-an-element-is-contained-in-the-arraylist/)** | 确定元素是否在数组列表中。 |
| **[文案(阵)](https://www.geeksforgeeks.org/c-sharp-how-to-copy-the-entire-arraylist-to-a-one-dimensional-array/)** | 从目标数组的开头开始，将整个数组列表复制到兼容的一维数组中。 |
| **[CopyTo(Array，Int32)](https://www.geeksforgeeks.org/c-sharp-copying-the-entire-arraylist-to-1-d-array-starting-at-the-specified-index/)** | 从目标数组的指定索引开始，将整个数组列表复制到兼容的一维数组。 |
| **CopyTo(Int32，Array，Int32，Int32)** | 从目标数组的指定索引开始，将数组列表中的一系列元素复制到兼容的一维数组中。 |
| **[等于(对象)](https://www.geeksforgeeks.org/c-sharp-check-if-two-arraylist-objects-are-equal/)** | 确定指定的对象是否等于当前对象。 |
| **固定大小(数组列表)** | 返回一个固定大小的数组列表包装。 |
| **固定大小(IList)** | 返回一个固定大小的 IList 包装。 |
| **[【get 分子()](https://www.geeksforgeeks.org/c-sharp-getting-an-enumerator-for-the-entire-arraylist/)** | 返回整个数组列表的枚举数。 |
| **[GetEnumerator(Int32，Int32)](https://www.geeksforgeeks.org/c-sharp-getting-an-enumerator-for-a-range-of-elements-in-the-arraylist/)** | 返回数组列表中某个元素范围的枚举数。 |
| **GetHashCode（）** | 用作默认哈希函数。 |
| **[GetRange(Int32，Int32)](https://www.geeksforgeeks.org/c-sharp-getting-a-subset-of-the-elements-from-the-source-arraylist/)** | 返回一个数组列表，该列表代表源数组列表中元素的子集。 |
| **GetType()** | 获取当前实例的类型。 |
| **索引（对象）** | 搜索指定的对象，并返回整个数组列表中第一个匹配项的从零开始的索引。 |
| **索引（对象， Int32）** | 搜索指定的对象，并返回数组列表中从指定索引延伸到最后一个元素的元素范围内第一个匹配项的从零开始的索引。 |
| **索引 Of(对象，Int32，Int32)** | 搜索指定的对象，并返回数组列表中元素范围内第一个匹配项的从零开始的索引，该索引从指定的索引开始并包含指定数量的元素。 |
| **[插入(Int32，Object)](https://www.geeksforgeeks.org/c-insert-an-element-into-the-arraylist-at-the-specified-index/)** | 将元素插入数组列表中的指定索引处。 |
| **插入范围(Int32，ICollection)** | 将集合的元素插入到指定索引处的数组列表中。 |
| **最后索引（对象）** | 搜索指定的对象，并返回整个数组列表中最后一个匹配项的从零开始的索引。 |
| **最后索引（对象， Int32）** | 搜索指定的对象，并返回数组列表中从第一个元素延伸到指定索引的元素范围内最后一个匹配项的从零开始的索引。 |
| **最后一个索引(对象，Int32，Int32)** | 搜索指定的对象，并返回数组列表中元素范围内最后一个匹配项的从零开始的索引，该列表包含指定数量的元素并以指定的索引结束。 |
| **MemberWiseCrone()** | 创建当前对象的浅拷贝。 |
| **[【只读(数组列表)](https://www.geeksforgeeks.org/c-creating-a-read-only-wrapper-for-the-arraylist/)** | 返回只读数组列表包装。 |
| **只读(IList)** | 返回只读 IList 包装。 |
| **[移除(对象)](https://www.geeksforgeeks.org/c-remove-the-first-occurrence-of-a-specific-object-from-the-arraylist/)** | 从数组列表中删除特定对象的第一个匹配项。 |
| **[移除 At(Int32)](https://www.geeksforgeeks.org/c-remove-the-element-at-the-specified-index-of-the-arraylist/)** | 移除数组列表中指定索引处的元素。 |
| **[移除范围(Int32，Int32)](https://www.geeksforgeeks.org/c-remove-a-range-of-elements-from-the-arraylist/)** | 从数组列表中移除一系列元素。 |
| **[重复(对象，Int32)](https://www.geeksforgeeks.org/c-sharp-arraylist-whose-elements-are-copies-of-the-specified-value/)** | 返回一个数组列表，其元素是指定值的副本。 |
| **[【反转()](https://www.geeksforgeeks.org/c-reverse-the-order-of-the-elements-in-the-entire-arraylist-or-in-the-specified-range/)** | 颠倒整个数组列表中元素的顺序。 |
| **[倒车(Int32，Int32)](https://www.geeksforgeeks.org/c-reverse-the-order-of-the-elements-in-the-entire-arraylist-or-in-the-specified-range/)** | 反转指定范围内元素的顺序。 |
| **[【setrange(int 32，icollion)](https://www.geeksforgeeks.org/c-sharp-copy-the-elements-of-collection-over-a-range-of-elements-in-arraylist/)** | 将集合的元素复制到数组列表中的一系列元素上。 |
| **[【排序()](https://www.geeksforgeeks.org/c-sharp-sort-the-elements-in-the-arraylist/)** | 对整个数组列表中的元素进行排序。 |
| **[【排序(IComparer)](https://www.geeksforgeeks.org/c-sharp-sort-the-elements-in-the-arraylist/)** | 使用指定的比较器对整个数组列表中的元素进行排序。 |
| **[排序(Int32，Int32，IComparer)](https://www.geeksforgeeks.org/c-sharp-sort-the-elements-in-the-arraylist/)** | 使用指定的比较器对数组列表中某个元素范围内的元素进行排序。 |
| **[【同步(数组列表)](https://www.geeksforgeeks.org/c-creating-a-synchronized-thread-safe-wrapper-for-the-arraylist/)** | 返回一个同步的数组列表包装(线程安全)。 |
| **同步(IList)** | 返回一个同步的 IList 包装(线程安全)。 |
| **[【toaarray()](https://www.geeksforgeeks.org/c-sharp-copying-the-elements-of-arraylist-to-a-new-array/)** | 将数组列表的元素复制到新的对象数组中。 |
| **[ToArray(类型)](https://www.geeksforgeeks.org/c-sharp-copying-the-elements-of-arraylist-to-a-new-array/)** | 将数组列表的元素复制到指定元素类型的新数组中。 |
| **ToString()** | 返回表示当前对象的字符串。 |
| **[【trimtosize()](https://www.geeksforgeeks.org/c-sharp-sets-the-capacity-to-the-actual-number-of-elements-in-the-arraylist/)** | 将容量设置为数组列表中元素的实际数量。 |

**例 1:**

```cs
// C# code to check if an element is
// contained in ArrayList or not
using System;
using System.Collections;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating an ArrayList
        ArrayList myList = new ArrayList();

        // Adding elements to ArrayList
        myList.Add("A");
        myList.Add("B");
        myList.Add("C");
        myList.Add("D");
        myList.Add("E");
        myList.Add("F");
        myList.Add("G");
        myList.Add("H");

        // To check if the ArrayList Contains element "E"
        // If yes, then display it's index, else
        // display the message
        if (myList.Contains("E"))
            Console.WriteLine("Yes, exists at index " + myList.IndexOf("E"));
        else
            Console.WriteLine("No, doesn't exists");
    }
}
```

**输出:**

```cs
Yes, exists at index 4

```

**例 2:**

```cs
// C# code to remove a range of
// elements from the ArrayList
using System;
using System.Collections;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating an ArrayList
        ArrayList myList = new ArrayList(10);

        // Adding elements to ArrayList
        myList.Add(2);
        myList.Add(4);
        myList.Add(6);
        myList.Add(8);
        myList.Add(10);
        myList.Add(12);
        myList.Add(14);
        myList.Add(16);
        myList.Add(18);
        myList.Add(20);

        // Displaying the elements in ArrayList
        Console.WriteLine("The initial ArrayList: ");

        foreach(int i in myList)
        {
            Console.WriteLine(i);
        }

        // removing 4 elements starting from index 0
        myList.RemoveRange(0, 4);

        // Displaying the modified ArrayList
        Console.WriteLine("The ArrayList after Removing elements: ");

        // Displaying the elements in ArrayList
        foreach(int i in myList)
        {
            Console.WriteLine(i);
        }
    }
}
```

**输出:**

```cs
The initial ArrayList: 
2
4
6
8
10
12
14
16
18
20
The ArrayList after Removing elements: 
10
12
14
16
18
20

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . ArrayList？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.arraylist?view=netframework-4.7.2)