# C# |获取或设置与排序列表

中指定键相关联的值

> 原文:[https://www . geeksforgeeks . org/c-sharp-get-or-set-value-associated-in-spected-key-sorted list/](https://www.geeksforgeeks.org/c-sharp-get-or-set-the-value-associated-with-specified-key-in-sortedlist/)

**排序列表。项目[对象]属性**用于获取和设置与排序列表对象中特定键相关联的值。

**语法:**

```cs
public virtual object this[object key] { get; set; }
```

这里，键与要获取或设置的值相关联。它属于对象类型。

**返回值:**如果找到了与排序列表对象中的*键*参数相关联的值，则该属性返回空值。

**异常:**

*   **ArgumentNullException:** 如果密钥为空。
*   **NotSupportedException:** 如果设置了属性，而 SortedList 对象是只读的，或者如果设置了属性，则该键不存在于集合中，并且 SortedList 具有固定的大小。
*   **OutOfMemoryException:** 如果没有足够的可用内存将元素添加到 SortedList。
*   **无效操作异常:**如果比较器抛出异常。

以下程序说明了上述属性的使用:

**例 1:**

```cs
// C# code to Gets or sets the value 
// associated with the specified key 
using System; 
using System.Collections; 

class GFG { 

    // Driver code 
    public static void Main() 
    { 

        // Creating a SortedList 
        SortedList mylist = new SortedList(); 

        // Adding elements in SortedList 
        mylist.Add("g", "geeks"); 
        mylist.Add("c", "c++"); 
        mylist.Add("d", "data structures"); 
        mylist.Add("q", "quiz"); 

        // Get a collection of the keys.
        ICollection c = mylist.Keys; 

        // Displaying the contents 
        foreach(string str in c) 
            Console.WriteLine(str + ": " + mylist[str]); 

        // Setting the value associated with key "c" 
        mylist["c"] = "C#"; 

        Console.WriteLine("Updated Values:"); 

        // Displaying the contents 
        foreach(string str in c) 
            Console.WriteLine(str + ": " + mylist[str]); 
    } 
} 
```

**Output:**

```cs
c: c++
d: data structures
g: geeks
q: quiz
Updated Values:
c: C#
d: data structures
g: geeks
q: quiz

```

**例 2:**

```cs
// C# code to Gets or sets the value 
// associated with the specified key 
using System; 
using System.Collections; 

class GFG { 

    // Driver code 
    public static void Main() 
    { 

        // Creating a SortedList 
        SortedList mylist = new SortedList(); 

        // Adding elements in SortedList 
        mylist.Add("4", "Even"); 
        mylist.Add("9", "Odd"); 
        mylist.Add("5", "Odd and Prime"); 
        mylist.Add("2", "Even and Prime"); 

        // Get a collection of the keys.
        ICollection c = mylist.Keys; 

        // Displaying the contents 
        foreach(string str in c) 
            Console.WriteLine(str + ": " + mylist[str]); 

        // Setting the value associated 
        // with key "56" which is not present  
        // will result in the creation of  
        // new key and value will be set which  
        // is given by the user 
        mylist["56"] = "New Value"; 

        Console.WriteLine("Updated Values:"); 

        // Displaying the contents 
        foreach(string str in c) 
            Console.WriteLine(str + ": " + mylist[str]); 

        // Setting the value associated 
        // with key "28" which is not present  
        // will result in the creation of  
        // new key and its value can be null
        mylist["28"] = null; 

        Console.WriteLine("Updated Values:"); 

        // Displaying the contents 
        foreach(string str in c) 
            Console.WriteLine(str + ": " + mylist[str]); 
    } 
} 
```

**Output:**

```cs
2: Even and Prime
4: Even
5: Odd and Prime
9: Odd
Updated Values:
2: Even and Prime
4: Even
5: Odd and Prime
56: New Value
9: Odd
Updated Values:
2: Even and Prime
28: 
4: Even
5: Odd and Prime
56: New Value
9: Odd

```

**注:**

*   此属性返回与特定键关联的值。如果找不到该键，并且有人试图获取该键，则该属性将返回 null，如果试图设置，将导致创建具有指定键的新元素。
*   键不能为空，但值可以为空。若要区分由于找不到指定键而返回的 null 和由于指定键的值为 null 而返回的 null，请使用 Contains 方法或 ContainsKey 方法来确定该键是否存在于列表中。
*   检索该属性的值是一个 O(log n)操作，其中 n 是 Count。如果键已经在排序列表中，则设置属性是一个 O(log n)操作。如果键不在列表中，则设置属性是对未排序数据的 O(n)操作，如果新元素添加在列表末尾，则是 O(log n)。如果插入导致调整大小，操作是 O(n)。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . sorted list . item？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.sortedlist.item?view=netframework-4.7.2)