# C# |将数组列表的元素复制到新数组中

> 原文：[https://www.geeksforgeeks.org/c-sharp-copying-the-elements-of-arraylist-to-a-new-array/](https://www.geeksforgeeks.org/c-sharp-copying-the-elements-of-arraylist-to-a-new-array/)

`ArrayList.ToArray()`方法用于将[数组列表](https://www.geeksforgeeks.org/c-arraylist-class/)的元素复制到一个新数组中。该方法在其重载列表中包含两个方法，如下所示：

1.  `ToArray()`
2.  `ToArray(Type)`

## `ToArray()`

该方法用于将数组列表的元素复制到新的`object[]`数组中。使用`Array.Copy`，为 O(n)运算，其中 n 为`Count`。

**语法：**

```cs
public virtual object[] ToArray ();
```

**返回值：** 这个方法将返回一个包含数组列表元素副本的`object[]`数组。

**例：**

```cs
// C# program to illustrate ToArray() Method
using System;
using System.Collections;

class GFG {

    // Main Method
    public static void Main()
    {

        // Create and initializing ArrayList
        ArrayList mylist = new ArrayList(5);

        mylist.Add("G");
        mylist.Add("E");
        mylist.Add("E");
        mylist.Add("K");
        mylist.Add("S");

        // Copy the data of Arraylist into
        // the object Array Using ToArray()
        // method
        object[] str2 = mylist.ToArray();

        foreach(string i in str2)
        {
            Console.WriteLine(i);
        }
    }
}
```

**Output：**

```cs
G
E
E
K
S
```

## `ToArray(Type)`

此方法用于将数组列表的元素复制到指定元素类型的*新数组中。使用`Array.Copy`，为 O(n)运算，其中 n 为`Count`。

**语法：**

```cs
public virtual Array ToArray (Type t);
```

这里，`t`是要创建和复制元素的目标数组的元素类型。

**返回值：** 这个方法将返回一个指定元素类型的数组，包含数组列表元素的副本。

**异常：**

*   如果`t`的值为空，则该方法将给出`ArgumentNullException`。
*   如果源数组列表的类型不能自动转换为指定的类型，则此方法将给出`InvalidCastException`。

**注意：** 数组列表对象中的所有对象将被转换为`Type`参数中指定的类型。

**例：**

```cs
// C# program to illustrate ToArray(Type) Method
using System;
using System.Collections;

class GFG {

    // Main Method
    public static void Main()
    {

        // Create and initialize new array
        ArrayList mylist = new ArrayList(5);
        mylist.Add("G");
        mylist.Add("E");
        mylist.Add("E");
        mylist.Add("K");
        mylist.Add("S");

        // Copy the data of Arraylist into
        // the string Array Using
        // ToArray(Type) method
        string[] str2 = (string[])mylist.ToArray(typeof(string));

        // Display the data of str2 string
        foreach(string i in str2)
        {
            Console.WriteLine(i);
        }
    }
}
```

**Output：**

```cs
G
E
E
K
S
```

**参考：**

*   [https://docs.microsoft.com/en-us/dotnet/api/system.collections.arraylist.toarray?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.arraylist.toarray?view=netframework-4.7.2)