# 在 C# 中将字符数组转换为字符串的不同方式

> 原文:[https://www . geesforgeks . org/different-way-to-convert-char-array-to-string-in-c-sharp/](https://www.geeksforgeeks.org/different-ways-to-convert-char-array-to-string-in-c-sharp/)

我们已经给出了一个字符数组 **arr** ，任务是将字符数组转换为 C# 中的字符串 **str** 。

```cs
Input: arr = [s, t, r, i, n, g]  
Output: string

Input: arr = [G, e, e, k, s, F, o, r, G, e, e, k, s]
Output: GeeksForGeeks

```

为了完成这个任务，我们有以下方法:

### **方法一:**

**使用** [**字符串**](https://www.geeksforgeeks.org/c-sharp-string/) **()** **方法:****字符串**类有几个重载的构造函数，它们接受一个字符或字节数组。因此它可以用来 从字符数组中创建一个新的字符串。

**语法:**

```cs
string str = new string(character_array);

```

**示例:**

## C#

```cs
// C# program to convert the
// char array to string
using System;
using System.Text;

public class GFG{

    static string getString(char[] arr) 
    {
        // string() is a used to 
        // convert the char array
        // to string
        string s = new string(arr);

        return s;
    }

    static void Main(string[] args)
    {
        // given character array
        char[] arr = {'G', 'e', 'e', 'k', 
        's', 'F', 'o', 'r', 'G', 'e',
        'e', 'k', 's'};

        // function calling
        string str = getString(arr);

        // printing output
        Console.WriteLine(str);

    }
}
```

**输出:**

```cs
GeeksForGeeks

```

### **方法二:**

**使用**[***Join()***](https://www.geeksforgeeks.org/c-sharp-join-method-set-1/)**方法:**此方法用于连接集合的成员或指定数组的元素，在每个成员或元素之间使用指定的分隔符。因此它可以用来 从字符数组中创建一个新的字符串。

**语法:**

```cs
string str = string.Join("", character_array);

```

**示例:**

## C#

```cs
// C# program to convert the
// char array to string
using System;
using System.Text;

public class GFG{

    static string getString(char[] arr) 
    {
        // String.Join() is a used to 
        // convert the char array
        // to string
        string s = string.Join("", arr);

        return s;
    }

    static void Main(string[] args)
    {
        // given character array
        char[] arr = {'G', 'e', 'e', 'k', 
        's', 'F', 'o', 'r', 'G', 'e',
        'e', 'k', 's'};

        // function calling
        string str = getString(arr);

        // printing output
        Console.WriteLine(str);

    }
}
```

**输出:**

```cs
GeeksForGeeks

```

### **方法三:**

**使用**[***Concat()***](https://www.geeksforgeeks.org/c-sharp-string-concat-with-examples-set-3/)**方法:**此方法用于连接一个或多个字符串实例或一个或多个对象实例的值的字符串表示。因此它可以用来 从字符数组中创建一个新的字符串。

**语法:**

```cs
string str = string.Concat(character_array);

```

**示例:**

## C#

```cs
// C# program to convert the
// char array to string
using System;
using System.Text;

public class GFG{

    static string getString(char[] arr) 
    {
        // String.Concat() is a used to 
        // convert the char array
        // to string
        string s = string.Concat(arr);

        return s;
    }

    static void Main(string[] args)
    {
        // given character array
        char[] arr = {'G', 'e', 'e', 'k', 
        's', 'F', 'o', 'r', 'G', 'e',
        'e', 'k', 's'};

        // function calling
        string str = getString(arr);

        // printing output
        Console.WriteLine(str);

    }
}
```

**输出:**

```cs
GeeksForGeeks

```