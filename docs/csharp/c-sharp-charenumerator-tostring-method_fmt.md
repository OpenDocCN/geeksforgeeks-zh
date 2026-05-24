# C# | CharEnumerator.ToString()方法

> 原文：[https://www.geeksforgeeks.org/c-sharp-charenumerator-tostring-method/](https://www.geeksforgeeks.org/c-sharp-charenumerator-tostring-method/)

`CharEnumerator.ToString()`方法用于获取表示当前对象的字符串。它继承自[`Object`](https://www.geeksforgeeks.org/c-sharp-object-class/)类。

## 语法

```cs
public virtual string ToString();
```

## 返回值

这个方法返回一个代表当前`CharEnumerator`对象的字符串。

下面是说明使用`CharEnumerator.ToString()`方法的程序。

### 例 1

```cs
// C# program to illustrate the
// use of CharEnumerator.ToString()
// Method
using System;

class GFG {

// Driver code
    public static void Main()
    {
        // Initialize a string object
        string str = "GeeksforGeeks is Awesome!!";

        // Instantiate a CharEnumerator object
        CharEnumerator chEnum = str.GetEnumerator();

        // Printing the Type of
        // the CharEnumerator objects
        Console.WriteLine(chEnum.ToString().GetType());
    }
}
```

**Output:**

```cs
System.String
```

### 例 2

```cs
// C# program to illustrate the
// use of CharEnumerator.ToString()
// Method
using System;

class GFG {

// Driver code
    public static void Main()
    {
        // Initialize a string object
        string str = "GeeksforGeeks Ranking - 50!";

        // Instantiate a CharEnumerator object
        CharEnumerator chEnum = str.GetEnumerator();

        // Instantiate a clone of CharEnumerator object
        CharEnumerator chEnumClone = (CharEnumerator)chEnum.Clone();

        // Printing the Type of the
        // CharEnumerator objects
        // and its clone
        Console.WriteLine("Type of CharEnumerator Object: " +
                                 chEnum.ToString().GetType());

        Console.WriteLine("Type of CharEnumerator clone Object: " +
                                 chEnumClone.ToString().GetType());
    }
}
```

**Output:**

```cs
Type of CharEnumerator Object: System.String
Type of CharEnumerator clone Object: System.String
```