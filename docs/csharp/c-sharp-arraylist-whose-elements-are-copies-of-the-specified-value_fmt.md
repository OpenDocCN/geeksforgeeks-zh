# C# | 数组列表，其元素是指定值的副本

> 原文：[https://www.geeksforgeeks.org/c-sharp-arraylist-whose-elements-are-copies-of-the-specified-value/](https://www.geeksforgeeks.org/c-sharp-arraylist-whose-elements-are-copies-of-the-specified-value/)

`ArrayList.Repeat(Object, Int32)` 方法用于返回一个数组列表，该列表的元素是指定值的副本。或者换句话说，当你想在数组列表中重复一个指定的元素时，使用这个方法。此方法为 O(n) 运算，其中 n 为应复制项目的次数。

## 语法：

```cs
public static ArrayList Repeat (object item, int count);
```

## 参数：

> `item`：是在新数组列表中复制多次的对象。该值可以为空。
> `count`：统计 `item` 应复制的次数。

## 返回值：

该方法返回一个数组列表，其中包含 `count` 个元素，所有元素都是 `item` 的副本。

## 异常：

如果 `count` 值小于零，则该方法将给出 `ArgumentOutOfRangeException`。

下面给出了一些例子，以便更好地理解实现：

## 例 1：

```cs
// C# program to illustrate the use of 
// ArrayList.Repeat(Object, Int32) Method
using System;
using System.Collections;

class GFG {

// Main method
    public static void Main()
    {

// Create and repeat the element
        // of ArrayList "mylist" 
        ArrayList mylist = ArrayList.Repeat("GFG", 6);

// Display element
        foreach(Object ob in mylist)
        {
            Console.WriteLine(ob);
        }

// Display and count the total number of element
        Console.WriteLine("The count of the item is : {0}", mylist.Count);
    }
}
```

## 输出：

```cs
GFG
GFG
GFG
GFG
GFG
GFG
The count of the item is : 6
```

## 例 2：

```cs
// C# program to illustrate the use of 
// ArrayList.Repeat(Object, Int32) Method
using System;
using System.Collections;

class GFG {

// Main method
    public static void Main()
    {

// Create and repeat the 
        // element of mylist ArrayList
        // this will give runtime error
        // as count is less than 0
        ArrayList mylist = ArrayList.Repeat(43, -1);

// Display element
        foreach(Object ob in mylist)
        {
            Console.WriteLine(ob);
        }

// Display and count the total number of element
        Console.WriteLine("The count of the item is : {0}", mylist.Count);
    }
}
```

### 运行时错误：

> 未处理异常：
> System.ArgumentOutOfRangeException: 要求非负数。
> 参数名称: count

## 参考：

*   [https://docs.microsoft.com/en-us/dotnet/api/system.collections.arraylist.repeat?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.arraylist.repeat?view=netframework-4.7.2)