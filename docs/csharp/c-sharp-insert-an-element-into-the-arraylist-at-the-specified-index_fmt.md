# C# |在数组列表中指定的索引处插入一个元素

> 原文：[https://www.geeksforgeeks.org/c-sharp-insert-an-element-into-the-arraylist-at-the-specified-index/](https://www.geeksforgeeks.org/c-sharp-insert-an-element-into-the-arraylist-at-the-specified-index/)

`ArrayList`表示可以单独索引的对象的有序集合。它基本上是数组的替代。它还允许动态内存分配、添加、搜索和排序列表中的项目。`ArrayList.Insert(Int32, Object)`方法将一个元素插入到数组列表的指定索引处。

## `ArrayList`类的属性

*   可以随时在`ArrayList`集合中添加或删除元素。
*   `ArrayList`不能保证排序。
*   `ArrayList`的容量是`ArrayList`可以容纳的元素数量。
*   可以使用整数索引访问此集合中的元素。此集合中的索引从零开始。
*   它还允许重复元素。
*   不支持在`ArrayList`集合中使用多维数组作为元素。

## 语法

```cs
public virtual void Insert (int index, object value);
```

## 参数

> `index`：是应该插入值的从零开始的索引。
> `value`：是要插入的对象。`value`可以为空。

## 异常

*   `ArgumentOutOfRangeException`：如果`index`小于零或`index`大于`Count`，即`ArrayList`中的元素数量。
*   `NotSupportedException`：如果`ArrayList`是只读的或者`ArrayList`具有固定的大小。

下面给出了一些例子，以便更好地理解实现：

### 例 1

```cs
// C# code to insert an element
// into the ArrayList at the
// specified index
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
        myList.Add("A");
        myList.Add("B");
        myList.Add("C");

// Displaying the elements in ArrayList
        Console.WriteLine("The initial ArrayList is : ");
        foreach(string str in myList)
        {
            Console.WriteLine(str);
        }

// Inserting 3 elements at random index in the ArrayList
        myList.Insert(1, "D");
        myList.Insert(4, "E");
        myList.Insert(5, "F");

// Displaying the modified ArrayList
        Console.WriteLine("The ArrayList after Inserting elements is : ");

// Displaying the elements in ArrayList
        foreach(string str in myList)
        {
            Console.WriteLine(str);
        }
    }
}
```

**Output:**

```cs
The initial ArrayList is : 
A
B
C
The ArrayList after Inserting elements is : 
A
D
B
C
E
F
```

### 例 2

```cs
// C# code to insert an element
// into the ArrayList at the
// specified index
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
        myList.Add(1);
        myList.Add(2);
        myList.Add(3);

// Displaying the elements in ArrayList
        Console.WriteLine("The initial ArrayList is : ");
        foreach(int i in myList)
        {
            Console.WriteLine(i);
        }

// Inserting 3 elements in front of the ArrayList
        myList.Insert(0, 4);
        myList.Insert(0, 5);
        myList.Insert(0, 6);

// Displaying the modified ArrayList
        Console.WriteLine("The ArrayList after Inserting elements is : ");

// Displaying the elements in ArrayList
        foreach(int i in myList)
        {
            Console.WriteLine(i);
        }
    }
}
```

**Output:**

```cs
The initial ArrayList is :

The ArrayList after Inserting elements is :
```

## 注

*   如果`index`等于`Count`，即`ArrayList`中的元素数量，则`ArrayList`的末尾会添加一个值。
*   这个方法是一个 O(n)运算，其中 n 是`Count`。

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.collections.arraylist.insert?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.arraylist.insert?view=netframework-4.7.2)