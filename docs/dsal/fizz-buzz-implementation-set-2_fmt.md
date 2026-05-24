# 嘶嘶声实现|第二集

> 原文: [https://www.geeksforgeeks.org/fizz-buzz-implementation-set-2/](https://www.geeksforgeeks.org/fizz-buzz-implementation-set-2/)

给定一个整数 `N`，任务是将 `1` 到 `N` 的所有数字打印出来，将 `3`、`5` 的倍数以及 `3` 和 `5` 的倍数分别替换为`"Fizz"`、`"Buzz"`和`"FizzBuzz"`。

**示例:**

> **输入:** `N = 5`
> **输出:** 1, 2, Fizz, 4, Buzz
>
> **输入:** `N = 15`
> **输出:** 1, 2, Fizz, 4, Buzz, Fizz, 7, 8, Fizz, Buzz, 11, Fizz, 13, 14, FizzBuzz

## 使用模运算符

解决这个问题最简单的方法就是使用[模运算符](https://www.geeksforgeeks.org/modulo-operator-in-c-cpp-with-examples/)。该方法参见本文[前一篇文章](https://www.geeksforgeeks.org/fizz-buzz-implementation/)。

## 不使用取模运算符

不使用取模运算符就可以解决上述问题，因为:

*   模运算符是一种非常昂贵的运算。在最底层，模是除法。
*   编译器的 `DIV` 指令给出除法和模运算的结果。然而，现代的中央处理器使用带有查找表的专用除法电路，因此，通过使用位移位不会有任何明显的速度变化。
*   但是对于大整数，观察到模运算程序中的运行时间比另一个慢很多，计算复杂度为 `O(N^2)`。

## 按照以下步骤解决问题

*   初始化两个计数变量，比如 `count3` 和 `count5`，分别存储可被 `3` 和 `5` 整除的个数。
*   [使用变量迭代范围](https://www.geeksforgeeks.org/range-based-loop-c/) `[1, N]`，比如 `i`，并执行以下步骤:
    *   将 `count3` 和 `count5` 增加 `1`。
    *   如果 `count3` 的值等于 `3`，则打印 `"Fizz"` 并设置 `count3 = 0`。
    *   同样，如果 `count5` 的值等于 `5`，则打印 `"Buzz"` 并设置 `count5 = 0`。
    *   如果以上条件都不匹配，则打印 `i`。

## 下面是上述方法的实现

### C++

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to generate FizzBuzz sequence
void fizzBuzz(int N)
{
    // Stores count of multiples
    // of 3 and 5 respectively
    int count3 = 0;
    int count5 = 0;

    // Iterate from 1 to N
    for (int i = 1; i <= N; i++) {

        // Increment count3 by 1
        count3++;

        // Increment count5 by 1
        count5++;

        // Initialize a boolean variable
        // to check if none of the
        // condition matches
        bool flag = false;

        // Check if the value of count3
        // is equal to 3
        if (count3 == 3) {
            cout << "Fizz";

            // Reset count3 to 0, and
            // set flag as True
            count3 = 0;
            flag = true;
        }

        // Check if the value of count5
        // is equal  to 5
        if (count5 == 5) {
            cout << "Buzz";

            // Reset count5 to 0, and
            // set flag as True
            count5 = 0;
            flag = true;
        }

        // If none of the condition matches
        if (!flag) {
            cout << i;
        }

        cout << " ";
    }
}

// Driver Code
int main()
{
    int N = 15;
    fizzBuzz(N);

    return 0;
}
```

### Java

```java
// Java program for the above approach
import java.util.*;
class GFG
{

// Function to generate FizzBuzz sequence
static void fizzBuzz(int N)
{

    // Stores count of multiples
    // of 3 and 5 respectively
    int count3 = 0;
    int count5 = 0;

    // Iterate from 1 to N
    for (int i = 1; i <= N; i++) {

        // Increment count3 by 1
        count3++;

        // Increment count5 by 1
        count5++;

        // Initialize a boolean variable
        // to check if none of the
        // condition matches
        boolean flag = false;

        // Check if the value of count3
        // is equal to 3
        if (count3 == 3) {
            System.out.print("Fizz");

            // Reset count3 to 0, and
            // set flag as True
            count3 = 0;
            flag = true;
        }

        // Check if the value of count5
        // is equal  to 5
        if (count5 == 5) {
            System.out.print("Buzz");

            // Reset count5 to 0, and
            // set flag as True
            count5 = 0;
            flag = true;
        }

        // If none of the condition matches
        if (!flag) {
            System.out.print(i);
        }

        System.out.print(" ");
    }
}

// Driver Code
public static void main(String[] args)
{
    int N = 15;
    fizzBuzz(N);
}
}

// This code is contributed by susmitakundugoaldanga.
```

### Python 3

```python
# Python3 program for the above approach

# Function to generate FizzBuzz sequence
def fizzBuzz(N):

    # Stores count of multiples
    # of 3 and 5 respectively
    count3 = 0
    count5 = 0

    # Iterate from 1 to N
    for i in range(1, N + 1):

        # Increment count3 by 1
        count3 += 1

        # Increment count5 by 1
        count5 += 1

        # Initialize a boolean variable
        # to check if none of the
        # condition matches
        flag = False

        # Check if the value of count3
        # is equal to 3
        if (count3 == 3):
            print ("Fizz", end = "")

            # Reset count3 to 0, and
            # set flag as True
            count3 = 0
            flag = True

        # Check if the value of count5
        # is equal  to 5
        if (count5 == 5):
            print ("Buzz", end = "")

            # Reset count5 to 0, and
            # set flag as True
            count5 = 0
            flag = True

        # If none of the condition matches
        if (not flag):
            print (i, end = "")

        print(end = " ")

# Driver Code
if __name__ == '__main__':
    N = 15
    fizzBuzz(N)

    # This code is contributed by mohit kumar 29.
```

### C#

```csharp
// C# program for the above approach
using System;

class GFG{

// Function to generate FizzBuzz sequence
static void fizzBuzz(int N)
{

    // Stores count of multiples
    // of 3 and 5 respectively
    int count3 = 0;
    int count5 = 0;

    // Iterate from 1 to N
    for(int i = 1; i <= N; i++)
    {

        // Increment count3 by 1
        count3++;

        // Increment count5 by 1
        count5++;

        // Initialize a bool variable
        // to check if none of the
        // condition matches
        bool flag = false;

        // Check if the value of count3
        // is equal to 3
        if (count3 == 3)
        {
            Console.Write("Fizz");

            // Reset count3 to 0, and
            // set flag as True
            count3 = 0;
            flag = true;
        }

        // Check if the value of count5
        // is equal  to 5
        if (count5 == 5)
        {
            Console.Write("Buzz");

            // Reset count5 to 0, and
            // set flag as True
            count5 = 0;
            flag = true;
        }

        // If none of the condition matches
        if (!flag)
        {
            Console.Write(i);
        }
        Console.Write(" ");
    }
}

// Driver Code
public static void Main(String[] args)
{
    int N = 15;

    fizzBuzz(N);
}
}

// This code is contributed by shikhasingrajput
```

# JavaScript 描述语言

```javascript
<script>

// JavaScript program for the above approach

// Function to generate FizzBuzz sequence
function fizzBuzz(N)
{
    // Stores count of multiples
    // of 3 and 5 respectively
    let count3 = 0;
    let count5 = 0;

    // Iterate from 1 to N
    for (let i = 1; i <= N; i++) {

        // Increment count3 by 1
        count3++;

        // Increment count5 by 1
        count5++;

        // Initialize a boolean variable
        // to check if none of the
        // condition matches
        let flag = false;

        // Check if the value of count3
        // is equal to 3
        if (count3 == 3) {
            document.write("Fizz");

            // Reset count3 to 0, and
            // set flag as True
            count3 = 0;
            flag = true;
        }

        // Check if the value of count5
        // is equal  to 5
        if (count5 == 5) {
            document.write("Buzz");

            // Reset count5 to 0, and
            // set flag as True
            count5 = 0;
            flag = true;
        }

        // If none of the condition matches
        if (!flag) {
            document.write(i);
        }

        document.write(" ");
    }
}

// Driver Code
let N = 15;
fizzBuzz(N);

// This code is contributed by unknown2108

</script>
```

## 输出

```
1 2 Fizz 4 Buzz Fizz 7 8 Fizz Buzz 11 Fizz 13 14 FizzBuzz
```

**时间复杂度:** `O(N)`
**辅助空间:** `O(1)`