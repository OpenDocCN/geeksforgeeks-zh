# 不使用循环和递归的数组元素之和

> 原文:[https://www . geesforgeks . org/无循环递归 n 元素之和/](https://www.geeksforgeeks.org/sum-of-n-elements-without-loops-and-recursion/)

给定一个 N 个元素的数组，任务是在不使用循环(for，while & doWhile)和递归的情况下找到 N 个元素的和。
**例:**

```cpp
Input: arr[]={1, 2, 3, 4, 5}   
Output: 15

Input: arr[]={10, 20, 30}   
Output: 60
```

**方法:**无条件跳转语句可以用来解决这个问题。
**无条件跳转语句:**
[跳转语句](https://www.geeksforgeeks.org/c-sharp-jump-statements-break-continue-goto -return-and-throw/)中断语句的顺序执行，使执行在程序的不同点继续。如果跳转目的地在自动变量的作用域之外，则跳转会破坏自动变量。造成 C 中无条件跳转的语句有四种:[断](https://www.geeksforgeeks.org/break-statement-cc/)、[继续](https://www.geeksforgeeks.org/continue-statement-cpp/)、[转到](https://www.geeksforgeeks.org/goto-statement-in-c-cpp/)，返回。
为了解决这个特殊问题，goto 语句可能会很有用。
[**goto 语句**](https://www.geeksforgeeks.org/goto-statement-in-c-cpp/)**:**
goto 语句是一个跳转语句，有时也被称为无条件跳转语句。goto 语句可以用来从函数中的任何地方跳转到任何地方。
**语法** :

```cpp
Syntax1      |   Syntax2
----------------------------
goto label;  |    label:  
.                  |    .
.                  |    .
.                  |    .
label:          |    goto label;
```

在上面的语法中，第一行告诉编译器转到或跳转到标记为标签的语句。这里的标签是用户定义的标识符，表示目标语句。紧跟在“label:”后面的语句是目标语句。“label:”也可以出现在“goto label 之前语句。

![goto](img/848e1955930c2ca88c3079efd0850e22.png)

以下是上述方法的实现:

## C++

```cpp
// C++ program to find the sum of
// N elements with goto statement

#include <iostream>
using namespace std;

// Function to perform desired operation
int operate(int array[], int N)
{
    int sum = 0, index = 0;

label:
    sum += array[index++ ];

    if (index < N) {

        // backward jump of goto statement
        goto label;
    }

    // return the sum
    return sum;
}

// Driver Code
int main()
{

    // Get N
    int N = 5, sum = 0;

    // Input values of an array
    int array[] = { 1, 2, 3, 4, 5 };

    // Find the sum
    sum = operate(array, N);

    // Print the sum
    cout << sum;
}
```

## C

```cpp
// C program to find the sum of
// N elements with goto statement

#include <stdio.h>

// Function to perform desired operation
int operate(int array[], int N)
{
    int sum = 0, index = 0;

label:
    sum += array[index++ ];

    if (index < N) {

        // backward jump of goto statement
        goto label;
    }

    // return the sum
    return sum;
}

// Driver Code
int main()
{

    // Get N
    int N = 5, sum = 0;

    // Input values of an array
    int array[] = { 1, 2, 3, 4, 5 };

    // Find the sum
    sum = operate(array, N);

    // Print the sum
    printf("%d", sum);
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
// Java program to find the sum of
// N elements
class GFG
{
  // Function to perform desired operation
  static int operate(int array[], int N)
  {
    int sum = 0, index = 0;      
    while(true)
    {
      sum += array[index++ ];      
      if (index < N)
      {

        // backward jump of goto statement
        continue;
      }
      else
      {
        break;
      }
    }

    // return the sum
    return sum;
  }

  // Driver code
  public static void main(String[] args)
  {

    // Get N
    int N = 5, sum = 0;

    // Input values of an array
    int array[] = { 1, 2, 3, 4, 5 };

    // Find the sum
    sum = operate(array, N);

    // Print the sum
    System.out.print(sum);
  }
}

// This code is contributed by divyeshrabaiya07
```

## 蟒蛇 3

```cpp
# Python3 program to find the sum of
# N elements

# Function to perform desired operation
def operate(array, N) :  
    Sum, index = 0, 0  
    while(True) :
        Sum += array[index]
        index += 1
        if index < N :

            # backward jump of goto statement
            continue
        else :
            break

    # return the sum
    return Sum

# Get N
N, Sum = 5, 0

# Input values of an array
array = [ 1, 2, 3, 4, 5 ]

# Find the sum
Sum = operate(array, N)

# Print the sum
print(Sum)

# This code is contributed by divyesh072019
```

## C#

```cpp
// C# program to find the sum of
// N elements with goto statement
using System;

class GFG
{
// Function to perform desired operation
static int operate(int[] array, int N)
{
    int sum = 0, index = 0;

label:
    sum += array[index++ ];

    if (index < N)
    {

        // backward jump of goto statement
        goto label;
    }

    // return the sum
    return sum;
}

// Driver Code
public static void Main()
{

    // Get N
    int N = 5, sum = 0;

    // Input values of an array
    int[] array = { 1, 2, 3, 4, 5 };

    // Find the sum
    sum = operate(array, N);

    // Print the sum
    Console.Write(sum);
}
}

// This code is contributed
// by Akanksha Rai
```

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```cpp
<?php
// PHP program to find the sum of N
// elements with goto statement
function operate($array, $N)
{
    $sum = 0;
    $index = 0;
    label:
        $sum += $array[$index++ ];

        if($index < $N)
        {
            // backward jump of goto statement
            goto label;
        }

        // return the sum
        return $sum;
}

// Driver code
$N = 5;

$array = array(1, 2, 3, 4, 5);

echo operate($array, $N);

// This code is contributed
// by Mohit kumar 29
?>
```

## java 描述语言

```cpp
<script>
    // Javascript program to find the sum of
    // N elements

    // Function to perform desired operation
    function operate(array, N)
    {
      let sum = 0, index = 0;     
      while(true)
      {
        sum += array[index++ ];     
        if (index < N)
        {

          // backward jump of goto statement
          continue;
        }
        else
        {
          break;
        }
      }

      // return the sum
      return sum;
    }

    // Get N
    let N = 5, sum = 0;

    // Input values of an array
    let array = [ 1, 2, 3, 4, 5 ];

    // Find the sum
    sum = operate(array, N);

    // Print the sum
    document.write(sum);

    // This code is contributed by suresh07.
</script>
```

**Output:** 

```cpp
15
```