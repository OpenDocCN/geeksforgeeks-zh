# C# | 为数组列表创建只读包装器

> 原文：[https://www.geeksforgeeks.org/c-sharp-creating-a-read-only-wrapper-for-the-arraylist/](https://www.geeksforgeeks.org/c-sharp-creating-a-read-only-wrapper-for-the-arraylist/)

## `ArrayList.ReadOnly(ArrayList)` 方法

`ArrayList.ReadOnly(ArrayList)` 方法用于获取一个只读的 [`ArrayList`](https://www.geeksforgeeks.org/c-arraylist-class/) 包装器。

## 语法

```cs
public static ArrayList ReadOnly(ArrayList list);
```

这里 `list` 是要包装的 `ArrayList`。

## 返回值

返回一个只读 `ArrayList` 包装器，用于包装 `list`。

## 异常

如果 `list` 为 `null`，该方法返回 `ArgumentNullException`。

## 示例

以下程序说明了上述方法的使用：

### 例 1

```cs
// C# code to create a read-only
// wrapper for the ArrayList
using System;
using System.Collections;

class GFG {

// Driver code
    public static void Main()
    {

// Creating an ArrayList
        ArrayList myList = new ArrayList();

// Adding elements to ArrayList
        myList.Add("Geeks");
        myList.Add("for");
        myList.Add("Geeks");
        myList.Add("Noida");
        myList.Add("Geeks Classes");
        myList.Add("Delhi");

// Creating a Read-Only packing
        // around the ArrayList
        ArrayList myList2 = ArrayList.ReadOnly(myList);

// --------- Using IsReadOnly Property

// print the status of both ArrayList
        Console.WriteLine("myList ArrayList is {0}.",
                    myList.IsReadOnly ? "read-only" : 
                                    "not read-only");

        Console.WriteLine("myList2 ArrayList is {0}.",
                    myList2.IsReadOnly ? "read-only" : 
                                     "not read-only");
    }
}
```

**输出：**

```cs
myList ArrayList is not read-only.
myList2 ArrayList is read-only.
```

### 例 2

```cs
// C# code to create a read-only 
// wrapper for the ArrayList
using System; 
using System.Collections;

class GFG {

// Driver code 
    public static void Main() 
    {

// Creating an ArrayList 
        ArrayList myList = new ArrayList();

// Adding elements to ArrayList 
        myList.Add("C"); 
        myList.Add("C++"); 
        myList.Add("Java"); 
        myList.Add("C#"); 
        myList.Add("Python");

        Console.WriteLine("Before Wrapping: ");

// Displaying the elements in the ArrayList 
        foreach(string str in myList) 
        { 
            Console.WriteLine(str); 
        }

// Creating a Read-Only packing 
        // around the ArrayList 
        ArrayList myList2 = ArrayList.ReadOnly(myList);

        Console.WriteLine("After Wrapping: ");

// Displaying the elements 
        foreach(string str in myList2) 
        { 
            Console.WriteLine(str); 
        }

        Console.WriteLine("Trying to add new element into myList2:");

// it will give error
        myList2.Add("HTML");

    } 
} 
```

**输出：**

```cs
Before Wrapping: 
C
C++
Java
C#
Python
After Wrapping: 
C
C++
Java
C#
Python
Trying to add new element into myList2:
```

**运行时错误：**

> 未处理异常：
> `System.NotSupportedException`: 集合是只读的。
> 在 `System.Collections.ArrayList+ReadOnlyArrayList.Add`

## 说明

在上面的程序中，可以在 `myList` 中添加或删除元素，即原始 `ArrayList`，它将反映到只读集合中。

## 注

*   为防止对 `list` 的任何修改，仅通过此包装暴露 `list`。
*   只读集合只是一个带有防止修改集合的包装的集合。如果对基础集合进行了更改，只读集合将反映这些更改。
*   这个方法是一个 O(1) 运算。

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.collections.arraylist.readonly?view=netframework-4.7.2#System_Collections_ArrayList_ReadOnly_System_Collections_ArrayList_](https://docs.microsoft.com/en-us/dotnet/api/system.collections.arraylist.readonly?view=netframework-4.7.2#System_Collections_ArrayList_ReadOnly_System_Collections_ArrayList_)