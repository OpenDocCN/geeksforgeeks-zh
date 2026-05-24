# 使用递归生成子阵列

> 原文：[https://www.geeksforgeeks.org/generating-subarrays-using-recursion/](https://www.geeksforgeeks.org/generating-subarrays-using-recursion/)

给定一个数组，使用递归生成给定数组的所有可能的子数组。

**示例：**

```
Input : [1, 2, 3]
Output : [1], [1, 2], [2], [1, 2, 3], [2, 3], [3]

Input : [1, 2]
Output : [1], [1, 2], [2]
```

我们已经讨论了[迭代程序来生成所有子阵列](https://www.geeksforgeeks.org/subarraysubstring-vs-subsequence-and-programs-to-generate-them/)。在这篇文章中，递归被讨论。

## 方法

我们使用两个指针`start`和`end`来保持数组的开始和结束点，并遵循下面给出的步骤：

*   如果我们已经到达数组的末尾，请停止
*   如果`start`已经大于`end`，则增加`end`指数
*   打印从索引`start`到`end`的子阵列，并增加起始索引

下面是上述方法的实现。

## C++

```
// C++ code to print all possible subarrays 
// for given array using recursion

#include <iostream>
# include <vector>
using namespace std;

// Recursive function to print all possible subarrays 
// for given array
void printSubArrays(vector<int> arr, int start, int end)
{     
    // Stop if we have reached the end of the array     
    if (end == arr.size())
        return;

    // Increment the end point and start from 0
    else if (start > end)
        printSubArrays(arr, 0, end + 1);

    // Print the subarray and increment the starting point
    else
    {
        cout << "[";
        for (int i = start; i < end; i++){
            cout << arr[i] << ", ";
        }

        cout << arr[end] << "]" << endl;
        printSubArrays(arr, start + 1, end);
    }

    return;
}

int main()
{
   vector<int> arr = {1, 2, 3};
   printSubArrays(arr, 0, 0);
   return 0;
}
```

## Java

```
// Java code to print all possible subarrays
// for given array using recursion

class solution
{

// Recursive function to print all possible subarrays
// for given array
static void printSubArrays(int []arr, int start, int end)
{    
    // Stop if we have reached the end of the array     
    if (end == arr.length)
        return;

    // Increment the end point and start from 0
    else if (start > end)
        printSubArrays(arr, 0, end + 1);

    // Print the subarray and increment the starting point
    else
    {
        System.out.print("[");
        for (int i = start; i < end; i++){
            System.out.print(arr[i]+", ");
        }

        System.out.println(arr[end]+"]");
        printSubArrays(arr, start + 1, end);
    }

    return;
}

public static void main(String args[])
{
int []arr = {1, 2, 3};
printSubArrays(arr, 0, 0);

}
}
```

## Python 3

```
# Python3 code to print all possible subarrays
# for given array using recursion

# Recursive function to print all possible subarrays
# for given array
def printSubArrays(arr, start, end):

    # Stop if we have reached the end of the array   
    if end == len(arr):
        return

    # Increment the end point and start from 0
    elif start > end:
        return printSubArrays(arr, 0, end + 1)

    # Print the subarray and increment the starting
    # point
    else:
        print(arr[start:end + 1])
        return printSubArrays(arr, start + 1, end)

# Driver code
arr = [1, 2, 3]
printSubArrays(arr, 0, 0)
```

## C#

```
// C# code to print all possible subarrays
// for given array using recursion
using System;

class GFG
{

    // Recursive function to print all 
    // possible subarrays for given array
    static void printSubArrays(int []arr,
                        int start, int end)
    {
        // Stop if we have reached
        // the end of the array
        if (end == arr.Length)
            return;

        // Increment the end point
        // and start from 0
        else if (start > end)
            printSubArrays(arr, 0, end + 1);

        // Print the subarray and
        // increment the starting point
        else
        {
            Console.Write("[");
            for (int i = start; i < end; i++)
            {
                Console.Write(arr[i]+", ");
            }

            Console.WriteLine(arr[end]+"]");
            printSubArrays(arr, start + 1, end);
        }
        return;
    }

    // Driver code
    public static void Main(String []args)
    {
        int []arr = {1, 2, 3};
        printSubArrays(arr, 0, 0);
    }
}

// This code is contributed by Rajput-Ji
```

## PHP

```
<?php
// PHP code to print all possible
// subarrays for given array using recursion

// Recursive function to print all
// possible subarrays for given array
function printSubArrays($arr, $start, $end)
{
    // Stop if we have reached
    // the end of the array
    if ($end == count($arr))
        return;

    // Increment the end point
    // and start from 0
    else if ($start > $end)
        return printSubArrays($arr, 0,
                              $end + 1);

    // Print the subarray and increment
    // the starting point
    else
    {
    echo "[";
    for($i = $start; $i < $end + 1; $i++)
    {
        echo $arr[$i];
        if($i != $end)
        echo ", ";
    }
    echo "]\n";
        return printSubArrays($arr, $start + 1,
                                    $end);
    }
}

// Driver code
$arr = array(1, 2, 3);
printSubArrays($arr, 0, 0);

// This code is contributed by mits
?>
```

## JavaScript

```
<script>

// Javascript code to print all possible
// subarrays for given array using recursion

// Recursive function to print all
// possible subarrays for given array
function printSubArrays(arr, start, end)
{

    // Stop if we have reached the end
    // of the array     
    if (end == arr.length)
        return;

    // Increment the end point and start
    // from 0
    else if (start > end)
        printSubArrays(arr, 0, end + 1);

    // Print the subarray and increment
    // the starting point
    else
    {
        document.write("[");
        for(var i = start; i < end; i++)
        {
            document.write( arr[i] + ", ");
        }

        document.write(arr[end] + "]<br>");
        printSubArrays(arr, start + 1, end);
    }
    return;
}

// Driver code
var arr = [ 1, 2, 3 ];
printSubArrays(arr, 0, 0);

// This code is contributed by rutvik_56

</script>
```

## 输出

```
[1]
[1, 2]
[2]
[1, 2, 3]
[2, 3]
[3]
```

## 时间复杂度

`O(n^2)`