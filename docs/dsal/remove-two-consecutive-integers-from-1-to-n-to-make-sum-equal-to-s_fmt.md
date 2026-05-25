# 去掉 1 到 N 两个连续的整数，使和等于 S

> 原文: [https://www.geeksforgeeks.org/remove-two-consecutive-integers-from-1-to-n-to-make-sum-equal-to-s/](https://www.geeksforgeeks.org/remove-two-consecutive-integers-from-1-to-n-to-make-sum-equal-to-s/)

给定一个和 `S` 和一个整数 `N`，任务是去掉从 1 到 `N` 的两个连续整数，使和等于 `S`。

**示例:**

```
Input: N = 4, S = 3
Output: Yes
sum(1, 2, 3, 4) = 10, 
remove 3 and 4 from 1 to N
now sum(1, 2) = 3 = S
Hence by removing 3 and 4 we got sum = S

Input: N = 5, S =3
Output: No
Its not possible to remove two elements
from 1 to N such that new sum is 3
```

## 方法 1

*   **时间复杂度:** `O(n)`
*   **空间复杂度:** `O(n)`

1.  创建一个包含 1 到 `n` 个元素的数组。
2.  每次去掉两个连续的元素，检查 `N` 个自然数之和与两个去掉的元素之和之差为 `s`。
3.  `N` 个自然数之和可以用公式 `sum = (n)(n + 1) / 2` 计算。

## 方法 2

1.  我们知道，`N` 个自然数的和可以用公式 `sum = (n)(n + 1) / 2` 来计算。
2.  根据问题陈述，我们需要从 1 到 `N` 中去掉两个整数，这样剩下的整数之和就是 `s`。
3.  假设要去掉的两个连续整数为 `i` 和 `i + 1`。
4.  因此，
    ```
    required sum = S = (n)(n + 1) / 2 - (i) - (i + 1)
                   S = (n)(n + 1) / 2 - (2i - 1)

    Therefore,
    i = ((n)(n + 1) / 4) - ((S + 1) / 2)
    ```
5.  因此我用上面的公式。
6.  如果 `i` 是整数，那么答案是是，否则是否。

下面是上述方法的实现:

### C++

```cpp
// C++ program remove two consecutive integers
// from 1 to N to make sum equal to S

#include <bits/stdc++.h>
using namespace std;

// Function to find the numbers
// to be removed
float findNumber(int N, int S)
{
    // typecast appropriately
    // so that answer is float
    float i = (((float)(N) * (float)(N + 1)) / 4)
              - ((float)(S + 1) / 2);

    // return the obtained result
    return i;
}

void check(int N, int S)
{
    float i = findNumber(N, S);

    // Convert i to integer
    int integerI = (int)i;

    // If i is an integer is 0
    // then answer is Yes
    if (i - integerI == 0)
        cout << "Yes: "
             << integerI << ", "
             << integerI + 1
             << endl;
    else
        cout << "No"
             << endl;
}

// Driver code
int main()
{
    int N = 4, S = 3;
    check(N, S);

    N = 5, S = 3;
    check(N, S);

    return 0;
}
```

### Java

```java
// Java program remove two consecutive integers 
// from 1 to N to make sum equal to S

class GFG 
{
    // Function to find the numbers 
    // to be removed 
    static float findNumber(int N, int S) 
    {
        // typecast appropriately 
        // so that answer is float 
        float i = (((float)(N) * (float)(N + 1)) / 4) 
                - ((float)(S + 1) / 2);

        // return the obtained result 
        return i; 
    }

    static void check(int N, int S) 
    {
        float i = findNumber(N, S);

        // Convert i to integer 
        int integerI = (int)i;

        // If i is an integer is 0 
        // then answer is Yes 
        if (i - integerI == 0) 
            System.out.println("Yes: " + integerI + 
                            ", " + (integerI + 1)) ;
        else
            System.out.println("No");
    }

    // Driver code 
    public static void main (String[] args)
    {
        int N = 4, S = 3; 
        check(N, S);

        N = 5; S = 3; 
        check(N, S);
    } 
}

// This code is contributed by AnkitRai01
```

### Python 3

```python
# Python3 program remove two consecutive integers 
# from 1 to N to make sum equal to S

# Function to find the numbers 
# to be removed 
def findNumber(N, S) :
    # typecast appropriately 
    # so that answer is float 
    i = (((N) * (N + 1)) / 4) - ((S + 1) / 2);

    # return the obtained result 
    return i;

def check(N, S) :
    i = findNumber(N, S);

    # Convert i to integer 
    integerI = int(i);

    # If i is an integer is 0 
    # then answer is Yes 
    if (i - integerI == 0) :
        print("Yes:", integerI,
                 ",", integerI + 1); 
    else :
        print("No");

# Driver code 
if __name__ == "__main__" :
    N = 4;
    S = 3; 
    check(N, S);

    N = 5;
    S = 3; 
    check(N, S);

# This code is contributed by AnkitRai01
```

### C\#

```csharp
// C# program remove two consecutive integers 
// from 1 to N to make sum equal to S 
using System;

class GFG 
{
    // Function to find the numbers 
    // to be removed 
    static float findNumber(int N, int S) 
    {
        // typecast appropriately 
        // so that answer is float 
        float i = (((float)(N) * (float)(N + 1)) / 4) 
                - ((float)(S + 1) / 2);

        // return the obtained result 
        return i; 
    }

    static void check(int N, int S) 
    { 
        float i = findNumber(N, S);

        // Convert i to integer 
        int integerI = (int)i;

        // If i is an integer is 0 
        // then answer is Yes 
        if (i - integerI == 0) 
            Console.WriteLine("Yes: " + integerI + 
                            ", " + (integerI + 1)) ; 
        else
            Console.WriteLine("No"); 
    }

    // Driver code 
    public static void Main() 
    {
        int N = 4, S = 3; 
        check(N, S);

        N = 5; S = 3; 
        check(N, S); 
    } 
}

// This code is contributed by AnkitRai01 
```

**输出:**

```
Yes: 3, 4
No
```

**时间复杂度:** `O(1)`
**空间复杂度:** `O(1)`