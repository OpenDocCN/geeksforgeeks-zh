# 检查给定的数字是否可见

> 原文: [https://www.geeksforgeeks.org/check-whether-a-given-number-is-polydivisible-or-not/](https://www.geeksforgeeks.org/check-whether-a-given-number-is-polydivisible-or-not/)

## 定义

给定一个整数 `n`，找出 `n` 是否是一个聚二可见的。在数学中，如果一个数遵循一些独特的性质，它就被称为**聚二可见**。该数字不应有任何前导零。输入数字的前 `i` 位组成的数字应能被 `i` 整除，其中 `i > 1` 且 `i <= number of digits in the input number`。如果任何一个数遵循这些性质，那么它被称为**聚二可见数**。

## 例子

```
Input: 345654
Output: 345654 is Polydivisible number.
Explanation: 
The first digit of the number is non-zero. 
The number formed by the first 2 digits(34) 
is divisible by 2. The number formed by the
first 3 digits(345) is divisible by 3. 
The number formed by the first 4 digits(3456)
is divisible by 4. The number formed by the
first 5 digits(34565) is divisible by 5. 
The number formed by the first 6 digits(345654)
is divisible by 6.     

Input: 130
Output: 130 is Not Polydivisible number.

Input: 129
Output: 129 is Polydivisible number.    
```

## 做法

思路很简单。

1.  提取数字的所有位数并存储在一个数组中。
2.  取前两位数字组成一个数，检查它是否能被 2 整除。
3.  选择下一位数字，将其附加到现有数字上，并检查该数字是否能被 `i` 整除。
4.  如果上述所有条件都满足，直到所有数字都被用完，则给定的数字是聚二可见的。

下面是上述方法的实现。

## 实现

### C++

```cpp
// CPP program to check whether
// a number is polydivisible or not
#include <bits/stdc++.h>
using namespace std;

// function to check polydivisible
// number
void check_polydivisible(int n)
{
    int N = n;
    vector<int> digit;

    // digit extraction of input number
    while (n > 0) {

        // store the digits in an array
        digit.push_back(n % 10);
        n /= 10;
    }
    reverse(digit.begin(), digit.end());

    bool flag = true;
    n = digit[0];
    for (int i = 1; i < digit.size(); i++) {

        // n contains first i digits
        n = n * 10 + digit[i];

        // n should be divisible by i
        if (n % (i + 1) != 0) {
            flag = false;
            break;
        }
    }
    if (flag)
        cout << N << " is Polydivisible number.";
    else
        cout << N << " is Not Polydivisible number.";
}

int main()
{
    int n = 345654;
    check_polydivisible(n);
}
```

### Java

```java
// Java program to check whether
// a number is polydivisible or not
import java.util.*;
import java.io.*;

class GFG {

    // function to check polydivisible
    // number
    static void check_polydivisible(int n)
    {
        int N = n;
        Vector<Integer> digit = new Vector<Integer>();

        // digit extraction of input number
        while (n > 0) {

            // store the digits in an array
            digit.add(new Integer(n % 10));
            n /= 10;
        }
        Collections.reverse(digit);

        boolean flag = true;
        n = digit.get(0);
        for (int i = 1; i < digit.size(); i++) {

            // n contains first i digits
            n = n * 10 + digit.get(i);

            // n should be divisible by i
            if (n % (i + 1) != 0) {
                flag = false;
                break;
            }
        }
        if (flag)
            System.out.println(N + " is Polydivisible number.");
        else
            System.out.println(N + " is Not Polydivisible number.");
    }

    // Driver code
    public static void main (String[] args)
    {
        int n = 345654;
        check_polydivisible(n);
    }
}
```

### Python 3

```python
# Python 3 program to check whether
# a number is polydivisible or not

# function to check polydivisible
# number
def check_polydivisible(n):
    N = n
    digit = []

    # digit extraction of input number
    while (n > 0):

        # store the digits in an array
        digit.append(n % 10)
        n //= 10

    digit.reverse()

    flag = True
    n = digit[0]
    for i in range(1, len(digit), 1):

        # n contains first i digits
        n = n * 10 + digit[i]

        # n should be divisible by i
        if (n % (i + 1) != 0):
            flag = False
            break

    if (flag):
        print(N, "is Polydivisible number.")
    else:
        print(N, "is Not Polydivisible number.")

# Driver Code
if __name__ == '__main__':
    n = 345654
    check_polydivisible(n)

# This code is contributed by
# Sahil_Shelangia
```

### C#

```csharp
// C# program to check whether
// a number is polydivisible or not
using System;
using System.Collections.Generic;

class GFG
{

    // function to check polydivisible
    // number
    static void check_polydivisible(int n)
    {
        int N = n;
        List<int> digit = new List<int>();

        // digit extraction of input number
        while (n > 0)
        {

            // store the digits in an array
            digit.Add((int)n % 10);
            n /= 10;
        }
        digit.Reverse();

        bool flag = true;
        n = digit[0];
        for (int i = 1; i < digit.Count; i++)
        {

            // n contains first i digits
            n = n * 10 + digit[i];

            // n should be divisible by i
            if (n % (i + 1) != 0)
            {
                flag = false;
                break;
            }
        }
        if (flag)
            Console.WriteLine(N +
                    " is Polydivisible number.");
        else
            Console.WriteLine(N +
                    " is Not Polydivisible number.");
    }

    // Driver code
    public static void Main (String[] args)
    {
        int n = 345654;
        check_polydivisible(n);
    }
}

// This code is contributed by Rajput-Ji
```

### JavaScript

```javascript
<script>
    // Javascript program to check whether
    // a number is polydivisible or not

    // function to check polydivisible
    // number
    function check_polydivisible(n)
    {
        let N = n;
        let digit = [];

        // digit extraction of input number
        while (n > 0)
        {

            // store the digits in an array
            digit.push(n % 10);
            n = parseInt(n / 10, 10);
        }
        digit.reverse();

        let flag = true;
        n = digit[0];
        for (let i = 1; i < digit.length; i++)
        {

            // n contains first i digits
            n = n * 10 + digit[i];

            // n should be divisible by i
            if (n % (i + 1) != 0)
            {
                flag = false;
                break;
            }
        }
        if (flag)
            document.write(N + " is Polydivisible number." + "</br>");
        else
            document.write(N + " is Not Polydivisible number.");
    }

    let n = 345654;
      check_polydivisible(n);

</script>
```

## 输出

```
345654 is Polydivisible number.
```