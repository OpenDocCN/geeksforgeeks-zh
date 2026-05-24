# 如何在 C# 中创建哈希表的浅拷贝

> 原文:[https://www . geeksforgeeks . org/如何创建 c-sharp 中哈希表的浅拷贝/](https://www.geeksforgeeks.org/how-to-create-a-shallow-copy-of-hashtable-in-c-sharp/)

**哈希表。克隆方法**用于创建哈希表的浅拷贝。当我们制作一个[浅拷贝](https://www.geeksforgeeks.org/shallow-copy-and-deep-copy-in-c-sharp/)时，不管其类型如何，只有集合的元素被拷贝，它不拷贝引用所引用的对象。基本上，它创建一个新对象，该对象指向原始引用。

**语法:**

```cs
HashtableName.Clone();
```

下面的例子说明了这种方法的使用。

**示例 1:** 创建一个哈希表类类型的对象 H1，它是在系统中预定义的。集合命名空间。然后我们使用哈希表添加类型字符串的键和值。添加方法。Hashtable.clone 方法用于创建 H1 的浅拷贝。我们使用 foreach 循环来显示浅层 H1 的元素。DictionaryEntry 属性用于设置或获取键的值，值按对排序。

```cs
// C# Program to demonstrate
// the Hashtable.Clone Method
using System;
using System.Collections;

namespace hashtable {

class GFG {

    // Main Method
    public static void Main(string[] args)
    {
        // Declaring a Hashtable named H1
        // Calls the default constructor
        Hashtable H1 = new Hashtable();

        // Adding keys and values
        // to the hashtable
        H1.Add("1", "This");
        H1.Add("2", "is");
        H1.Add("3", "a");
        H1.Add("4", "Hash");
        H1.Add("5", "Table");

        // Creating a shallow copy of H1
        Hashtable ShallowH1 = new Hashtable();
        ShallowH1 = (Hashtable)H1.Clone();

        // Displaying values of key, value pairs
        // Using DictionaryEntry which is predefined
        foreach(DictionaryEntry item in ShallowH1)
        {
            Console.WriteLine("Key " + item.Key + 
                         " Value " + item.Value);
        }
    }
}
}
```

**输出:**

```cs
Key 5 Value Table
Key 1 Value This
Key 4 Value Hash
Key 3 Value a
Key 2 Value is

```