# C# |获取数组列表中一系列元素的枚举数

> 原文:[https://www . geeksforgeeks . org/c-sharp-get-enumerator-for-range-of-in-ArrayList 元素/](https://www.geeksforgeeks.org/c-sharp-getting-an-enumerator-for-a-range-of-elements-in-the-arraylist/)

**数组列表。GetEnumerator(Int32，Int32)方法**用于获取 ***[数组列表](https://www.geeksforgeeks.org/c-arraylist-class/)*** 中一系列元素的枚举数。

**语法:**

> 公共虚拟系统。集合。IEnumerator GetEnumerator(int index，int count)；

**参数:**

> **索引:**是数组列表节的 Int32 类型的从零开始的索引，枚举器应该引用它。
> 
> **计数:**是数组列表部分中枚举器应该引用的 Int32 类型的元素数。

**返回值:**该方法为数组列表中指定范围的元素返回一个 IEnumerator。

**异常:**

*   **argumentoutofrangerexception:**如果*指数*或*计数*小于零。
*   **参数异常:**如果*索引*和*计数*没有在数组列表中指定有效范围。

以下程序说明了上述方法的使用:

**例 1:**

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

**输出:**

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

**例 2:**

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

**运行时错误:**

> 未处理异常:
> 系统。ArgumentOutOfRangeException:要求非负数。
> 参数名称:索引

**注:**

*   C# 语言的 *foreach* 语句隐藏了枚举器的复杂性。因此，建议使用 *foreach* ，而不是直接操作枚举器。
*   枚举数可用于读取集合中的数据，但不能用于修改基础集合。
*   *当前*返回相同的对象，直到调用*移动下一个*或重置。*移动下一个*将当前设置为下一个元素。
*   只要集合保持不变，枚举数就保持有效。如果对集合进行了更改，例如添加、修改或删除元素，枚举数将无法恢复地失效，并且其行为未定义。
*   这个方法是一个 O(1)运算。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . ArrayList . getenumerator？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.arraylist.getenumerator?view=netframework-4.7.2)