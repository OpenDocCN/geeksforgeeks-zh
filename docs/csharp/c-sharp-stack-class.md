# C# |栈类

> 原文:[https://www.geeksforgeeks.org/c-sharp-stack-class/](https://www.geeksforgeeks.org/c-sharp-stack-class/)

**[栈](https://www.geeksforgeeks.org/stack-data-structure/)** 代表一个 ***后进先出*** 的集合对象。当您需要后进先出访问项目时，可以使用它。当您在列表中添加一个项目时，它被称为**推动**项目，当您移除它时，它被称为**弹出**项目。该类属于 ***系统。集合*** 命名空间。

**栈类特征:**

*   堆栈的容量是堆栈可以容纳的元素数量。随着元素添加到堆栈中，容量会根据需要通过重新分配自动增加。
*   如果计数小于堆栈的容量，推送是一个*0(1)*操作。如果需要增加容量来容纳新元素，Push 将成为 *O(n)* 操作，其中 *n* 为 Count。Pop 是一个 *O(1)* 操作。
*   堆栈接受 null 作为有效值，并允许重复元素。

#### 构造器

| 构造器 | 描述 |
| **[Stack()](https://www.geeksforgeeks.org/c-sharp-how-to-create-a-stack/)** | 初始化堆栈类的新实例，该实例为空并具有默认的初始容量。 |
| **堆栈(ICollection)** | 初始化堆栈类的新实例，该实例包含从指定集合复制的元素，并且具有与复制的元素数量相同的初始容量。 |
| **堆栈(Int32)** | 初始化堆栈类的新实例，该实例为空，具有指定的初始容量或默认初始容量，以较大者为准。 |

**示例:**

```cs
// C# code to create a Stack
using System;
using System.Collections;
class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Stack
        Stack myStack = new Stack();

        // Inserting the elements into the Stack
        myStack.Push("1st Element");
        myStack.Push("2nd Element");
        myStack.Push("3rd Element");
        myStack.Push("4th Element");
        myStack.Push("5th Element");
        myStack.Push("6th Element");

        // Displaying the count of elements
        // contained in the Stack
        Console.Write("Total number of elements in the Stack are : ");

        Console.WriteLine(myStack.Count);

        // Displaying the top element of Stack
        // without removing it from the Stack
        Console.WriteLine("Element at the top is : " + myStack.Peek());

        // Displaying the top element of Stack
        // without removing it from the Stack
        Console.WriteLine("Element at the top is : " + myStack.Peek());

        // Displaying the count of elements
        // contained in the Stack
        Console.Write("Total number of elements in the Stack are : ");

        Console.WriteLine(myStack.Count);
    }
}
```

**输出:**

```cs
Total number of elements in the Stack are : 6
Element at the top is : 6th Element
Element at the top is : 6th Element
Total number of elements in the Stack are : 6

```

#### 性能

| 财产 | 描述 |
| **[计数](https://www.geeksforgeeks.org/stack-count-property-in-c-sharp/)** | 获取堆栈中包含的元素数量。 |
| **[同步](https://www.geeksforgeeks.org/stack-issynchronized-property-in-c-sharp/)** | 获取一个值，该值指示对堆栈的访问是否同步(线程安全)。 |
| **[【sync root】](https://www.geeksforgeeks.org/how-to-get-synchronize-access-to-the-stack-in-c-sharp/)** | 获取可用于同步对堆栈的访问的对象。 |

**示例:**

```cs
// C# code to Get the number of
// elements contained in the Stack
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Stack
        Stack myStack = new Stack();

        // Inserting the elements into the Stack
        myStack.Push("Chandigarh");
        myStack.Push("Delhi");
        myStack.Push("Noida");
        myStack.Push("Himachal");
        myStack.Push("Punjab");
        myStack.Push("Jammu");

        // Displaying the count of elements
        // contained in the Stack
        Console.Write("Total number of elements in the Stack are : ");

        Console.WriteLine(myStack.Count);
    }
}
```

**输出:**

```cs
Total number of elements in the Stack are : 6

```

#### 方法

| 方法 | 描述 |
| **[晴()](https://www.geeksforgeeks.org/stack-clear-method-in-c-sharp/)** | 从堆栈中移除所有对象。 |
| **T1】克隆()T3】** | 创建堆栈的浅拷贝。 |
| **[包含(对象)](https://www.geeksforgeeks.org/stack-contains-method-in-c-sharp/)** | 确定元素是否在堆栈中。 |
| **[CopyTo(Array，Int32)](https://www.geeksforgeeks.org/stack-copyto-method-in-c-sharp/)** | 从指定的数组索引开始，将堆栈复制到现有的一维数组。 |
| **[等于(对象)](https://www.geeksforgeeks.org/stack-equals-method-in-c-sharp/)** | 确定指定的对象是否等于当前对象。 |
| **[【get 分子()](https://www.geeksforgeeks.org/stack-getenumerator-method-in-c-sharp/)** | 为堆栈返回一个 IEnumerator。 |
| **GetHashCode（）** | 用作默认哈希函数。 |
| gettype() | 获取当前实例的类型。 |
| **MemberWiseCrone()** | 创建当前对象的浅拷贝。 |
| **[【Peek()](https://www.geeksforgeeks.org/stack-peek-method-in-c-sharp/)** | 返回堆栈顶部的对象，而不移除它。 |
| **[【pop()](https://www.geeksforgeeks.org/stack-pop-method-in-c-sharp/)** | 移除并返回堆栈顶部的对象。 |
| **[【推(物)](https://www.geeksforgeeks.org/stack-push-method-in-c-sharp/)** | 在堆栈顶部插入一个对象。 |
| **[【同步(叠加)](https://www.geeksforgeeks.org/stack-synchronized-method-in-c-sharp/)** | 返回堆栈的同步(线程安全)包装。 |
| **[【toaarray()](https://www.geeksforgeeks.org/stack-toarray-method-in-c-sharp/)** | 将堆栈复制到新阵列。 |
| **[ToString()](https://www.geeksforgeeks.org/stack-tostring-method-in-c-sharp-with-examples/)** | 返回表示当前对象的字符串。 |

**示例:**

```cs
// C# code to Remove all
// objects from the Stack
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Stack 
        Stack myStack = new Stack();

        // Inserting the elements into the Stack
        myStack.Push("1st Element");
        myStack.Push("2nd Element");
        myStack.Push("3rd Element");
        myStack.Push("4th Element");
        myStack.Push("5th Element");
        myStack.Push("6th Element");

        // Displaying the count of elements
        // contained in the Stack before
        // removing all the elements
        Console.Write("Total number of elements in the Stack are : ");

        Console.WriteLine(myStack.Count);

        // Removing all elements from Stack
        myStack.Clear();

        // Displaying the count of elements
        // contained in the Stack after
        // removing all the elements
        Console.Write("Total number of elements in the Stack are : ");

        Console.WriteLine(myStack.Count);
    }
}
```

**Output:**

```cs
Total number of elements in the Stack are : 6
Total number of elements in the Stack are : 0

```

**示例:**

```cs
// C# code to Check if a Stack
// contains an element
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Stack of strings
        Stack myStack = new Stack();

        // Inserting the elements into the Stack
        myStack.Push("Geeks");
        myStack.Push("Geeks Classes");
        myStack.Push("Noida");
        myStack.Push("Data Structures");
        myStack.Push("GeeksforGeeks");

        // Checking whether the element is
        // present in the Stack or not
        // The function returns True if the
        // element is present in the Stack, else
        // returns False
        Console.WriteLine(myStack.Contains("GeeksforGeeks"));
    }
}
```

**Output:**

```cs
True

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . stack？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.stack?view=netframework-4.7.2)