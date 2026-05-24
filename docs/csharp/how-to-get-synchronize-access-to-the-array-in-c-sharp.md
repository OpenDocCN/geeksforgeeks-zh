# 如何在 C# 中同步访问数组

> 原文:[https://www . geeksforgeeks . org/如何同步访问 c-sharp 中的阵列/](https://www.geeksforgeeks.org/how-to-get-synchronize-access-to-the-array-in-c-sharp/)

**阵列。同步根属性**用于获取一个对象，该对象可用于同步对阵列的访问。一个[数组](https://www.geeksforgeeks.org/c-sharp-arrays/)是一组相似类型的变量，它们被一个共同的名字所引用。[数组类](https://www.geeksforgeeks.org/c-sharp-array-class/)属于*系统*命名空间。

**要点:**

*   完成对象的同步后，只有一个线程可以操作数组中的数据。
*   属性是提供读取、写入和计算私有数据字段的方法的类的成员。
*   *阵列。同步根属性*实现*系统。收藏。收藏*界面。
*   同步代码不能直接在集合上执行，因此它必须在集合的同步根上执行操作，以保证从其他对象派生的集合的正确操作。
*   检索该属性的值是一个 O(1)操作。

> **语法:** arrayName。SyncRoot
> 
> **属性值:**可用于同步访问阵列的对象。

**示例 1:** 在这段代码中，我们使用 SyncRoot 来获得对名为 *arr* 的数组的同步访问，这不是一个线程安全的过程，可能会导致异常。所以为了避免异常，我们在枚举期间锁定集合。

```cs
// C# program to illustrate the 
// use of SyncRoot property
using System;
using System.Threading;
using System.Collections;

namespace sync_root {

class GFG {

    // Main Method
    static void Main(string[] args)
    {

        // Declaring an array
        Array arr = new int[] {12, 15, 20, 3, 6};

        // Using the SyncRoot property
        lock(arr.SyncRoot)
        {
            // foreach loop to display 
            // the elements in arr
            foreach(Object i in arr)
                Console.WriteLine(i);
        }
    }
}
}
```

**Output:**

```cs
12
15
20
3
6

```

**示例 2:** 在下面的示例中，我们对类 x 的对象数组使用了 SynRoot 属性

```cs
// C# program to depict the use
// of SyncRoot Property
// for an array of objects
using System;
using System.Threading;
using System.Collections;

namespace sync_root_2 {

// User defined class X
class X {

    int x;

    // defining Constructor
    public X()
    {
        x = 0;
    }

    // Method to get the value
    // stored in x
    public int getValue()
    {
        return x;
    }
}

// Driver Class
public class Program {

    // Main Method
    static void Main(string[] args)
    {
        // Declaring an array of objects
        // of type class X
        X[] obj = new X[5];

        // Calling the constructor
        // for each object
        for (int i = 0; i < 5; i++)
            obj[i] = new X();

        // Synchronizing the array
        lock(obj.SyncRoot)
        {
            // Displaying the value
            foreach(X element in obj)
                Console.WriteLine(element.getValue());
        }
    }
}
}
```

**Output:**

```cs
0
0
0
0
0

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . array . sync root？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.array.syncroot?view=netframework-4.7.2)