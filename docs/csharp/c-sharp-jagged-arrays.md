# C# |交错数组

> 原文:[https://www.geeksforgeeks.org/c-sharp-jagged-arrays/](https://www.geeksforgeeks.org/c-sharp-jagged-arrays/)

#### 先决条件:[c# 中的数组](https://www.geeksforgeeks.org/c-sharp-arrays/)

交错数组是数组的**数组，这样成员数组可以有不同的大小。换句话说，每个数组索引的长度可以不同。交错数组的元素是引用类型，默认情况下初始化为空。交错数组也可以与多维数组混合使用。这里，行数在声明时是固定的，但是您可以改变列数。**

#### 申报

在交错数组中，用户只需提供行数。如果用户也要提供列数，那么这个数组将不再是交错数组。

**语法:**

```cs
data_type[][] name_of_array = new data_type[rows][]

```

**示例:**

```cs
int[][] jagged_arr = new int[4][]

```

在上面的示例中，声明了一个一维数组，它有 4 个元素(行)，每个元素都是一维整数数组。

#### 初始化

交错数组**的元素在使用前必须初始化**。您可以分别初始化每个数组元素。有许多方法可以初始化 Jagged 数组的元素。

**示例 1:** 分别提供每个数组元素的大小。这里每个元素都是一维整数数组，其中:

*   第一行或元素是 2 个整数的数组。
*   第二行或第二个元素是 4 个整数的数组。
*   第三行或第三个元素是 6 个整数的数组。
*   第四行或第四个元素是 7 个整数的数组。

```cs
jagged_arr[0] = new int[2];
jagged_arr[1] = new int[4];
jagged_arr[2] = new int[6];
jagged_arr[3] = new int[7];

```

**示例 2:** 当不需要数组大小时，其元素可以用直接值初始化，如下所示:

```cs
jagged_arr[0] = new int[] {1, 2, 3, 4};
jagged_arr[1] = new int[] {11, 34, 67};
jagged_arr[2] = new int[] {89, 23};
jagged_arr[3] = new int[] {0, 45, 78, 53, 99};

```

#### 声明和初始化

**实施例 1:** 使用直接法

```cs
int[][] jagged_arr = new int[][] 
{
    new int[] {1, 2, 3, 4},
    new int[] {11, 34, 67},
    new int[] {89, 23},
    new int[] {0, 45, 78, 53, 99}
};

```

**例 2:** 使用短手法。元素没有默认初始化，因此用户不能在元素初始化中忽略新运算符。

```cs
int[][] jagged_arr = 
{
    new int[] {1, 2, 3, 4},
    new int[] {11, 34, 67},
    new int[] {89, 23},
    new int[] {0, 45, 78, 53, 99}
};

```

#### 访问元素

要访问 Jagged 数组的元素，用户必须用数组名指定行和列。

**示例:**

```cs
// Accessing & Assigning 99 to the third element ([2]) of the second array ([1])
jagged_arr[1][2] = 99;

// Accessing & Assigning 47 to the first element ([0]) of the fourth array ([3]):
jagged_arr[3][0] = 47;

```

**程序:**

```cs
// C# program to illustrate the declaration 
// and Initialization of Jagged Arrays
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        // Declare the Jagged Array of four elements:
        int[][] jagged_arr = new int[4][];

        // Initialize the elements
        jagged_arr[0] = new int[] {1, 2, 3, 4};
        jagged_arr[1] = new int[] {11, 34, 67};
        jagged_arr[2] = new int[] {89, 23};
        jagged_arr[3] = new int[] {0, 45, 78, 53, 99};

        // Display the array elements:
        for (int n = 0; n < jagged_arr.Length; n++) {

            // Print the row number
            System.Console.Write("Row({0}): ", n);

            for (int k = 0; k < jagged_arr[n].Length; k++) {

                // Print the elements in the row
                System.Console.Write("{0} ", jagged_arr[n][k]);
            }
            System.Console.WriteLine();
        }
    }
}
```

**输出:**

```cs
Row(0): 1 2 3 4 
Row(1): 11 34 67 
Row(2): 89 23 
Row(3): 0 45 78 53 99 

```

#### 多维数组的交错数组

交错数组和多维数组可以混合使用。下面是包含四个不同大小的二维数组元素的一维交错数组的声明和初始化。

**示例:**

```cs
int[][, ] jagged_arr1 = new int[4][, ] 
{
    new int[, ] { {1, 3}, {5, 7} },
    new int[, ] { {0, 2}, {4, 6}, {8, 10} },
    new int[, ] { {7, 8}, {3, 1}, {0, 6} },
    new int[, ] { {11, 22}, {99, 88}, {0, 9} } 
};

```

用户可以访问如下例所示的各个元素，其中显示了第二个数组的元素[2，0]的值(即值为 8)

**示例:**

```cs
System.Console.Write("{0}", jagged_arr1[1][1, 0]);

```

**程序:**

```cs
// C# program to illustrate the Mixing of 1-D
// Jagged Array with the four 2-D array
using System;
namespace geeksforgeeks {

class GFG {

// Main Method
public static void Main()
{

    // Declaration and Initialization of 
    // Jagged array with 4 2-D arrays
    int[][, ] jagged_arr1 = new int[4][, ] {new int[, ] {{1, 3}, {5, 7}},
                                    new int[, ] {{0, 2}, {4, 6}, {8, 10}},
                                    new int[, ] {{7, 8}, {3, 1}, {0, 6}},
                                    new int[, ] {{11, 22}, {99, 88}, {0, 9}}};

    // Display the array elements:
    // Length method returns the number of
    // arrays contained in the jagged array
    for (int i = 0; i < jagged_arr1.Length; i++)
    {

        int x = 0;

        // GetLength method takes integer x which 
        // specifies the dimension of the array
        for (int j = 0; j < jagged_arr1[i].GetLength(x); j++) 
        {

            // Rank is used to determine the total 
            // dimensions of an array 
            for (int k = 0; k < jagged_arr1[j].Rank; k++)
                Console.Write("Jagged_Array[" + i + "][" + j + ", " + k + "]: "
                                            + jagged_arr1[i][j, k] + " ");
            Console.WriteLine();
        }
        x++;
        Console.WriteLine();
    }
}
}
}
```

**输出:**

```cs
Jagged_Array[0][0, 0]: 1 Jagged_Array[0][0, 1]: 3 
Jagged_Array[0][1, 0]: 5 Jagged_Array[0][1, 1]: 7 

Jagged_Array[1][0, 0]: 0 Jagged_Array[1][0, 1]: 2 
Jagged_Array[1][1, 0]: 4 Jagged_Array[1][1, 1]: 6 
Jagged_Array[1][2, 0]: 8 Jagged_Array[1][2, 1]: 10 

Jagged_Array[2][0, 0]: 7 Jagged_Array[2][0, 1]: 8 
Jagged_Array[2][1, 0]: 3 Jagged_Array[2][1, 1]: 1 
Jagged_Array[2][2, 0]: 0 Jagged_Array[2][2, 1]: 6 

Jagged_Array[3][0, 0]: 11 Jagged_Array[3][0, 1]: 22 
Jagged_Array[3][1, 0]: 99 Jagged_Array[3][1, 1]: 88 
Jagged_Array[3][2, 0]: 0 Jagged_Array[3][2, 1]: 9 

```