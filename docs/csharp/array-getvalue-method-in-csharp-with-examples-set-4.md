# 阵列。C# 中的 GetValue()方法，带示例| Set–4

> 原文:[https://www . geesforgeks . org/array-getvalue-method-in-csharp-with-examples-set-4/](https://www.geeksforgeeks.org/array-getvalue-method-in-csharp-with-examples-set-4/)

**阵列。C# 中的 GetValue()方法**用于获取当前[数组](https://www.geeksforgeeks.org/c-sharp-arrays/)中指定元素的值。该方法的重载列表中总共有 8 个方法，如下所示:

*   [**阵。GetValue(Int32，Int32)**](https://www.geeksforgeeks.org/array-getvalue-method-in-csharp-with-examples-set-1/)
*   [**阵。GetValue(Int64，Int64)**](https://www.geeksforgeeks.org/array-getvalue-method-in-csharp-with-examples-set-1/)
*   [**阵。GetValue(Int32)**](https://www.geeksforgeeks.org/array-getvalue-method-in-csharp-with-examples-set-2/)
*   [**阵。GetValue(Int64)**](https://www.geeksforgeeks.org/array-getvalue-method-in-csharp-with-examples-set-2/)
*   **阵列。GetValue(Int32，Int32，Int32)**
*   **阵列。GetValue(Int64，Int64，Int64)**
*   **Array.GetValue（Int32[]）**
*   **Array.GetValue（Int64[]）**

在本文中，我们将解释**数组。GetValue(Int32[])** 和**数组。GetValue(Int64[])** 方法。

**阵列。GetValue(Int32[])** 方法用于获取多维数组中指定位置的值。索引由 1D 数组传递给此方法，这意味着传递的 1D 数组包含指定的索引作为 1D 数组的数组元素，并且要搜索的元素位于 1D 数组中的索引处。索引被指定为 32 位整数。

**语法:**

```cs
public object GetValue (int[] index);

```

这里的“索引”是一个 32 位整数的 1D 数组，表示指定要搜索的元素位置的索引。搜索过了。

**返回:**该方法将由传递的 1D 数组定义的指定索引处的元素返回给 *GetValue* 方法。该值是一个 32 位整数值。

**异常:**

*   **参数异常:**如果当前数组中的维数不等于传递给 *GetValue* 方法的索引数组中的元素个数。
*   **indexoutofrangerexception:**如果索引数组中的元素定义的范围超出了当前数组相应维度的有效索引范围。
*   **ArgumentNullException:** 如果索引数组为空，则抛出。

**阵列。GetValue(Int64[])** 方法用于获取多维数组中指定位置的值。索引由 1D 数组传递给此方法，这意味着传递的 1D 数组包含指定的索引作为 1D 数组的数组元素，并且要搜索的元素位于 1D 数组中的索引处。索引被指定为 64 位整数。

**语法:**

```cs
public object GetValue (long[] index);

```

这里，**“index[]”**是 64 位整数的 1D 数组，表示指定要搜索的元素的位置的索引。

**返回:**该方法将由传递的 1D 数组定义的指定索引处的元素返回给 *GetValue* 方法。该值是一个 32 位整数值。

**异常:**

*   **参数异常:**如果当前数组中的维数不等于传递给 *GetValue* 方法的索引数组中的元素个数。
*   **argumentoutofrangerexception:**如果索引数组中的元素定义了一个范围，该范围超出了当前数组相应维度的有效索引范围。
*   **ArgumentNullException:** 如果索引数组为空，则抛出。

**例 1:**

## C#

```cs
// C# program to demonstrate the
// Array.GetValue(Int32[]) and
// Array.GetValue(Int64[]) method
using System;
public class GFG {

public static void Main() {

    // declare a character
    // array of size 1x2x2x3
    // it has 2 3D array
    // which have 2 row and 3 column each
    char[, , , ] arr = new char[1, 2, 2, 3]{
        {

            {// array 1
             {'A', 'B', 'C'},
             {'D', 'E', 'F'}

            },
            {// array 2
             {'G', 'H', 'I'},
             {'J', 'K', 'L'}}

        }
        /*Array look like
   |----------------------------------|
   | -------------------------------- |
   |  |A|          |B|           |C|  |
   |  |D|          |E|           |F|  |
   | -------------------------------- |
   | -------------------------------- |
   |  |G|          |H|           |I|  |
   |  |J|          |K|           |L|  |
   | -------------------------------- |
   |__________________________________|
   */
    };

    // initialize a integer array
    // contains the index of the element
    // index of 'L'
    int[] indx = new int[4]{0, 1, 1, 2};

    // "indx" array is passing
    // to GetValue(Int32[]) method
    Console.WriteLine("Element at index [0, 1, 1, 2] is : {0}",
                                           arr.GetValue(indx));
  }
}
```

**Output**

```cs
Element at index [0, 1, 1, 2] is : L

```

**例 2:**

## C#

```cs
// C# program to demonstrate the
// Array.GetValue(Int32[]) and
// Array.GetValue(Int64[]) method
using System;

class GFG {

public static void Main() {

    // declare a character
    // array of size 1x2x2x3
    // it has 2 3D array
    // which have 2 row and
    // 3 column each
    string[, , , ] arr = new string[1, 2, 2, 3];

    /*Array look like
|------------------------------------|
| ---------------------------------- |
|  |C++|          |Java|       |C#|  |
|  |Perl|          |python|    |PHP| |
| ---------------------------------- |
| ---------------------------------- |
|  |Ruby|        |F#|       |Julia|  |
|  |SQL|        |Kotlin|       |GO|  |
| ---------------------------------- |
|____________________________________|
*/

    arr.SetValue("C++", 0, 0, 0, 0);
    arr.SetValue("Java", 0, 0, 0, 1);
    arr.SetValue("C#", 0, 0, 0, 2);
    arr.SetValue("Perl", 0, 0, 1, 0);
    arr.SetValue("Python", 0, 0, 1, 1);
    arr.SetValue("PHP", 0, 0, 1, 2);
    arr.SetValue("Ruby", 0, 1, 0, 1);
    arr.SetValue("F#", 0, 1, 0, 1);
    arr.SetValue("Julia", 0, 1, 0, 2);
    arr.SetValue("SQL", 0, 1, 1, 0);
    arr.SetValue("kotlin", 0, 1, 1, 1);
    arr.SetValue("GO", 0, 1, 1, 2);

    // initialize a integer array
    // contains the index of the element
    // index of 'C#'
    int[] indx = new int[4]{0, 1, 1, 2};

    // "indx" array is passing
    // to GetValue(Int32[]) method
    Console.WriteLine("Element at index [0, 1, 1, 2] is : {0}",
                                           arr.GetValue(indx));
  }
}
```

**Output**

```cs
Element at index [0, 1, 1, 2] is : GO

```

**注意:**对于在线编译器，不能使用 32 位或 64 位整数。对 32 或 64 位整数使用脱机编译器。