# 阵列。C# 中的 GetValue()方法，带示例| Set–2

> 原文:[https://www . geesforgeks . org/array-getvalue-method-in-csharp-with-examples-set-2/](https://www.geeksforgeeks.org/array-getvalue-method-in-csharp-with-examples-set-2/)

数组。C# 中的 GetValue()方法用于获取当前[数组](https://www.geeksforgeeks.org/c-sharp-arrays/)中指定元素的值。本法过载列表共 8 法，如下:

***   阵。GetValue（Int32，Int32）*   数组。GetValue（Int64，Int64）*   数组。GetValue（Int32）*   数组。GetValue（Int64）*   数组。GetValue（Int32，Int32，Int32）*   数组。GetValue（Int64，Int64，Int64）*   GetValue（Int32[]）*   GetValue（Int64[]）**

下面，我们来讲解一下**数组。GetValue(Int32)** 和**数组。GetValue(Int64)方法**。

**GetValue(Int32)** 方法用于获取一维数组中指定位置的值。索引被指定为 32 位整数。

**语法:**

```cs
public object GetValue (int index);
```

这里，*索引*是表示要获取的数组元素位置的 32 位整数。

**返回:**该方法返回对象类型的一维数组中指定位置的值。

**异常:**

*   **参数异常:**如果当前数组没有恰好一维。
*   **indexoutofrangerexception:**如果索引在当前数组的有效索引范围之外。

**GetValue(Int64)** 方法用于获取一维数组中指定位置的值。索引被指定为 64 位整数。

**语法:**

```cs
public object GetValue (long index);
```

这里，*索引*是表示要获取的数组元素位置的 64 位整数。

**返回:**该方法返回对象类型的一维数组中指定位置的值。

**异常:**

*   **参数异常:**如果当前数组没有恰好一维。
*   **indexoutofrangerexception:**如果索引在当前数组的有效索引范围之外。

**例 1:**

```cs
// C# program to demonstrate the
// Array.GetValue(Int32) Method
using System;
public class GFG  {

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

输出:

```cs
element at index 3 is : D
element at index 1 is : B
element at index 2 is : C
element at index 0 is : A

```

**例 2:**

```cs
// C# program to demonstrate the
// Array.GetValue(Int64) Method
using System;
public class GFG  {

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

**输出:**

```cs
element at index 3 is : Perl
element at index 1 is : Java
element at index 2 is : C#
element at index 0 is : C++
element at index 0 is : Python

```

**注意:**对于在线编译器，不能使用 32 位或 64 位整数。对 32 或 64 位整数使用脱机编译器。