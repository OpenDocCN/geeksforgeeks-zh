# 阵列。C# 中方法的最后一个索引|集合–1

> 原文:[https://www . geesforgeks . org/array-last indexof-method-in-c-sharp-set-1/](https://www.geeksforgeeks.org/array-lastindexof-method-in-c-sharp-set-1/)

**阵列。LastIndexOf** 方法用于查找一维数组中的最后一个匹配元素。它从数组的最后一个元素开始搜索。它返回包含指定值的元素的索引。此方法的重载列表中有 6 种方法，如下所示:

*   **最后索引（数组、对象）**
*   **最后一个索引(数组，对象，Int32)**
*   **LastIndexOf(数组，对象，Int32，Int32)**
*   **最后一个指数< T > (T[]，T)**
*   **最后一个索引< T > (T[]，T，Int32)**
*   **最后一个< T > (T[]，T，Int32，Int32)**

这里我们只讨论前三种方法。

#### LastIndexOf（Array， Object）

此方法搜索指定的对象，并返回整个一维数组中最后一个匹配项的索引。

> **语法:**公共静态 int LastIndexOf (Array arr，对象值)；
> 
> **参数:**
> **arr** :搜索的是一维数组。
> **值**:是数组中要定位的对象。

**返回值:**如果找到了*值*的索引，则该方法返回该*值*在整个数组中最后一次出现的索引。如果没有找到，那么数组的下限减 1。

**异常:**

*   **参数空异常:**如果数组 **arr** 为空。
*   **rankeexception:**如果数组 **arr** 是多维的。

**例 1:**

```cs
// C# program to demonstrate the 
// Array.LastIndexOf(Array, 
// Object) method
using System;

class GFG {

    static void Main()
    {
        int[] arr = {1, 2, 6, 8, 6, 2};

        // search for "6" from end of the array
        // returns index 4
        int indx1 = Array.LastIndexOf(arr, 6);

        Console.WriteLine("First Index of 6 search"+
                     " from end found at " + indx1);

        // search for "2" from end of the array
        // returns index 5
        int indx2 = Array.LastIndexOf(arr, 2);

        // when the object is found then 
        // the search will stop searching
        Console.WriteLine("First Index of 2 search "+
                       "from end found at " + indx2);       
    }
}
```

**Output:**

```cs
First Index of 6 search from end found at 4
First Index of 2 search from end found at 5

```

**例 2:**

```cs
// C# program to demonstrate the 
// Array.LastIndexOf(Array, 
// Object) method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        // creating a array of type Array
        Array arr = Array.CreateInstance(typeof(String), 8);

        // 0, 1, 2, 3, 4, 5, 6, 7 are 
        // the indexes of the elements
        arr.SetValue("java", 0);
        arr.SetValue("C#", 1);
        arr.SetValue("C++", 2);
        arr.SetValue("C", 3);
        arr.SetValue("Python", 4);
        arr.SetValue("C#", 5);
        arr.SetValue("C++", 6);
        arr.SetValue("Ruby", 7);

        String s1 = "C#";
        int index1 = Array.LastIndexOf(arr, s1);

        Console.WriteLine("First Index of C# search"+
                     " from end found at " + index1);

        String s2 = "C++";
        int index2 = Array.LastIndexOf(arr, s2);

        Console.WriteLine("First Index of C++ search"+
                     " from end found at " + index2);
    }
}
```

**Output:**

```cs
First Index of C# search from end found at 5
First Index of C++ search from end found at 6

```

#### LastIndexOf（Array， Object， Int32）

此方法搜索指定的对象，并返回一维数组中从第一个元素延伸到指定索引的元素范围内最后一个匹配项的索引。

> **语法:**公共静态 int LastIndexOf (Array arr，对象值，int start)；
> 
> **参数:**
> **arr:** 搜索的是一维数组。
> **值:**是*阵*中要定位的对象。
> **start:** 是后向搜索的起始索引。

**返回值:**如果找到了*值*的索引，则该方法返回从第一个元素开始延伸的数组**arr**中元素范围内该*值*最后一次出现的索引。如果没有找到，那么数组的下限减 1。

**异常:**

*   **参数空异常:**如果数组 **arr** 为空。
*   **rankeexception:**如果数组 **arr** 是多维的。
*   **argumentoutofrangerexception:**如果**“开始”**索引在数组的有效索引范围之外。

**例 1:**

```cs
// C# program to demonstrate the 
// Array.LastIndexOf(Array, Object,
// Int32) method
using System;

class GFG {

    static void Main()
    {
        int[] arr = {1, 2, 6, 8, 6, 2};

        // search for "6"
        // search start from index 3
        // so returns index 2
        int indx1 = Array.LastIndexOf(arr, 6, 3);

        Console.WriteLine("First Index of 6 search "+
                   "from index 3 found at " + indx1);

         // search for "2"
         // search start from index 2
        // so returns index 1
        int indx2 = Array.LastIndexOf(arr, 2, 2);

        Console.WriteLine("First Index of 2 search "+
                   "from index 2 found at " + indx2);
    }
}
```

**Output:**

```cs
First Index of 6 search from index 3 found at 2
First Index of 2 search from index 2 found at 1

```

**例 2:**

```cs
// C# program to demonstrate the 
// Array.LastIndexOf(Array, Object, 
// Int32) method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        // creating a array of type Array
        Array arr = Array.CreateInstance(typeof(String), 8);

        // 0, 1, 2, 3, 4, 5, 6, 7 are the
        // indexes of the elements
        arr.SetValue("java", 0);
        arr.SetValue("C#", 1);
        arr.SetValue("C++", 2);
        arr.SetValue("C", 3);
        arr.SetValue("Python", 4);
        arr.SetValue("C#", 5);
        arr.SetValue("C++", 6);
        arr.SetValue("Ruby", 7);

        String s1 = "C#";

        // the search start from index 4
        // so returns index 1
        int index1 = Array.LastIndexOf(arr, s1, 4);

        Console.WriteLine("First Index of C# search "+
                   "from index 4 found at " + index1);

        String s2 = "C++";

        // the search start from index 4
        // so returns index 2
        int index2 = Array.LastIndexOf(arr, s2, 3);

        Console.WriteLine("First Index of C++ search"+
                  " from index 3 found at " + index2);
    }
}
```

**Output:**

```cs
First Index of C# search from index 4 found at 1
First Index of C++ search from index 3 found at 2

```

#### LastIndexOf（Array， Object， Int32， Int32）

此方法搜索指定的对象，并返回一维数组中元素范围内最后一个匹配项的索引，该一维数组包含指定数量的元素，并在指定的索引处结束。

> **语法:**公共静态 int LastIndexOf (Array arr，对象值，int start，int count)；
> 
> **参数:**
> **arr** :搜索的是一维数组。
> **值**:是数组中要定位的对象。
> **开始**:是搜索的开始索引。
> **计数**:是要搜索的部分的元素个数。

**返回值:**如果找到了*值*的索引，则该方法返回数组**【arr】**中包含**【count】**中指定元素数量的元素范围内该*值*最后一次出现的索引，并在**【start】**索引处结束。如果没有找到，那么数组的下限减 1。

**异常:**

*   **参数空异常:**如果数组 **arr** 为空。
*   **rankeexception:**如果数组 **arr** 是多维的。
*   **argumentoutofrangerexception:**如果**“开始”**索引在数组的有效索引范围之外，或者**“计数”**小于零，或者**“开始”**索引和计数没有在数组中指定有效的部分。

**例 1:**

```cs
// C# program to demonstrate the 
// Array.LastIndexOf(Array, 
// Object, Int32, Int32) method
using System;

class GFG {

    // Main Method
    static void Main()
    {
        int[] arr = {1, 5, 6, 2, 6, 8, 2};

        // search for "6"
        // search start from index 5 and
        // searches 2 indexes backward from index 5
        // at first index 4 is comes where the value is 6
        // so returns index 4
        int indx1 = Array.LastIndexOf(arr, 6, 5, 2);

        Console.WriteLine("First Index of 6 search from"+
                           " index 5 found at " + indx1);

        // search for "2"
        // search start from index 4 and
        // searches 2 indexes backward from index 4
        // at first index 3 is comes where the value is 2
        // so returns index 3
        int indx2 = Array.LastIndexOf(arr, 2, 4, 2);

        Console.WriteLine("First Index of 2 search from"+
                           " index 4 found at " + indx2);
    }
}
```

**Output:**

```cs
First Index of 6 search from index 5 found at 4
First Index of 2 search from index 4 found at 3

```

**例 2:**

```cs
// C# program to demonstrate the 
// Array.LastIndexOf(Array, Object,
// Int32, Int32) method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        // creating a array of type Array
        Array arr = Array.CreateInstance(typeof(String), 8);

        // 0, 1, 2, 3, 4, 5, 6, 7 are the 
        // indexes of the elements
        arr.SetValue("java", 0);
        arr.SetValue("C#", 1);
        arr.SetValue("C++", 2);
        arr.SetValue("C", 3);
        arr.SetValue("C++", 4);
        arr.SetValue("C#", 5);
        arr.SetValue("Python", 6);
        arr.SetValue("Ruby", 7);

        String s1 = "C#";

        // search for "C#"
        // search start from index 6 and
        // searches 3 indexes backward from index 6
        // at first index 5 is comes where the value is "C#"
        // so returns index 5
        int index1 = Array.LastIndexOf(arr, s1, 6, 3);

        Console.WriteLine("First Index of C# search from"+
                           " index 6 found at " + index1);

        String s2 = "C++";

        // search for "C++"
        // search start from index 5 and
        // searches 3 indexes backward from index 5
        // at first index 4 is comes where the value is "C++"
        // so returns index 4
        int index2 = Array.LastIndexOf(arr, s2, 5, 3);

        Console.WriteLine("First Index of C++ search from"+
                            " index 5 found at " + index2);
    }
}
```

**Output:**

```cs
First Index of C# search from index 6 found at 5
First Index of C++ search from index 5 found at 4

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . array . last indexof？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.array.lastindexof?view=netframework-4.7.2)