# 在 C# 中将数组作为参数传递

> 原文:[https://www . geesforgeks . org/passing-arrays-as-arguments-in-c-sharp/](https://www.geeksforgeeks.org/passing-arrays-as-arguments-in-c-sharp/)

一个 [**数组**](https://www.geeksforgeeks.org/c-sharp-arrays/) 是一个相似类型变量的集合，用一个共同的名字来指代。在 C# 中，数组是引用类型，因此它可以作为参数传递给方法。方法可以修改数组元素的值。一维和多维数组都可以作为参数传递给方法。

#### 将一维数组作为参数传递给方法

可以将一维数组传递给一个方法。有各种各样的选项，比如首先，分别声明和初始化数组，然后将其传递给方法。其次，您可以在一行代码中声明、初始化数组并将其传递给方法。

**示例 1:** 首先声明并初始化数组，然后将其作为参数传递给方法。

## c#

```cs
// taking an integer array
// declaring and initializing
// the array
int[] arr = {1, 2, 3, 4};

// passing the array as an
// argument to the method
// Result is the method name
Result(arr);
```

**示例 2:** 在单行代码中声明、初始化数组并将数组传递给方法。

```cs
Result(new int[] {1, 2, 3, 4});
```

**代码:**在下面的程序中，我们将一维数组 *arr* 传递给方法结果。该方法是静态的，它将打印传递给它的数组元素。

## C#

```cs
// C# program for passing the 1-D
// array to method as argument
using System;

class GFG {

    // declaring a method
    static void Result(int[] arr) {

        // displaying the array elements
        for(int i = 0; i < arr.Length; i++)
        {
            Console.WriteLine("Array Element: "+arr[i]);
        }

    }

    // Main method
    public static void Main() {

        // declaring an array
        // and initializing it
        int[] arr = {1, 2, 3, 4, 5};

        // calling the method
        Result(arr);
    }
}
```

**输出:**

```cs
Array Element: 1
Array Element: 2
Array Element: 3
Array Element: 4
Array Element: 5
```

#### 将多维数组作为参数传递给方法

您也可以将多维数组传递给方法。有各种各样的选项，比如首先，分别声明和初始化多维数组，然后将其传递给方法。其次，您可以在一行代码中声明、初始化数组并将其传递给方法。

**示例 1:** 首先声明并初始化数组，然后将其作为参数传递给方法。

## c#

```cs
// declaring and initializing
// the 2-D array
int[,] arr = { {1, 2, 3, 4}, {5, 6, 7, 8} };

// passing the array as an
// argument to the method
// Result is the method name
Result(arr);
```

**示例 2:** 在单行代码中声明、初始化二维数组并将其传递给方法。

```cs
Result(new int[,] { {1, 2, 3, 4}, {5, 6, 7, 8} });
```

**代码:**在下面的程序中，我们将一个二维数组 *arr* 传递给给出矩阵转置的转置方法。 [**GetLength()**](https://www.geeksforgeeks.org/c-total-number-of-elements-present-in-an-array/) 方法用于统计特定维度中元素的总数。

## c#

```cs
// C# program for finding the transpose
// of matrix(2-D array) by using array
// as function arguments
using System;

class GFG {

    // temp is used as temporary variable
    static int temp = 0;

    // passing 2-D array 'arr' as argument
    // to find the transpose of matrix
    static void transpose(int[, ] arr)
    {
        for (int i = 0; i < arr.GetLength(0); i++) {
            for (int j = i; j < arr.GetLength(1); j++) {
                temp = arr[i, j];
                arr[i, j] = arr[j, i];
                arr[j, i] = temp;
            }
        }
    }

    // to display the transposed matrix
    static void displayresult(int[, ] arr)
    {

        Console.WriteLine("Matrix After Transpose: ");

        for (int i = 0; i < arr.GetLength(0); i++) {
            for (int j = 0; j < arr.GetLength(1); j++)
                Console.Write(arr[i, j] + " ");
            Console.WriteLine();
        }
    }

    // Main Method
    static public void Main()
    {
        // declaration of an 2-d array
        int[, ] arr;

        // initializing 2-D array
        // matrix of 4 rows and 4 columns
        arr = new int[4, 4]{ { 1, 2, 3, 4},
                             { 5, 6, 7, 8},
                             {9, 10, 11, 12},
                             {13, 14, 15, 16} };

        Console.WriteLine("Matrix Before Transpose: ");

        for (int i = 0; i < arr.GetLength(0); i++)
        {
            for (int j = 0; j < arr.GetLength(1); j++)
                Console.Write(arr[i, j] + " ");
            Console.WriteLine();
        }

        Console.WriteLine();

        // calling transpose method
        transpose(arr);

        // calling displayresult method
        // to display the result
        displayresult(arr);
    }
}
```

**输出:**

```cs
Matrix Before Transpose: 
1 2 3 4 
5 6 7 8 
9 10 11 12 
13 14 15 16 

Matrix After Transpose: 
1 5 9 13 
2 6 10 14 
3 7 11 15 
4 8 12 16 
```