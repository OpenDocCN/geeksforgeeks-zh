# C# |向 HashSet 添加元素

> 原文：[https://www.geeksforgeeks.org/c-sharp-add-element-to-hashset/](https://www.geeksforgeeks.org/c-sharp-add-element-to-hashset/)

一个`HashSet`是一个无序的**独特元素**的集合。它属于`System.Collections.Generic`命名空间。它用于我们希望防止在集合中插入重复项的情况。就性能而言，与列表相比更好。可以使用`HashSet<T>.Add(T item)`方法将元素添加到`HashSet`中。

## 语法：

```cs
mySet.Add(T item);
```

这里`mySet`是`HashSet`的名字。

## 参数：

> **item:** 要添加到集合中的元素。

## 返回类型：

如果元素被添加到`HashSet<T>`对象中，此方法返回`true`。如果元素已经存在，则返回`false`。

下面给出了一些例子，以便更好地理解实现：

### 例 1：

```cs
// C# code to add element to HashSet
using System;
using System.Collections.Generic;

class GFG {

// Driver code
    public static void Main()
    {

// Creating a HashSet of odd numbers
        HashSet<int> odd = new HashSet<int>();

// Inserting elements in HashSet
        for (int i = 0; i < 5; i++) {
            odd.Add(2 * i + 1);
        }

// Displaying the elements in the HashSet
        foreach(int i in odd)
        {
            Console.WriteLine(i);
        }
    }
}
```

**Output:**

```cs

```

### 例 2：

```cs
// C# code to add element to HashSet
using System;
using System.Collections.Generic;

class GFG {

// Driver code
    public static void Main()
    {

// Creating a HashSet of strings
        HashSet<string> mySet = new HashSet<string>();

// Inserting elements in HashSet
        mySet.Add("Geeks");
        mySet.Add("GeeksforGeeks");
        mySet.Add("GeeksClasses");
        mySet.Add("GeeksQuiz");

// Displaying the elements in the HashSet
        foreach(string i in mySet)
        {
            Console.WriteLine(i);
        }
    }
}
```

**Output:**

```cs
Geeks
GeeksforGeeks
GeeksClasses
GeeksQuiz
```

## 参考：

*   [https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.hashset-1.add?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.hashset-1.add?view=netframework-4.7.2)