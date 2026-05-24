# c#–使用预定义功能执行搜索

> 原文:[https://www . geesforgeks . org/c-sharp-执行-搜索-使用-预定义-函数/](https://www.geeksforgeeks.org/c-sharp-perform-searching-using-predefined-functions/)

给定一个数组，现在我们的任务是使用 C# 中的预定义函数来搜索数组中的元素。因此，最好的搜索技术是二分搜索法，它将使用预定义的函数搜索数组中的给定元素。二分搜索法算法是一种高效的算法，只适用于元素的有序集合。所以如果我们想使用二分搜索法，那么数组必须被排序，否则，它会给出错误的结果。所以要对数组进行排序，我们使用 [Sort()](https://www.geeksforgeeks.org/how-to-sort-an-array-in-c-sharp-array-sort-method-set-1/) 函数。二分搜索法将通过重复将搜索间隔分成两半，在排序的数组中进行搜索。它将以覆盖整个数组的间隔开始。如果搜索元素小于间隔中间的项目，请将间隔缩小到下半部分。否则缩小到上半部分。它将重复检查，直到找到元素或间隔为空。我们可以使用 [BinarySearch()](https://www.geeksforgeeks.org/how-to-use-array-binarysearch-method-in-c-sharp-set-1/# :~:text=BinarySearch(Array%2C%20Int32%2C%20Int32%2C%20Object)%20Method,is%20defined%20by%20the%20user.) 功能来执行二分搜索法。

**语法**:

```cs
Array.BinarySearch(array_name, (Object)element)
```

其中 array_name 是输入数组，element 是要用 Object 数据类型搜索的元素。

**示例:**

```cs
Input:
Array size: 5
Elements: {3, 4, 5, 2, 1}
Element to Search: 4
Output:
Present in 3rd position

Input:
Array size: 1
Elements: {1}
Element to Search: 1
Output:
Present in 0 th position
```

**进场:**

> 1.  Read the array size from the user.
> 2.  Reads elements into arrays from users.
> 3.  Use the Sort () function to sort the array.
> 4.  Read the elements to be searched in a given array from the user.
> 5.  Use the method of bisection function to get the elements in the array.
> 6.  Displays the element and its position in the array.

**例**:

## C#

```cs
// C# program to search elements in the
// array using predefined functions
using System;

class GFG{

public static void Main()
{
    Console.WriteLine("Enter the size of array ");

    // Read the array size
    string n = Console.ReadLine();
    int data = Int32.Parse(n);

    // Declare an array
    int[] array1 = new int[data];
    Console.WriteLine("Enter data :");
    for(int i = 0; i < data; i++)
    {
        string s = Console.ReadLine();
        array1[i] = Int32.Parse(s);
    }

    // Sort an array by using Sort() function
    Array.Sort(array1);

    // Read a number to search an array
    Console.WriteLine("Search a number : ");
    string search = Console.ReadLine();
    int data2 = Int32.Parse(search);

    // Apply BinarySearch() function to
    // search the specified element
    int data3 = Array.BinarySearch(array1,
                                   (Object)data2);

    // Display the position of the slement
    Console.WriteLine("Element {1} is present in  {0} position",
                      data3, array1[data3]);
}
}
```

**输出:**

```cs
Enter the size of array 
5
Enter data :
1
4
2
7
8
Search a number : 
2
Element 2 is present in  1 position
```