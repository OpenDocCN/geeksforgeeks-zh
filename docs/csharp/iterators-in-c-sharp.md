# c# 中的迭代器

> 原文:[https://www.geeksforgeeks.org/iterators-in-c-sharp/](https://www.geeksforgeeks.org/iterators-in-c-sharp/)

迭代器是 C# 中的一种方法，用于数组或集合，如列表等。逐个检索元素。或者换句话说，我们可以说迭代器用于对集合执行迭代。该功能在 ***C# 2.0*** 中介绍。它使用 **yield return** 语句一次从集合中返回元素，并且它总是记住迭代器的当前位置，所以当下一次迭代发生时，它将返回给定集合的下一个元素。如果您想要停止迭代，您将使用**屈服中断**语句。

这个方法的返回类型是 IEnumerable、IEnumerable <t>、IEnumerator 或 IEnumerator <t>。这意味着通过使用迭代器编译器将自动为您创建 IEnumerable 或 IEnumerator 接口，不需要在您的类中实现 IEnumerable 或 IEnumerator 接口来使用 foreach 循环。当编译器在你的类中识别出一个迭代器时，它会自动创建当前的，移动下一个，并释放 IEnumerable 或 IEnumerator 接口的方法。</t></t>

**要点:**

*   迭代器可以用作方法，也可以用作属性。
*   迭代器方法也称为 get 访问器。
*   您可以将迭代器用作方法或 get 访问器。
*   不能在事件实例构造函数、静态构造函数或静态终结器中使用迭代器。
*   迭代器方法不包含 ref 或 [out](https://www.geeksforgeeks.org/out-parameter-with-examples-in-c-sharp/) 参数。
*   这里，yield 不是保留字，但当你用 yield 搭配 return 或 break 语句时，那么 yield 就有了特殊的含义。
*   您可以使用多个收益率报表。
*   它通常用于泛型或非泛型集合。
*   当您使用迭代器时，有必要添加系统。集合。程序中的通用命名空间。

**例 1:**

## C#

```cs
// C# program to illustrate the concept
// of iterator using list collection
using System;
using System.Collections.Generic;

 class GFG {

    public static IEnumerable<string> GetMyList()
    {
        // Creating and adding elements in list
        List<string> my_list = new List<string>() {
                     "Cat", "Goat", "Dog", "Cow" };

        // Iterating the elements of my_list
        foreach(var items in my_list)
        {
            // Returning the element after every iteration
            yield return items;
        }
    }

    // Main Method
    static public void Main()
    {

        // Storing the elements of GetMyList
        IEnumerable<string> my_slist = GetMyList();

        // Display the elements return from iteration
        foreach(var i in my_slist)
        {
            Console.WriteLine(i);
        }
    }
}
```

**Output:** 

```cs
Cat
Goat
Dog
Cow
```

**例 2:**

## C#

```cs
// C# program to illustrate the concept
// of iterator using array
using System;
using System.Collections.Generic;

class GFG {

    public static IEnumerable<string> GetMyArray()
    {
        string[] myarray = new string[] {"Geeks",
                        "geeks123", "1234geeks"};

        // Iterating the elements of myarray
        foreach(var items in myarray)
        {

            // Returning the element after every iteration
            yield return items.ToString();
        }
    }

    // Main Method
    static public void Main()
    {

        // Storing the elements of GetMyArray
        IEnumerable<string> myitems = GetMyArray();

        // Display the elements return from iteration
        foreach(var i in myitems)
        {
            Console.WriteLine(i);
        }
    }
}
```

**Output:** 

```cs
Geeks
geeks123
1234geeks
```