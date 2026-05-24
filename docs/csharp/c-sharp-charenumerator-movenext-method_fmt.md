# CharEnumerator.MoveNext() 方法

> 原文：[https://www.geeksforgeeks.org/c-sharp-charenumerator-movenext-method/](https://www.geeksforgeeks.org/c-sharp-charenumerator-movenext-method/)

`CharEnumerator.MoveNext()` 方法用于将当前 `CharEnumerator` 对象的内部索引递增到枚举字符串的下一个字符。

## 语法

```cs
public bool MoveNext();
```

## 返回值

如果索引成功递增并且在枚举字符串内，则该方法返回布尔值 `true`，否则返回 `false`。

下面是说明使用 `CharEnumerator.MoveNext()` 方法的程序。

## 示例

### 示例 1

```cs
// C# program to illustrate the
// use of CharEnumerator.MoveNext()
// Method
using System;

class GFG {

// Driver code
    public static void Main()
    {
        // Initialize a string object
        string str = "A Computer Science Portal for Geeks!";

        // Instantiate a CharEnumerator object
        CharEnumerator chEnum = str.GetEnumerator();

        // Printing the string
        while (chEnum.MoveNext()) 
        {
            Console.Write(chEnum.Current);
        }
    }
}
```

**输出：**

```cs
A Computer Science Portal for Geeks!
```

### 示例 2

```cs
// C# program to illustrate the
// use of CharEnumerator.MoveNext()
// Method
using System;

class GFG {

// Driver code
    public static void Main()
    {
        // Initialize a string object
        string str = "Best Data Structure and Algorithms Tutorials!";

        // Instantiate a CharEnumerator object
        CharEnumerator chEnum = str.GetEnumerator();

        // Printing the string
        while (chEnum.MoveNext()) 
        {
            if (chEnum.Current == ' ') 
            {
                Console.WriteLine();
                continue;
            }
            Console.Write(chEnum.Current);
        }
    }
}
```

**输出：**

```cs
Best
Data
Structure
and
Algorithms
Tutorials!
```

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.charenumerator.movenext?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.charenumerator.movenext?view=netframework-4.7.2)