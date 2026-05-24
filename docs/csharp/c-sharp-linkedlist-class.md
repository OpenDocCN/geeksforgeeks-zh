# C# |链表类

> 原文:[https://www.geeksforgeeks.org/c-sharp-linkedlist-class/](https://www.geeksforgeeks.org/c-sharp-linkedlist-class/)

**[链接列表](https://www.geeksforgeeks.org/data-structures/linked-list/)<**>**类存在于 ***系统中。集合.通用*** 命名空间。这种泛型类型允许快速插入和移除元素。它实现了一个经典的链表。每个对象都是单独分配的。在链接列表中，某些操作不需要复制整个集合。但是在许多常见的情况下，LinkedList 会影响性能。**

****链表类的特征:****

*   ****链表<T1**T5 是一个通用链表。它支持枚举器。**
*   **插入和取出是 **O(1)** 操作。**
*   **您可以删除节点并将其重新插入到同一个列表或另一个列表中，这样就不会在堆上分配额外的对象。**
*   **因为列表还维护内部计数，所以获取计数属性是一个 O(1)操作。**
*   **链接列表中的每个节点< **T** >对象属于链接列表节点<**T**T6 类型。**
*   **LinkedList 类不支持链接、拆分、循环或其他可能使列表处于不一致状态的功能。**
*   **如果链接列表为空，则**第一个**和**最后一个**属性包含空值。**
*   **链接列表是双向链接的，因此，每个节点都指向下一个节点，并向后指向上一个节点。**

#### **构造器**

| 构造器 | 描述 |
| **链接列表()** | 初始化空的 LinkedList 类的新实例。 |
| **链接列表(无数)** | 初始化 LinkedList 类的新实例，该实例包含从指定的 IEnumerable 复制的元素，并且有足够的容量容纳复制的元素数量。 |
| **链接列表(SerializationInfo，StreamingContext)** | 初始化 LinkedList 类的新实例，该实例可使用指定的 SerializationInfo 和 StreamingContext 进行序列化。 |

****示例:****

```cs
// C# code to create a LinkedList
using System;
using System.Collections;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a LinkedList of Strings
        LinkedList<String> myList = new LinkedList<String>();

        // Adding nodes in LinkedList
        myList.AddLast("Geeks");
        myList.AddLast("for");
        myList.AddLast("Data Structures");
        myList.AddLast("Noida");

        // To check if LinkedList is empty or not
        if (myList.Count > 0)
            Console.WriteLine("LinkedList is not empty");
        else
            Console.WriteLine("LinkedList is empty");
    }
}
```

****输出:****

```cs
LinkedList is not empty 
```

#### **性能**

| 财产 | 描述 |
| **[计数](https://www.geeksforgeeks.org/c-get-the-number-of-nodes-contained-in-linkedlistt/)** | 获取链接列表中实际包含的节点数。 |
| **[第一](https://www.geeksforgeeks.org/c-get-the-first-node-of-the-linkedlistt/)** | 获取链接列表的第一个节点。 |
| **[最后](https://www.geeksforgeeks.org/c-get-the-last-node-of-the-linkedlistt/)** | 获取链接列表的最后一个节点。 |

****示例:****

```cs
// C# code to illustrate the
// LinkedList<T> class properties
using System;
using System.Collections;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a LinkedList of Strings
        LinkedList<String> myList = new LinkedList<String>();

        // Adding nodes in LinkedList
        myList.AddLast("GeeksforGeeks");
        myList.AddLast("GFG");
        myList.AddLast("Data Structures");
        myList.AddLast("Noida");

        // ------- Count Property -------

        // To get the first node of the LinkedList
        if (myList.Count > 0)
            Console.WriteLine(myList.First.Value);
        else
            Console.WriteLine("LinkedList is empty");

        // ------- Last Property -------

        // To get the last node of the LinkedList
        if (myList.Count > 0)
            Console.WriteLine(myList.Last.Value);
        else
            Console.WriteLine("LinkedList is empty");    

    }
}
```

****输出:****

```cs
GeeksforGeeks
Noida 
```

#### **方法**

| 方法 | 描述 |
| **添加后** | 在链接列表中的现有节点后添加新节点或值。 |
| 在之前添加 | 在链接列表中的现有节点之前添加新节点或值。 |
| **[【add first】](https://www.geeksforgeeks.org/c-adding-new-node-or-value-at-the-start-of-linkedlistt/)** | 在链接列表的开始处添加新的节点或值。 |
| **[【add last】](https://www.geeksforgeeks.org/c-adding-new-node-or-value-at-the-end-of-linkedlistt/)** | 在链接列表的末尾添加新的节点或值。 |
| **[晴()](https://www.geeksforgeeks.org/c-removing-all-nodes-from-linkedlistt/)** | 从链接列表中删除所有节点。 |
| **[包含(T)](https://www.geeksforgeeks.org/c-check-if-a-value-is-in-linkedlistt/)** | 确定值是否在链接列表中。 |
| **[CopyTo(T[]，Int32)](https://www.geeksforgeeks.org/c-copy-the-entire-linkedlistt-to-array/)** | 从目标数组的指定索引开始，将整个链接列表复制到兼容的一维数组。 |
| **[等于(对象)](https://www.geeksforgeeks.org/c-check-if-two-linkedlistt-objects-are-equal/)** | 确定指定的对象是否等于当前对象。 |
| **[寻找(T)](https://www.geeksforgeeks.org/c-find-the-first-node-in-linkedlistt-containing-the-specified-value/)** | 查找包含指定值的第一个节点。 |
| **[FindLast(T)](https://www.geeksforgeeks.org/c-find-the-last-node-in-linkedlistt-containing-the-specified-value/)** | 查找包含指定值的最后一个节点。 |
| **[【get 分子()](https://www.geeksforgeeks.org/c-getting-an-enumerator-that-iterates-through-linkedlistt/)** | 返回遍历链表的枚举数。 |
| **GetHashCode（）** | 用作默认哈希函数。 |
| **GetObjectData(SerializationInfo，StreamingContext)** | 实现 ISerializable 接口并返回序列化 LinkedList 实例所需的数据。 |
| gettype() | 获取当前实例的类型。 |
| **MemberWiseCrone()** | 创建当前对象的浅拷贝。 |
| **on 序列化(对象)** | 实现 ISerializable 接口，并在反序列化完成时引发反序列化事件。 |
| **[移除(链接节点)](https://www.geeksforgeeks.org/c-removing-the-specified-node-from-the-linkedlistt/)** | 从链接列表中删除指定的节点。 |
| **[移除(T)](https://www.geeksforgeeks.org/c-removing-first-occurrence-of-specified-value-from-linkedlistt/)** | 从链接列表中删除指定值的第一个匹配项。 |
| **[【remove first()](https://www.geeksforgeeks.org/c-removing-the-node-at-the-start-of-the-linkedlistt/)** | 删除链接列表开头的节点。 |
| **[【删除负载()](https://www.geeksforgeeks.org/c-removing-the-node-at-the-end-of-linkedlistt/)** | 删除链接列表末尾的节点。 |
| **ToString()** | 返回表示当前对象的字符串。 |

****示例:****

```cs
// C# code to check if a
// value is in LinkedList
using System;
using System.Collections;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {
        // Creating a LinkedList of Strings
        LinkedList<String> myList = new LinkedList<String>();

        // Adding nodes in LinkedList
        myList.AddLast("A");
        myList.AddLast("B");
        myList.AddLast("C");
        myList.AddLast("D");
        myList.AddLast("E");

        // To check if a value is in LinkedList
        Console.WriteLine(myList.Contains("B"));
    }
}
```

****输出:****

```cs
True 
```

****示例:****

```cs
// C# code to remove the specified
// node from the LinkedList
using System;
using System.Collections;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a LinkedList of Integers
        LinkedList<int> myList = new LinkedList<int>();

        // Adding nodes in LinkedList
        myList.AddLast(2);
        myList.AddLast(4);
        myList.AddLast(6);
        myList.AddLast(8);

        // To get the count of nodes in LinkedList
        // before removing all the nodes
        Console.WriteLine("Total nodes in myList are : " + myList.Count);

        // Displaying the nodes in LinkedList
        foreach(int i in myList)
        {
            Console.WriteLine(i);
        }

        // Removing the first node from the LinkedList
        myList.Remove(myList.First);

        // To get the count of nodes in LinkedList
        // after removing all the nodes
        Console.WriteLine("Total nodes in myList are : " + myList.Count);

        // Displaying the nodes in LinkedList
        foreach(int i in myList)
        {
            Console.WriteLine(i);
        }
    }
}
```

****输出:****

```cs
Total nodes in myList are : 4
2
4
6
8
Total nodes in myList are : 3
4
6
8 
```

****参考:****

*   **[https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . linked list-1？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.linkedlist-1?view=netframework-4.7.2)**