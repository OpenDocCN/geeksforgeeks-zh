# 如何在 C# | List 中对列表进行排序。排序()方法集-2

> 原文:[https://www . geesforgeks . org/how-sort-a-list-in-c-sharp-list-sort-method-set-2/](https://www.geeksforgeeks.org/how-to-sort-a-list-in-c-sharp-list-sort-method-set-2/)

**列表< T >。Sort()方法**用于使用指定或默认的 IComparer < T >实现或提供的比较< T >委托来比较列表元素，从而对列表中的元素或部分元素进行排序。该方法的重载列表中共有 4 种方法如下:

***   [排序(IComparer < T > )](https://www.geeksforgeeks.org/how-to-sort-list-in-c-sharp-set-1/# m1)T10[排序(Int32，Int32，IComparer<t>)</t>](https://www.geeksforgeeks.org/how-to-sort-list-in-c-sharp-set-1/# m2)*   [sort ()](# m3)*   [sort (compare < t >)](# m4)T24**

**这里前两种方法在 **[集合–1](https://www.geeksforgeeks.org/how-to-sort-list-in-c-sharp-set-1/)**中讨论。所以，我们将讨论最后两种方法。**

##### **排序()方法**

**此方法用于使用默认比较器对整个列表<t>中的元素进行排序。</t>**

> ****语法:**public void Sort()；**
> 
> ****异常:**如果默认*比较器*找不到 IComparable < T >泛型接口或 T 类型的 IComparable 接口的实现，此方法将给出***invalid operationexception*****

****例 1:****

```cs
// C# program to demonstrate the 
// use of List<T>.Sort() method
using System;
using System.Collections.Generic;

class GFG {

    // Main Method
    public static void Main()
    {

        // List initialize
        List<int> list1 = new List<int> {

            // list elements
            1, 5, 6, 2, 4, 3

        };

        Console.WriteLine("Original List");

        foreach(int g in list1)
        {

            // Display Original List
            Console.WriteLine(g);
        }

        Console.WriteLine("\nSorted List");

        // use of List<T>.Sort() method
        list1.Sort();

        foreach(int g in list1)
        {

            // Display sorted list
            Console.WriteLine(g);
        }
    }
}
```

****输出:**

```cs
Original List
1
5
6
2
4
3

Sorted List
1
2
3
4
5
6

```

**例 2:**

```cs
// C# program to demonstrate the 
// use of List<T>.Sort() method
using System;
using System.Collections.Generic;

class GFG {

    // Main Method
    public static void Main()
    {
        List<string> list1 = new List<string>();

        // list elements
        list1.Add("A");
        list1.Add("I");
        list1.Add("G");
        list1.Add("B");
        list1.Add("E");
        list1.Add("H");
        list1.Add("F");
        list1.Add("C");
        list1.Add("D");

        Console.WriteLine("Original List");

        // Display Original List
        Display(list1);

        Console.WriteLine("\nSorted List");

        // use of List.Sort() method
        list1.Sort();

        // Display sorted List
        Display(list1);
    }

    // Display function
    public static void Display(List<string> list)
    {
        foreach(string g in list)
        {
            Console.Write(g + " ");
        }
    }
}
```

**输出:**

```cs
Original List
A I G B E H F C D 
Sorted List
A B C D E F G H I

```

**例 3:**

```cs
// C# program to demonstrate the
// use of List<T>.Sort() method
using System;
using System.Collections.Generic;

public class GFG {

    // Main Method
    public static void Main()
    {
        // array elements
        String[] list = {"C++", "Java", "C",
                    "Python", "HTML", "CSS",
                    "Scala", "Ruby", "Perl"};

        var list1 = new List<String>();

        // "AddRange" method to add the
        // string array elements into the List
        list1.AddRange(list);

        Console.WriteLine("List in unsorted order: ");
        Display(list1);

        Console.WriteLine(Environment.NewLine);

        // using List.Sort() method
        list1.Sort();

        Console.WriteLine("List in sorted order: ");
        Display(list1);
    }

    // Display method
    static void Display(List<string> list)
    {
        foreach(string g in list)
        {
            Console.Write(g + "\t");
        }
    }
}
```

**输出:**

```cs
List in unsorted order: 
C++    Java    C    Python    HTML    CSS    Scala    Ruby    Perl    

List in sorted order: 
C    C++    CSS    HTML    Java    Perl    Python    Ruby    Scala

```**