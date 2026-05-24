# C# |队列类

> 原文:[https://www.geeksforgeeks.org/c-sharp-queue-class/](https://www.geeksforgeeks.org/c-sharp-queue-class/)

**[队列](https://www.geeksforgeeks.org/queue-data-structure/)** 代表一个 ***先进先出*** 集合的对象。当您需要先进先出访问项目时，可以使用它。当您在列表中添加一个项目时，它被称为**入队**，当您移除一个项目时，它被称为**出队**。该类属于**系统。集合**命名空间并实现 *ICollection、IEnumerable 和 I Coloneable*接口。

**队列类特征:**

*   **入队**在队列末尾添加一个元素。
*   **出列**从队列开始处移除最旧的元素。
*   **Peek** 返回队列开始处最早的元素，但不将其从队列中移除。
*   队列的**容量**是队列可以容纳的元素数量。
*   当元素添加到队列中时，容量会根据需要通过重新分配内部阵列来自动增加。
*   队列接受 **null** 作为引用类型的有效值，并允许重复元素。

#### 构造器

| 构造器 | 描述 |
| [队列()](https://www.geeksforgeeks.org/how-to-create-a-queue-in-c-sharp/) | 初始化队列类的新实例，该实例为空，具有默认初始容量，并使用默认增长因子。 |
| **伫列(icollion)** | 初始化队列类的新实例，该实例包含从指定集合复制的元素，具有与复制的元素数相同的初始容量，并使用默认增长因子。 |
| **队列(Int32)** | 初始化队列类的新实例，该实例为空，具有指定的初始容量，并使用默认增长因子。 |
| **队列(Int32，单个)** | 初始化队列类的新实例，该实例为空，具有指定的初始容量，并使用指定的增长因子。 |

**示例:**

```cs
// C# code to create a Queue
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Queue 
        Queue myQueue = new Queue();

        // Inserting the elements into the Queue
        myQueue.Enqueue("one");

        // Displaying the count of elements
        // contained in the Queue
        Console.Write("Total number of elements in the Queue are : ");

        Console.WriteLine(myQueue.Count);

        myQueue.Enqueue("two");

        // Displaying the count of elements
        // contained in the Queue
        Console.Write("Total number of elements in the Queue are : ");

        Console.WriteLine(myQueue.Count);

        myQueue.Enqueue("three");

        // Displaying the count of elements
        // contained in the Queue
        Console.Write("Total number of elements in the Queue are : ");

        Console.WriteLine(myQueue.Count);

        myQueue.Enqueue("four");

        // Displaying the count of elements
        // contained in the Queue
        Console.Write("Total number of elements in the Queue are : ");

        Console.WriteLine(myQueue.Count);

        myQueue.Enqueue("five");

        // Displaying the count of elements
        // contained in the Queue
        Console.Write("Total number of elements in the Queue are : ");

        Console.WriteLine(myQueue.Count);

        myQueue.Enqueue("six");

        // Displaying the count of elements
        // contained in the Queue
        Console.Write("Total number of elements in the Queue are : ");

        Console.WriteLine(myQueue.Count);
    }
}
```

**Output:**

```cs
Total number of elements in the Queue are : 1
Total number of elements in the Queue are : 2
Total number of elements in the Queue are : 3
Total number of elements in the Queue are : 4
Total number of elements in the Queue are : 5
Total number of elements in the Queue are : 6

```

#### 性能

| 财产 | 描述 |
| **[计数](https://www.geeksforgeeks.org/queue-count-property-in-c-sharp/)** | 获取队列中包含的元素数量。 |
| **[同步](https://www.geeksforgeeks.org/queue-issynchronized-property-in-c-sharp/)** | 获取一个值，该值指示对队列的访问是否同步(线程安全)。 |
| **[【sync root】](https://www.geeksforgeeks.org/how-to-get-synchronize-access-to-the-queue-in-c-sharp/)** | 获取一个对象，该对象可用于同步对队列的访问。 |

**示例:**

```cs
// C# code to Get the number of
// elements contained in the Queue
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Queue
        Queue myQueue = new Queue();

        // Inserting the elements into the Queue
        myQueue.Enqueue("Chandigarh");
        myQueue.Enqueue("Delhi");
        myQueue.Enqueue("Noida");
        myQueue.Enqueue("Himachal");
        myQueue.Enqueue("Punjab");
        myQueue.Enqueue("Jammu");

        // Displaying the count of elements
        // contained in the Queue
        Console.Write("Total number of elements in the Queue are : ");

        Console.WriteLine(myQueue.Count);
    }
}
```

**Output:**

```cs
Total number of elements in the Queue are : 6

```

#### 方法

| 方法 | 描述 |
| **[晴()](https://www.geeksforgeeks.org/queue-clear-method-in-c-sharp/)** | 从队列中移除所有对象。 |
| **T1】克隆()T3】** | 创建队列的浅拷贝。 |
| **[包含(对象)](https://www.geeksforgeeks.org/queue-contains-method-in-c-sharp/)** | 确定元素是否在队列中。 |
| **[CopyTo(Array，Int32)](https://www.geeksforgeeks.org/queue-copyto-method-in-c-sharp/)** | 从指定的数组索引开始，将队列元素复制到现有的一维数组中。 |
| **[出列()](https://www.geeksforgeeks.org/queue-dequeue-method-in-c-sharp/)** | 移除并返回队列开头的对象。 |
| **[【入队(对象)](https://www.geeksforgeeks.org/queue-enqueue-method-in-c-sharp/)** | 将对象添加到队列的末尾。 |
| **[等于(对象)](https://www.geeksforgeeks.org/queue-equals-method-in-c-sharp/)** | 确定指定的对象是否等于当前对象。 |
| **[【get 分子()](https://www.geeksforgeeks.org/queue-getenumerator-method-in-c-sharp/)** | 返回遍历队列的枚举数。 |
| **GetHashCode（）** | 用作默认哈希函数。 |
| gettype() | 获取当前实例的类型。 |
| **MemberWiseCrone()** | 创建当前对象的浅拷贝。 |
| **[【Peek()](https://www.geeksforgeeks.org/queue-peek-method-in-c-sharp/)** | 返回队列开头的对象，而不删除它。 |
| **[【同步(排队)](https://www.geeksforgeeks.org/queue-synchronized-method-in-c-sharp/)** | 返回一个新队列，该队列包装原始队列，并且是线程安全的。 |
| **[【toaarray()](https://www.geeksforgeeks.org/queue-toarray-method-in-c-sharp/)** | 将队列元素复制到新数组中。 |
| **ToString()** | 返回表示当前对象的字符串。 |
| **TrimToSize()** | 将容量设置为队列中元素的实际数量。 |

**例 1:**

```cs
// C# code to Check if a Queue
// contains an element
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Queue
        Queue myQueue = new Queue();

        // Inserting the elements into the Queue
        myQueue.Enqueue(5);
        myQueue.Enqueue(10);
        myQueue.Enqueue(15);
        myQueue.Enqueue(20);
        myQueue.Enqueue(25);

        // Checking whether the element is
        // present in the Queue or not
        // The function returns True if the
        // element is present in the Queue, else
        // returns False
        Console.WriteLine(myQueue.Contains(7));
    }
}
```

**Output:**

```cs
False

```

**例 2:**

```cs
// C# code to Convert Queue to array
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Queue 
        Queue myQueue = new Queue();

        // Inserting the elements into the Queue
        myQueue.Enqueue("Geeks");
        myQueue.Enqueue("Geeks Classes");
        myQueue.Enqueue("Noida");
        myQueue.Enqueue("Data Structures");
        myQueue.Enqueue("GeeksforGeeks");

        // Converting the Queue
        // into object array
        Object[] arr = myQueue.ToArray();

        // Displaying the elements in array
        foreach(Object obj in arr)
        {
            Console.WriteLine(obj);
        }
    }
}
```

**Output:**

```cs
Geeks
Geeks Classes
Noida
Data Structures
GeeksforGeeks

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . queue？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.queue?view=netframework-4.7.2)