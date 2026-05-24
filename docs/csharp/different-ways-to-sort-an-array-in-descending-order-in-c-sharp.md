# 在 C# 中对数组进行降序排序的不同方式

> 原文:[https://www . geeksforgeeks . org/不同的排序方式-按 c-sharp 降序排列数组/](https://www.geeksforgeeks.org/different-ways-to-sort-an-array-in-descending-order-in-c-sharp/)

一个 **[数组](https://www.geeksforgeeks.org/c-sharp-arrays/)** 是一组相似类型的变量，用一个共同的名字来指代。每个数据项被称为数组的一个元素。将数组元素从大到小排列称为按降序排列数组。

**示例:**

```cs
Input : array = {5, 9, 1, 4, 6, 8};
Output : 9, 8, 6, 5, 4, 1

Input : array = {1, 9, 6, 7, 5, 9};
Output : 9 9 7 6 5 1

Input : array = {-8, 9, 7, 7, 0, 9, -9};
Output : 9 9 7 7 0 -8 -9

```

**方法一:使用数组。排序()和数组。反向()方法**
首先，使用[数组对数组进行排序。Sort()](https://www.geeksforgeeks.org/how-to-sort-an-array-in-c-sharp-array-sort-method-set-1/) 将一个数组按升序排序的方法，然后使用*数组将其反转。反向()*方法。

```cs
// C# program sort an array in decreasing order
// using Array.Sort() and Array.Reverse() Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        // declaring and initializing the array
        int[] arr = new int[] {1, 9, 6, 7, 5, 9};

        // Sort array in ascending order.
        Array.Sort(arr);

        // reverse array
        Array.Reverse(arr);

        // print all element of array
        foreach(int value in arr)
        {
            Console.Write(value + " ");
        }
    }
}
```

**Output:**

```cs
9 9 7 6 5 1

```

**方法二:使用 CompareTo()方法**
也可以使用 CompareTo()方法对数组进行降序排序。

```cs
// C# program sort an array in 
// decreasing order using 
// CompareTo() Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        // declaring and initializing the array
        int[] arr = new int[] {1, 9, 6, 7, 5, 9};

        // Sort the arr from last to first.
        // compare every element to each other
        Array.Sort<int>(arr, new Comparison<int>(
                  (i1, i2) => i2.CompareTo(i1)));

        // print all element of array
        foreach(int value in arr)
        {
            Console.Write(value + " ");
        }
    }
}
```

**Output:**

```cs
9 9 7 6 5 1

```

**方法 3:使用[委托](https://www.geeksforgeeks.org/c-delegates/)**
这里，首先使用匿名方法对委托进行 Sort()。

```cs
// C# program sort an array 
// in decreasing order
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        // declaring and initializing the array
        int[] arr = new int[] {1, 9, 6, 7, 5, 9};

        // Sort the arr from last to first
        // Normal compare is m-n 
        Array.Sort<int>(arr, delegate(int m, int n)
                                { return n - m; });

        // print all element of array
        foreach(int value in arr)
        {
            Console.Write(value + " ");
        }
    }
}
```

**Output:**

```cs
9 9 7 6 5 1

```

**方法四:采用迭代方式**

不使用任何内置函数，通过迭代方式对数组进行排序。

```cs
// C# program sort an array 
// in decreasing order using 
// iterative way
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        // declaring and initializing the array
        int[] arr = new int[] {1, 9, 6, 7, 5, 9};

        int temp;

        // traverse 0 to array length
        for (int i = 0; i < arr.Length - 1; i++)

            // traverse i+1 to array length
            for (int j = i + 1; j < arr.Length; j++)

                // compare array element with 
                // all next element
                if (arr[i] < arr[j]) {

                    temp = arr[i];
                    arr[i] = arr[j];
                    arr[j] = temp;
                }

        // print all element of array
        foreach(int value in arr)
        {
            Console.Write(value + " ");
        }
    }
}
```

**Output:**

```cs
9 9 7 6 5 1

```

**方法五:使用 LINQ 降序**
LINQ 代表语言综合查询。这是一种统一的查询语法，用于检索和保存来自不同来源的数据。这里 *OrderByDescending* 排序方式用于降序排序。LINQ 返回 *IOrderedIEnumerable* ，使用 *ToArray()* 方法将其转换为数组。

```cs
// C# program sort an array in decreasing 
// order by using LINQ OrderByDescending 
// method
using System;
using System.Linq;

class GFG {

    // Main Method
    public static void Main()
    {

        // declaring and initializing the 
        // array with 6 positive number
        int[] arr = new int[] {1, 9, 6, 7, 5, 9};

        // Sort the arr in decreasing order
        // and return a array
        arr = arr.OrderByDescending(c => c).ToArray();

        // print all element of array
        foreach(int value in arr)
        {
            Console.Write(value + " ");
        }
    }
}
```

**Output:**

```cs
9 9 7 6 5 1

```