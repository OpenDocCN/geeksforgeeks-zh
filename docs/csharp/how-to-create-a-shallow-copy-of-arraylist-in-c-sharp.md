# 如何在 C# 中创建数组列表的浅拷贝

> 原文:[https://www . geeksforgeeks . org/如何创建 c-sharp 中数组列表的浅拷贝/](https://www.geeksforgeeks.org/how-to-create-a-shallow-copy-of-arraylist-in-c-sharp/)

**数组列表。克隆()方法**用于创建指定的[数组列表](https://www.geeksforgeeks.org/c-sharp-arraylist-class/)的浅拷贝。集合的浅层副本仅复制集合的元素，而不考虑引用类型或值类型。但是它不会复制引用所引用的对象。新集合中的引用指向与原始集合中的引用指向的对象相同的对象。

**语法:**

```cs
public virtual object Clone ();
```

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# code to illustrate the use 
// of ArrayList.Clone Method
using System;
using System.Collections;

public class GFG {

    // Main Method
    public static void Main(String[] args)
    {

        // Creating an empty ArrayList
        ArrayList list = new ArrayList();

        // Use Add() method
        // to Add elements 
        // in the list
        list.Add("Geeks");
        list.Add("for");
        list.Add("Geeks");
        list.Add("10");
        list.Add("20");

        // Displaying the list
        Console.WriteLine("Elements of Original ArrayList: \n");

        // Displaying the elements in ArrayList
        foreach(string str in list)
        {
            Console.WriteLine(str);
        }

        // Creating another ArrayList
        ArrayList sec_list = new ArrayList();

        // using Clone() Method
        sec_list = (ArrayList)list.Clone();

        // Displaying the Cloned ArrayList
        Console.WriteLine("\nElements of Cloned ArrayList: \n");

        // Displaying the elements in ArrayList
        foreach(string str1 in sec_list)
        {
            Console.WriteLine(str1);
        }
    }
}
```

**输出:**

```cs
Elements of Original ArrayList: 

Geeks
for
Geeks
10
20

Elements of Cloned ArrayList: 

Geeks
for
Geeks
10
20

```