# Array.GetValue() 方法在 C# 中的应用与示例（第 2 部分）

> 原文：[https://www.geeksforgeeks.org/array-getvalue-method-in-csharp-with-examples-set-2/](https://www.geeksforgeeks.org/array-getvalue-method-in-csharp-with-examples-set-2/)

`Array.GetValue()` 方法用于获取当前数组中指定元素的值。此方法共有 8 个重载，如下所示：

*   `Array.GetValue(Int32, Int32)`
*   `Array.GetValue(Int64, Int64)`
*   `Array.GetValue(Int32)`
*   `Array.GetValue(Int64)`
*   `Array.GetValue(Int32, Int32, Int32)`
*   `Array.GetValue(Int64, Int64, Int64)`
*   `GetValue(Int32[])`
*   `GetValue(Int64[])`

下面，我们来讲解一下 `Array.GetValue(Int32)` 和 `Array.GetValue(Int64)` 方法。

## Array.GetValue(Int32) 方法

`GetValue(Int32)` 方法用于获取一维数组中指定位置的值。索引被指定为 32 位整数。

**语法：**

```cs
public object GetValue (int index);
```

这里，`index` 是表示要获取的数组元素位置的 32 位整数。

**返回值：** 该方法返回 `object` 类型的一维数组中指定位置的值。

**异常：**

*   `ArgumentException`：如果当前数组没有恰好一维。
*   `IndexOutOfRangeException`：如果 `index` 在当前数组的有效索引范围之外。

## Array.GetValue(Int64) 方法

`GetValue(Int64)` 方法用于获取一维数组中指定位置的值。索引被指定为 64 位整数。

**语法：**

```cs
public object GetValue (long index);
```

这里，`index` 是表示要获取的数组元素位置的 64 位整数。

**返回值：** 该方法返回 `object` 类型的一维数组中指定位置的值。

**异常：**

*   `ArgumentException`：如果当前数组没有恰好一维。
*   `IndexOutOfRangeException`：如果 `index` 在当前数组的有效索引范围之外。

## 示例

### 示例 1

```cs
// C# program to demonstrate the
// Array.GetValue(Int32) Method
using System;
public class GFG {

    public static void Main()
    {
        // declare a character array
        char[] arr = new char[]{'A', 'B', 'C', 'D'};

        // use of GetValue(Int32) Method
        Console.WriteLine("element at index 3 is : " + arr.GetValue(3));
        Console.WriteLine("element at index 1 is : " + arr.GetValue(1));
        Console.WriteLine("element at index 2 is : " + arr.GetValue(2));
        Console.WriteLine("element at index 0 is : " + arr.GetValue(0));
    }
}
```

**输出：**

```cs
element at index 3 is : D
element at index 1 is : B
element at index 2 is : C
element at index 0 is : A
```

### 示例 2

```cs
// C# program to demonstrate the
// Array.GetValue(Int64) Method
using System;
public class GFG {

    public static void Main()
    {
        // declare a string array
        string[] arr = new string[5];

        // use "SetValue()" method to set
        // the value at specified index
        arr.SetValue( "C++", 0 );
        arr.SetValue( "Java", 1 );
        arr.SetValue( "C#", 2 );
        arr.SetValue( "Perl", 3 );
        arr.SetValue( "Python", 4 );

        // Using GetValue(Int32) Method
        Console.WriteLine("element at index 3 is : " + arr.GetValue(3));
        Console.WriteLine("element at index 1 is : " + arr.GetValue(1));
        Console.WriteLine("element at index 2 is : " + arr.GetValue(2));
        Console.WriteLine("element at index 0 is : " + arr.GetValue(0));
        Console.WriteLine("element at index 0 is : " + arr.GetValue(4));
    }
}
```

**输出：**

```cs
element at index 3 is : Perl
element at index 1 is : Java
element at index 2 is : C#
element at index 0 is : C++
element at index 0 is : Python
```

**注意：** 对于在线编译器，不能使用 32 位或 64 位整数。对 32 或 64 位整数请使用离线编译器。