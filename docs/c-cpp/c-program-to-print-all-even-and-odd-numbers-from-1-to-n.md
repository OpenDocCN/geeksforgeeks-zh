# C++ 程序打印所有从 1 到 N 的偶数和奇数

> 原文:[https://www . geesforgeks . org/c-program-to-print-all-偶数和奇数-从-1 到-n/](https://www.geeksforgeeks.org/c-program-to-print-all-even-and-odd-numbers-from-1-to-n/)

给定一个数字 N，任务是从 1 开始打印 N 个偶数和 N 个奇数。

**示例:**

```cpp
Input: N = 5
Output: 
Even: 2 4 6 8 10
Odd: 1 3 5 7 9

Input: N = 3
Output: 
Even: 2 4 6
Odd: 1 3 5

```

**进场:**

1.  **偶数:**
    *   偶数是可被 2 整除的数。
    *   要打印从 1 到 N 的偶数，请从 1 开始遍历每个数字。
    *   检查这些数字是否能被 2 整除。
    *   如果是真的，打印那个号码。
2.  **For Odd numbers:**
    *   奇数是不能被 2 整除的数。
    *   要打印从 1 到 N 的奇数，请从 1 开始遍历每个数字。
    *   检查这些数字是否不能被 2 整除。
    *   如果是真的，打印那个号码。

    下面是上述方法的实现:

    ```cpp
    // C++ program to print all Even
    // and Odd numbers from 1 to N

    #include <bits/stdc++.h>
    using namespace std;

    // Function to print even numbers
    void printEvenNumbers(int N)
    {

        cout << "Even: ";
        for (int i = 1; i <= 2 * N; i++) {

            // Numbers that are divisible by 2
            if (i % 2 == 0)
                cout << i << " ";
        }
    }

    // Function to print odd numbers
    void printOddNumbers(int N)
    {

        cout << "\nOdd: ";
        for (int i = 1; i <= 2 * N; i++) {

            // Numbers that are not divisible by 2
            if (i % 2 != 0)
                cout << i << " ";
        }
    }

    // Driver code
    int main()
    {

        int N = 5;

        printEvenNumbers(N);
        printOddNumbers(N);

        return 0;
    }
    ```

    **Output:**

    ```cpp
    Even: 2 4 6 8 10 
    Odd: 1 3 5 7 9

    ```