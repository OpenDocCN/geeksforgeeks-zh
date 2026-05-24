# 程序以相反的顺序将一个数组的内容复制到另一个数组中

> 原文:[https://www . geesforgeks . org/program-to-copy-将一个数组的内容以相反的顺序复制到另一个数组中/](https://www.geeksforgeeks.org/program-to-copy-the-contents-of-one-array-into-another-in-the-reverse-order/)

给定一个[数组](https://www.geeksforgeeks.org/array-data-structure/)，任务是将这些数组元素复制到反向数组中的另一个数组中。
**例:**

```cpp
Input: array: 1 2 3 4 5 
Output: 5 4 3 2 1 

Input: array: 10 20 30 40 50 
Output: 50 40 30 20 10  
```

设**透镜**为原阵列长度。我们将每个元素 original_arr[i]复制到 copy_arr[n-i-1]中，以在 copy_arr[]中获得反转。

## C++

```cpp
// C program to copy the contents
// of one array into another
// in the reverse order

#include <stdio.h>

// Function to print the array
void printArray(int arr[], int len)
{
    int i;
    for (i = 0; i < len; i++) {
        printf("%d ", arr[i]);
    }
}

// Driver code
int main()
{
    int original_arr[] = {1, 2, 3, 4, 5};
    int len = sizeof(original_arr)/sizeof(original_arr[0]);

    int copied_arr[len], i, j;

    // Copy the elements of the array
    // in the copied_arr in Reverse Order
    for (i = 0; i < len; i++) {
        copied_arr[i] = original_arr[len - i - 1];
    }

    // Print the original_arr
    printf("\nOriginal array: ");
    printArray(original_arr, len);

    // Print the copied array
    printf("\nResultant array: ");
    printArray(copied_arr, len);

    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
// Java program to copy the contents
// of one array into another
// in the reverse order
class GFG {

// Function to print the array
static void printArray(int arr[], int len)
{
    int i;
    for (i = 0; i < len; i++)
    {
        System.out.printf("%d ", arr[i]);
    }
}

// Driver code
public static void main(String[] args)
{
    int original_arr[] = {1, 2, 3, 4, 5};
    int len = original_arr.length;
    int copied_arr[] = new int[len], i, j;

    // Copy the elements of the array
    // in the copied_arr in Reverse Order
    for (i = 0; i < len; i++)
    {
        copied_arr[i] = original_arr[len - i - 1];
    }

    // Print the original_arr
    System.out.printf("\nOriginal array: ");
    printArray(original_arr, len);

    // Print the copied array
    System.out.printf("\nResultant array: ");
    printArray(copied_arr, len);
    }
}

// This code is contributed by
// PrinciRaj1992
```

## 蟒蛇 3

```cpp
# Python3 program to copy the contents of one
# array into another in the reverse order
import math as mt

# Function to print the array
def printArray(arr, Len):

    for i in range(Len):
        print(arr[i], end = " ")

# Driver code
original_arr = [1, 2, 3, 4, 5]
Len = len(original_arr)

copied_arr = [0 for i in range(Len)]

# Copy the elements of the array
# in the copied_arr in Reverse Order
for i in range(Len):
    copied_arr[i] = original_arr[Len - i - 1]

# Print the original_arr
print("Original array: ", end = "")
printArray(original_arr, Len)

# Print the copied array
print("\nResultant array: ", end = "")
printArray(copied_arr, Len)

# This code is contributed by
# Mohit kumar 29
```

## C#

```cpp
// C# program to copy the contents
// of one array into another
// in the reverse order
using System;
class GFG
{

// Function to print the array
static void printArray(int []arr, int len)
{
    int i;
    for (i = 0; i < len; i++)
    {
        Console.Write(arr[i]);
    }
}

// Driver code
public static void Main()
{
    int []original_arr = {1, 2, 3, 4, 5};
    int len = original_arr.Length;
    int []copied_arr = new int[len];
    int i;

    // Copy the elements of the array
    // in the copied_arr in Reverse Order
    for (i = 0; i < len; i++)
    {
        copied_arr[i] = original_arr[len - i - 1];
    }

    // Print the original_arr
    Console.Write("\nOriginal array: ");
    printArray(original_arr, len);

    // Print the copied array
    Console.Write("\nResultant array: ");
    printArray(copied_arr, len);
    }
}

// This code is contributed by Rajput-Ji
```

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```cpp
<?php
// PHP program to copy the contents
// of one array into another
// in the reverse order

// Function to print the array
function printArray($arr, $len)
{
    for ($i = 0; $i < $len; $i++)
    {
        echo $arr[$i], " ";
    }
}

// Driver code
$original_arr = array(1, 2, 3, 4, 5);
$len = sizeof($original_arr);

$copied_arr = array();

// Copy the elements of the array
// in the copied_arr in Reverse Order
for ($i = 0; $i < $len; $i++)
{
    $copied_arr[$i] = $original_arr[$len - $i - 1];
}

// Print the original_arr
echo "Original array: ";
printArray($original_arr, $len);

// Print the copied array
echo "\nResultant array: ";
printArray($copied_arr, $len);

// This code is contributed by Ryuga
?>
```

## java 描述语言

```cpp
<script>

// JavaScript program to copy the contents
// of one array into another
// in the reverse order

// Function to print the array
function printArray(arr, len)
{
    var i;
    for (i = 0; i < len; i++) {
        document.write( arr[i] + " ");
    }
}

// Driver code
var original_arr = [1, 2, 3, 4, 5];
var len = original_arr.length;
var copied_arr = Array(len), i, j;

// Copy the elements of the array
// in the copied_arr in Reverse Order
for (i = 0; i < len; i++) {
    copied_arr[i] = original_arr[len - i - 1];
}
// Print the original_arr
document.write("Original array: ");
printArray(original_arr, len);

// Print the copied array
document.write("<br>Resultant array: ");
printArray(copied_arr, len);

</script>
```

**Output:** 

```cpp
Original array: 1 2 3 4 5 
Resultant array: 5 4 3 2 1
```

***时间复杂度:** O(len)*

***辅助空间:** O(镜头)*