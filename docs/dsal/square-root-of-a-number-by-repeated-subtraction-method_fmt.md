# 重复减法求一个数的平方根

> 原文：[https://www.geeksforgeeks.org/square-root-of-a-number-by-repeated-subtraction-method/](https://www.geeksforgeeks.org/square-root-of-a-number-by-repeated-subtraction-method/)

给定一个整数 `N`，任务是只通过重复减法找到其完美的[平方根](https://www.geeksforgeeks.org/square-root-of-an-integer/)。

**例:**

> **输入** : `N = 25`
> **输出** : `5`
> **输入** : `N = 841`
> **输出** : `29`

**巴比伦法和二分搜索法法:**基于[巴比伦法](https://www.geeksforgeeks.org/square-root-of-a-perfect-square/)和[二分搜索法](https://www.geeksforgeeks.org/binary-search/)的方法参考[整数平方根](https://www.geeksforgeeks.org/square-root-of-an-integer/)。

**重复减法方法:**
按照以下步骤解决问题:

*   前 `N` 个奇数自然数之和等于 `N^2`。
*   基于上述事实，需要执行从 1 开始的奇数的重复减法，直到 `N` 变成 `0`。
*   这个过程中使用的奇数计数将给出数字 `N` 的平方根。

> **图解:**
> `N = 81`
> **第一步:** `81-1=80`
> **第二步:** `80-3=77`
> **第三步:** `77-5=72`
> **第四步:** `72-7=65`
> **第五步:** `65-9=56`
> **第六步:** `56-11=45`
> **第七步:** `45-13=32`
> **第八步:** `32-15=17`
> **第九步:** `17-17=0`
> 由于在第 9 步变为 0，因此平方根为 9。

下面是上述方法的实现。

## C++

```cpp
// C++ implementation of
// the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to return the square
// root of the given number
int SquareRoot(int num)
{
    int count = 0;

    for (int n = 1; n <= num; n += 2) {

        // Subtract n-th odd number
        num = num - n;
        count += 1;
        if (num == 0)
            break;
    }

    // Return the result
    return count;
}

// Driver Code
int main()
{
    int N = 81;
    cout << SquareRoot(N);
}
```

## Java

```java
// Java implementation of
// the above approach
class GFG{

// Function to return the square
// root of the given number
public static int SquareRoot(int num)
{
    int count = 0;

    for(int n = 1; n <= num; n += 2)
    {

       // Subtract n-th odd number
       num = num - n;
       count += 1;
       if (num == 0)
           break;
    }

    // Return the result
    return count;
}

// Driver code
public static void main(String[] args)
{
    int N = 81;
    System.out.println(SquareRoot(N));
}
}

// This code is contributed by divyeshrabadiya07
```

## Python 3

```python
# Python3 implementation of the
# above approach

# Function to return the square
# root of the given number
def SquareRoot(num):

    count = 0
    for n in range(1, num + 1, 2):

        # Subtract n-th odd number
        num = num - n
        count = count + 1
        if (num == 0):
            break

    # Return the result
    return count

# Driver Code
N = 81
print(SquareRoot(N))

# This code is contributed by Sanjit_Prasad
```

## C#

```csharp
// C# implementation of
// the above approach
using System;

class GFG{

// Function to return the square
// root of the given number
public static int SquareRoot(int num)
{
    int count = 0;

    for(int n = 1; n <= num; n += 2)
    {

        // Subtract n-th odd number
        num = num - n;
        count += 1;
        if (num == 0)
            break;
    }

    // Return the result
    return count;
}

// Driver code
public static void Main()
{
    int N = 81;

    Console.Write(SquareRoot(N));
}
}

// This code is contributed by chitranayal
```

## JavaScript

```javascript
<script>

// Javascript implementation of
// the above approach

// Function to return the square
// root of the given number
function SquareRoot(num)
{
    let count = 0;

    for (let n = 1; n <= num; n += 2) {

        // Subtract n-th odd number
        num = num - n;
        count += 1;
        if (num == 0)
            break;
    }

    // Return the result
    return count;
}

// Driver Code

    let N = 81;
    document.write(SquareRoot(N));

// This code is contributed by Mayank Tyagi

</script>
```

### 输出

```
9
```

**时间复杂度:** `O(N)`
**辅助空间:** `O(1)`