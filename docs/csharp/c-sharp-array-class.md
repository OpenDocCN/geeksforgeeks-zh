# C# |数组类

> 原文:[https://www.geeksforgeeks.org/c-sharp-array-class/](https://www.geeksforgeeks.org/c-sharp-array-class/)

Array 类给出了创建、操作、搜索和排序数组的方法。数组类不是*系统的一部分。集合*命名空间，但它仍然被认为是一个集合，因为它基于 *IList 接口*。数组类是支持数组的语言实现的基类。

**数组类的特征:**

*   在数组中，元素是数组的值，数组的长度是数组中存在的项目总数。
*   数组的下限是其第一个元素的索引，下限的默认值是 0。
*   阵列的默认大小为 *2GB* 。
*   具有相同数组类型的数组对象共享相同的类型对象。

**示例:**

## C#

```cs
// C# program to creating an array
// of the string as coffee name, store
// coffee name in the store,
// and prints each value.
using System;
namespace geeksforgeeks {

class GFG {

    // Main Method
    public static void Main()
    {

        // declares an 1D Array of string
        string[] store;

        // allocating memory for coffee names.
        store = new string[] {"Americano, ", "Cafe au lait, ",
                              "Espresso, ", "Cappuccino, ",
                              "Long Black, ", "Macchiato" };

        // Displaying Elements of the array
        Console.WriteLine("Different types of coffee: ");
        Console.WriteLine();
        foreach(string coffeename in store)
            Console.WriteLine(coffeename + " ");
    }
}
}
```

**Output:** 

```cs
Different types of coffee: 

Americano,  
Cafe au lait,  
Espresso,  
Cappuccino,  
Long Black,  
Macchiato
```

#### 性能

<figure class="table">

| 财产 | 描述 |
| --- | --- |
| [**【is fixed DSI】**](https://www.geeksforgeeks.org/c-check-if-an-array-has-fixed-size-or-not/) | 获取一个值，该值指示数组是否具有固定大小。 |
| [**【isreadonly】**](https://www.geeksforgeeks.org/c-check-if-an-array-is-read-only-or-not/) | 获取一个值，该值指示数组是否是只读的。 |
| [**同步**](https://www.geeksforgeeks.org/c-check-if-an-array-is-synchronized-thread-safe-or-not/) | 获取一个值，该值指示对数组的访问是否同步(线程安全)。 |
| [**长度**](https://www.geeksforgeeks.org/how-to-find-the-length-of-an-array-in-c/) | 获取数组所有维度中的元素总数。 |
| **长**长 | 获取一个 64 位整数，该整数表示数组所有维度中的元素总数。 |
| [**排名**](https://www.geeksforgeeks.org/how-to-find-the-rank-of-an-array-in-c/) | 获取数组的秩(维数)。例如，一维数组返回 1，二维数组返回 2，依此类推。 |
| [**【sync root】**](https://www.geeksforgeeks.org/how-to-get-synchronize-access-to-the-array-in-c-sharp/) | 获取一个对象，该对象可用于同步对数组的访问。 |

</figure>

**例 1:**

## C#

```cs
// C# program to illustrate
// Length property of Array class
using System;
namespace geeksforgeeks {

class GFG {

    // Main Method
    public static void Main()
    {

        // declares an 1D Array of string.
        string[] topic;

        // allocating memory for topic.
        topic = new string[] {"Array, ", "String, ",
                              "Stack, ", "Queue, ",
                              "Exception, ", "Operators"};

        // Displaying Elements of the array
        Console.WriteLine("Topic of C# :");
        Console.WriteLine();

        // Here we calculate and print
        // the length of the array, i.e. 6
        Console.WriteLine("Length of the array: {0}",
                                       topic.Length);
        foreach(string ele in topic)
            Console.WriteLine(ele + " ");
    }
}
}
```

**Output:** 

```cs
Topic of C# :

Length of the array: 6
Array,  
String,  
Stack,  
Queue,  
Exception,  
Operators
```

**例 2:**

## C#

```cs
// C# program to illustrate the
// Rank property of Array class
using System;
namespace geeksforgeeks {

class GFG {

    // Main Method
    public static void Main()
    {

        // declares an 1D Array of string.
        string[] topic;

        // allocating memory for topic.
        topic = new string[] {"Array, ", "String, ",
                              "Stack, ", "Queue, ",
                              "Exception, ", "Operators" };

        // Displaying Elements of array
        Console.WriteLine("Topic of C# :");
        Console.WriteLine();

        // Rank property provides the dimension rank
        // here we use 1-D array so it return 1
        // if we use 2-D array then it will return 2
        Console.WriteLine("Rank of the array: {0}",
                                         topic.Rank);
        foreach(string ele in topic)
            Console.WriteLine(ele + " ");
    }
}
}
```

**Output:** 

```cs
Topic of C# :

Rank of the array: 1
Array,  
String,  
Stack,  
Queue,  
Exception,  
Operators
```

#### 方法

<figure class="table">

| 方法 | 描述 |
| --- | --- |
| [**【ASR only()**](https://www.geeksforgeeks.org/c-array-asreadonlyt-method/) | 返回指定数组的只读包装。 |
| [**BinarySearch()**](https://www.geeksforgeeks.org/how-to-use-array-binarysearch-method-in-c-sharp-set-1/) | 使用二分搜索法算法在一维排序数组中搜索值。 |
| [**晴()**](https://www.geeksforgeeks.org/c-array-clear-method/) | 将数组中的元素范围设置为每个元素类型的默认值。 |
| **克隆()** | 创建数组的浅拷贝。 |
| [**约束副本()**](https://www.geeksforgeeks.org/c-array-constrainedcopy-method/) | 从指定的源索引开始复制数组中的一系列元素，并将其粘贴到从指定的目标索引开始的另一个数组中。保证如果复制没有完全成功，所有更改都将被撤消。 |
| [**【全部转换()**](https://www.geeksforgeeks.org/c-converting-an-array-of-one-type-to-an-array-of-another-type/) | 将一种类型的数组转换为另一种类型的数组。 |
| **复制()** | 将一个数组中的一系列元素复制到另一个数组，并根据需要执行类型转换和装箱。 |
| **CopyTo()** | 将当前一维数组的所有元素复制到指定的一维数组。 |
| **CreateInstance()** | 初始化数组类的新实例。 |
| **空()** | 返回一个空数组。 |
| [**等于()**](https://www.geeksforgeeks.org/c-check-if-an-array-object-is-equal-to-another-array-object/) | 确定指定的对象是否等于当前对象。 |
| [**存在()**](https://www.geeksforgeeks.org/c-check-if-an-array-contain-the-elements-that-match-the-specified-conditions/) | 确定指定数组是否包含与指定谓词定义的条件相匹配的元素。 |
| [**Find()**](https://www.geeksforgeeks.org/c-array-find-method/) | 搜索与指定谓词定义的条件匹配的元素，并返回整个数组中的第一个匹配项。 |
| [**【find all()**](https://www.geeksforgeeks.org/c-array-findall-method/) | 检索与指定谓词定义的条件匹配的所有元素。 |
| 查找指数() | 搜索与指定谓词定义的条件相匹配的元素，并返回数组中第一个匹配项或其一部分的从零开始的索引。 |
| [**查找最后（）**](https://www.geeksforgeeks.org/c-array-findlast-method/) | 搜索与指定谓词定义的条件匹配的元素，并返回整个数组中的最后一个匹配项。 |
| **FindLastIndex()** | 搜索与指定谓词定义的条件相匹配的元素，并返回数组中最后一个匹配项或其一部分的从零开始的索引。 |
| [**ForEach()**](https://www.geeksforgeeks.org/c-performing-specified-action-on-each-element-of-array/) | 对指定数组的每个元素执行指定的操作。 |
| [**【get 分子()**](https://www.geeksforgeeks.org/c-array-getenumerator-method/) | 为数组返回一个 IEnumerator。 |
| **GetHashCode（）** | 用作默认哈希函数。 |
| [**【get ength()**](https://www.geeksforgeeks.org/c-total-number-of-elements-present-in-an-array/) | 获取一个 32 位整数，该整数表示数组指定维度中的元素数。 |
| [**【get longlength()**](https://www.geeksforgeeks.org/total-number-of-elements-in-a-specified-dimension-of-an-array-in-c/) | 获取一个 64 位整数，该整数表示数组指定维度中的元素数。 |
| [**【get power bound()**](https://www.geeksforgeeks.org/c-finding-the-index-of-first-element-in-the-array/) | 获取数组中指定维度的第一个元素的索引。 |
| gettype() | 获取当前实例的类型。 |
| [**获取支持（）**](https://www.geeksforgeeks.org/c-finding-the-index-of-last-element-in-the-array/) | 获取数组中指定维度的最后一个元素的索引。 |
| **GetValue（）** | 获取当前数组中指定元素的值。 |
| **指数（）** | 搜索指定的对象，并返回其在一维数组或数组元素范围中的第一个匹配项的索引。 |
| **初始化()** | 通过调用值类型的默认构造函数来初始化值类型数组的每个元素。 |
| [**最新索引（）**](https://www.geeksforgeeks.org/array-lastindexof-method-in-c-sharp-set-1/) | 返回一维数组或数组的一部分中最后一次出现的值的索引。 |
| **MemberWiseCrone()** | 创建当前对象的浅拷贝。 |
| [**调整大小()**](https://www.geeksforgeeks.org/c-how-to-change-the-size-of-one-dimensional-array/) | 将一维数组的元素数量更改为指定的新大小。 |
| **反转()** | 反转一维数组或数组一部分中元素的顺序。 |
| **集值（）** | 将当前数组中的指定元素设置为指定值。 |
| [**【排序()**](https://www.geeksforgeeks.org/how-to-sort-an-array-in-c-sharp-array-sort-method-set-1/) | 对一维数组中的元素进行排序。 |
| **ToString()** | 返回表示当前对象的字符串。
(从对象继承) |
| [**【true forall()**](https://www.geeksforgeeks.org/c-array-trueforall-method/) | 确定数组中的每个元素是否符合指定谓词定义的条件。 |

</figure>

**例 1:**

## C#

```cs
// C# program to illustrate the Reverse() Method
using System;
namespace geeksforgeeks {

class GFG {

    // Main Method
    public static void Main()
    {

        // declares an 1D Array of string.
        string[] topic;

        // allocating memory for topic.
        topic = new string[] {"Array, ", "String, ",
                              "Stack, ", "Queue, ",
                              "Exception, ", "Operators" };

        // Displaying Elements of
        // the array before reverse
        Console.WriteLine("Topic of C# before reverse:");
        Console.WriteLine();
        foreach(string ele in topic)
        {
            Console.WriteLine(ele + " ");
        }
        Console.WriteLine();

        // using Reverse() method to
        // reverse the given array
        Array.Reverse(topic);

        // Displaying Elements of array after reverse
        Console.WriteLine("Topic of C# after reverse:");
        Console.WriteLine();
        foreach(string val in topic)
        {
            Console.WriteLine(val + " ");
        }
    }
}
}
```

**Output:** 

```cs
Topic of C# before reverse:

Array,  
String,  
Stack,  
Queue,  
Exception,  
Operators 

Topic of C# after reverse:

Operators 
Exception,  
Queue,  
Stack,  
String,  
Array,
```

**例 2:**

## C#

```cs
// C# program to illustrate the Sort() Method
using System;
namespace geeksforgeeks {

class GFG {

    // Main Method
    public static void Main()
    {

        // declares an 1D Array of string.
        string[] topic;

        // allocating memory for topic.
        topic = new string[] {"Array, ", "String, ",
                              "Stack, ", "Queue, ",
                              "Exception, ", "Operators" };

        // Displaying Elements of the array before sort
        Console.WriteLine("Topic of C# before reverse:");
        Console.WriteLine();
        foreach(string ele in topic)
        {
            Console.WriteLine(ele + " ");
        }
        Console.WriteLine();

        // using Sort() method to
        // sort the given array
        Array.Sort(topic);

        // Displaying Elements of
        // array after sort
        Console.WriteLine("Topic of C# after reverse:");
        Console.WriteLine();
        foreach(string val in topic)
        {
            Console.WriteLine(val + " ");
        }
    }
}
}
```

**Output:** 

```cs
Topic of C# before reverse:

Array,  
String,  
Stack,  
Queue,  
Exception,  
Operators 

Topic of C# after reverse:

Array,  
Exception,  
Operators 
Queue,  
Stack,  
String,
```

**参考:**

*   [https://docs.microsoft.com/en-us/dotnet/api/system.array?视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.array?view=netframework-4.7.2)