# C# | CharEnumerator.GetType()方法

> 原文：[https://www.geeksforgeeks.org/c-sharp-charenumerator-gettype-method/](https://www.geeksforgeeks.org/c-sharp-charenumerator-gettype-method/)

## 方法介绍

`CharEnumerator.GetType()`方法用于获取当前实例的类型。此方法继承自`Object`类。

## 语法

```cs
public Type GetType();
```

## 返回值

此方法返回当前实例的确切运行时类型。

## 示例

下面是说明使用`CharEnumerator.GetType()`方法的程序。

### 例 1

```cs
// C# program to illustrate the
// use of CharEnumerator.GetType()
// Method
using System;

class GFG {

// Driver code
    public static void Main()
    {
        // Initialize a string object
        string str = "GeeksforGeeks is Awesome!";

        // Instantiate a CharEnumerator object
        CharEnumerator chEnum = str.GetEnumerator();

        // Printing the Type of
        // the CharEnumerator objects
        Console.WriteLine(chEnum.GetType());
    }
}
```

**Output:**

```cs
System.CharEnumerator
```

### 例 2

```cs
// C# program to illustrate the
// use of CharEnumerator.GetType()
// Method
using System;

class GFG {

// Driver code
    public static void Main()
    {
        // Initialize a string object
        string str = "GeeksforGeeks is fun";

        // Instantiate a CharEnumerator object
        CharEnumerator chEnum = str.GetEnumerator();

        // Instantiate a clone of CharEnumerator object
        CharEnumerator chEnumClone = (CharEnumerator)chEnum.Clone();

        // Printing the Type of the
        // CharEnumerator objects and its clone
        Console.WriteLine("Type of CharEnumerator object: "
                         + chEnum.GetType());

        Console.WriteLine("Type of CharEnumerator clone object: "
                         + chEnumClone.GetType());
    }
}
```

**Output:**

```cs
Type of CharEnumerator object: System.CharEnumerator
Type of CharEnumerator clone object: System.CharEnumerator
```