# C# | 获取数组列表中一系列元素的枚举数

> 原文：[https://www.geeksforgeeks.org/c-sharp-getting-an-enumerator-for-a-range-of-elements-in-the-arraylist/](https://www.geeksforgeeks.org/c-sharp-getting-an-enumerator-for-a-range-of-elements-in-the-arraylist/)

`ArrayList.GetEnumerator(Int32, Int32)` 方法用于获取 [`ArrayList`](https://www.geeksforgeeks.org/c-arraylist-class/) 中一系列元素的枚举数。

## 语法：

```cs
public virtual System.Collections.IEnumerator GetEnumerator(int index, int count);
```

## 参数：

- `index`：是 `ArrayList` 节的 `Int32` 类型的从零开始的索引，枚举器应该引用它。
- `count`：是 `ArrayList` 部分中枚举器应该引用的 `Int32` 类型的元素数。

## 返回值：

该方法为 `ArrayList` 中指定范围的元素返回一个 `IEnumerator`。

## 异常：

- `ArgumentOutOfRangeException`：如果 `index` 或 `count` 小于零。
- `ArgumentException`：如果 `index` 和 `count` 没有在 `ArrayList` 中指定有效范围。

以下程序说明了上述方法的使用：

### 例 1：

```cs
// C# code to get an enumerator for a
// range of elements in the ArrayList
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating an ArrayList
        ArrayList myList = new ArrayList();

        // adding elements in myList
        myList.Add(14);
        myList.Add(45);
        myList.Add(78);
        myList.Add(48);
        myList.Add(49);
        myList.Add(51);
        myList.Add(77);

        // To get an Enumerator
        // for the ArrayList
        IEnumerator enumerator = myList.GetEnumerator();

        // If MoveNext passes the end of the
        // collection, the enumerator is positioned
        // after the last element in the ArrayList
        // and MoveNext returns false.
        while (enumerator.MoveNext()) {

            Console.WriteLine(enumerator.Current);
        }

        Console.WriteLine("After GetEnumerator(Int32, Int32) Method: ");

        // To get an Enumerator for a range
        // of elements of the ArrayList
        // here index is 3 and count is 2
        IEnumerator e = myList.GetEnumerator(3, 2);

        // If MoveNext passes the end of the
        // collection, the enumerator is positioned
        // after the last element in the ArrayList
        // and MoveNext returns false.
        while (e.MoveNext()) {
            Object obj1 = e.Current;
            Console.WriteLine(obj1);
        }
    }
}
```

### 输出：

```cs
14
45
78
48
49
51
77
After GetEnumerator(Int32, Int32) Method:
48
49
```

### 例 2：

```cs
// C# code to get an enumerator for a
// range of elements in the ArrayList
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating an ArrayList
        ArrayList myList = new ArrayList();

        // adding elements in myList
        myList.Add("C");
        myList.Add("C++");
        myList.Add("Java");
        myList.Add("Python");
        myList.Add("C#");
        myList.Add("HTML");
        myList.Add("CSS");

        Console.WriteLine("After GetEnumerator(Int32, Int32) Method: ");

        // To get an Enumerator for a range
        // of elements of the ArrayList
        // this will give error as index is
        // less than zero
        IEnumerator e = myList.GetEnumerator(-1, 2);

        // If MoveNext passes the end of the
        // collection, the enumerator is positioned
        // after the last element in the ArrayList
        // and MoveNext returns false.
        while (e.MoveNext()) {
            Object obj1 = e.Current;
            Console.WriteLine(obj1);
        }
    }
}
```

### 运行时错误：

> 未处理异常:
> System.ArgumentOutOfRangeException: 要求非负数。
> 参数名称: index

## 注：

- C# 语言的 `foreach` 语句隐藏了枚举器的复杂性。因此，建议使用 `foreach` ，而不是直接操作枚举器。
- 枚举数可用于读取集合中的数据，但不能用于修改基础集合。
- `Current` 返回相同的对象，直到调用 `MoveNext` 或 `Reset`。`MoveNext` 将 `Current` 设置为下一个元素。
- 只要集合保持不变，枚举数就保持有效。如果对集合进行了更改，例如添加、修改或删除元素，枚举数将无法恢复地失效，并且其行为未定义。
- 这个方法是一个 O(1) 运算。

## 参考：

- [https://docs.microsoft.com/en-us/dotnet/api/system.collections.arraylist.getenumerator?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.arraylist.getenumerator?view=netframework-4.7.2)