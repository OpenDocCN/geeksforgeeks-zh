# 用位加两个无符号数

> 原文:[https://www . geesforgeks . org/add-two-unsigned-numbers-using-bits/](https://www.geeksforgeeks.org/add-two-unsigned-numbers-using-bits/)

给定两个无符号整数(最大可能输入 32 位)。任务是使用位操作将两个数字相加。

**示例:**

```cpp
Input: n1 = 12, n2 = 34
Output: 46

Input: n1 = 12564 n2 = -1
Output: 12563 
```

**方法:**因为我们知道除了位加法

*   1+0=1
*   0+1=1
*   0+0=0
*   1+1=0 进位 1
*   if(进位==1) 1+1=1 进位 1

用 C++ 中的[位集函数](https://www.geeksforgeeks.org/c-bitset-and-its-application/)表示整数。它的行为就像一个在第 0 个索引处存储最低有效位的数组，当我们打印这样一个数组时，它会以相反的格式打印二进制表示。根据位添加属性从右开始添加每个位，并存储在第三个位集中。函数 [to_ulong()](https://www.geeksforgeeks.org/stdbitsetto_ullong-and-stdbitsetto_ulong/) 用于将一个位集形式转换为其十进制形式。
以下是上述办法的实施情况。

## C++

```cpp
#include <bits/stdc++.h>
#define M 32
using namespace std;

// Function to add two bitset
int binAdd(bitset<M> atemp, bitset<M> btemp)
{
    // To store the bits of answer
    bitset<M> ctemp;
    for (int i = 0; i < M; i++)
        ctemp[i] = 0;

    // Initialize carry to 0
    int carry = 0;

    for (int i = 0; i < M; i++) {

        // Both bits are zero
        if (atemp[i] + btemp[i] == 0) {

            if (carry == 0)
                ctemp[i] = 0;

            else {
                ctemp[i] = 1;
                carry = 0;
            }
        }

        // Any of the one bit is 1
        else if (atemp[i] + btemp[i] == 1) {

            if (carry == 0)
                ctemp[i] = 1;
            else {
                ctemp[i] = 0;
            }
        }

        // Both bits are 1
        else {
            if (carry == 0) {
                ctemp[i] = 0;
                carry = 1;
            }
            else {
                ctemp[i] = 1;
            }
        }
    }

    // To convert bitset into
    // decimal equivalent
    return ctemp.to_ulong();
}

// Driver Code
int main()
{
    int number1, number2;
    number1 = 12;
    number2 = 34;

    // Converting number 1 to bitset form
    bitset<M> num1(number1);

    // Converting number 2 to bitset form
    bitset<M> num2(number2);

    cout << binAdd(num1, num2) << endl;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
// Java program to add two unsigned numbers using bits

import java.util.*; // Needed for BitSet class.

class GFG {
    static final int M = 32;

    // Function to add two BitSets. Returns long number.
    static long binAdd(BitSet atemp, BitSet btemp)
    {
        // Initialize a 3rd BitSet to store the answer.
        BitSet ctemp = new BitSet(M);
        for (int i = 0; i < M; i++) {
            ctemp.set(i, false);
        }

        // Initialize carry to ZERO.
        int carry = 0;

        for (int i = 0; i < M; i++) {

            // Both of the bits are ZERO.
            if (atemp.get(i) == false
                && // Uses the "conditional-AND" operator
                   // (also known as "short-circuit AND")
                   // which is more efficient than the
                   // ordinary & bitwise operator.
                btemp.get(i) == false) {

                if (carry == 0) {
                    ctemp.set(i, false);
                }
                else {
                    ctemp.set(i, true);
                    carry = 0;
                }
            }

            // Either of the bits is a ONE but not both.
            else if (atemp.get(i) == true
                     ^ // Uses the "XOR" (exclusive-OR)
                       // operator to ensure that ONLY
                       // one of the two bits is a ONE.
                     btemp.get(i) == true) {

                if (carry == 0) {
                    ctemp.set(i, true);
                }
                else {
                    ctemp.set(i, false);
                }
            }

            // Both of the bits are ONE.
            else // By process of elimination we do not need
                 // to code for the (TRUE & TRUE) condition.
            {
                if (carry == 0) {
                    ctemp.set(i, false);
                    carry = 1;
                }
                else {
                    ctemp.set(i, true);
                }
            }
        }

        // Returns the 3rd BitSet as its decimal equivalent
        // number in long format.
        return ctemp.toLongArray()[0];
    }

    // Driver Code
    public static void main(String args[])
    {
        int number1, number2;

        // binary literal for decimal 15.
        number1 = 15;
        // binary literal for decimal 85.
        number2 = 1;
        // result should be decimal 100.

        // Converting number1 to BitSet form.
        BitSet num1
            = BitSet.valueOf(new long[] { number1 });

        // Converting number2 to BitSet form.
        BitSet num2
            = BitSet.valueOf(new long[] { number2 });

        System.out.printf("%d plus %d equals %d", number1,
                          number2, binAdd(num1, num2));
        System.out.println();
    }
}

// This code is contributed by Arnab Kundu.
// Modified by Matt Ambrose.
```

## 蟒蛇 3

```cpp
# Python3 implementation of the approach

# Function to convert given Integer
# to list of bits of length M
def bitset(num):

    return [int(x) for x in format(num, '032b')]

# Function to add two bitset
def binAdd(atemp, btemp):

    # To store the bits of answer
    ctemp = [0] * M

    # Initialize carry to 0
    carry = 0
    for i in range(0, M):

        # Both bits are zero
        if atemp[i] + btemp[i] == 0:

            if carry == 0:
                ctemp[i] = 0

            else:
                ctemp[i] = 1
                carry = 0

        # Any of the one bit is 1
        elif atemp[i] + btemp[i] == 1:

            if carry == 0:
                ctemp[i] = 1
            else:
                ctemp[i] = 0

        # Both bits are 1
        else:
            if carry == 0:
                ctemp[i] = 0
                carry = 1

            else:
                ctemp[i] = 1

    # To convert bitset into string and then
    # convert string to its decimal equivalent
    temp = ''.join([str(x) for x in ctemp])
    return int(temp, 2)

# Driver Code
if __name__ == "__main__":

    number1, number2 = 12, 34
    M = 32

    # Converting number 1 to bitset form
    num1 = bitset(number1)

    # Converting number 2 to bitset form
    num2 = bitset(number2)

    print(binAdd(num1, num2))

# This code is contributed by Rituraj Jain
```

**Output**

```cpp
46

```