# 检查 X 是否可以给队列中的每个人找钱

> 原文:[https://www . geeksforgeeks . org/check-if-x-can-change-to-even-in-the-queue/](https://www.geeksforgeeks.org/check-if-x-can-give-change-to-every-person-in-the-queue/)

给定 N 个整数的数组，其中 A <sub>i</sub> 表示第一个人拥有的纸币。可能的货币有 5、10 和 20。所有的 N 个人都在排队等着从 X 那里买一个价值 5 卢比的冰淇淋。最初，X 的初始余额为 0。检查 X 是否能够为所有等待购买冰淇淋的人提供零钱。

**示例:**

> **输入:** a[] = {5，5，5，10，20}
> **输出:** YES
> 第四个人来买冰淇淋的时候，X 有三个 Rs 5
> 零钱，于是 X 给他 1，现在第五个人
> 来买冰淇淋的时候，X 有两个 Rs 5 和一个 Rs 10 纸币，于是他
> 给他一个 Rs 10 和一个 Rs 5 纸币。
> 
> **输入:** a[] = {5，10，10，20 }
> T3】输出:否

**方法**是记录*卢比 5* 和*卢比 10* 的货币数量。不会使用 20 卢比的货币，因为这是一个人能给的最高货币，因此不能作为零钱给。初始化两个变量来计数 5 卢比(五个计数)和 10 卢比(十个计数)。如果此人有 10 卢比的货币和 5 个计数> 0，则减少 5 个计数并增加 10 个计数。如果 X 没有 Rs 5，那么 X 就不能给这个人所需的零钱。如果这个人有 5 美元的纸币，将 5 计数增加 1。如果此人有 20 卢比，则有三个条件:

*   如果五个计数> 0，十个计数> 0，则两者都减少。
*   否则，如果五个计数> = 3，则将五个计数减少三。
*   否则，返回 false。

如果队列中的所有人都得到零钱，则打印“是”，否则打印“否”。

以下是上述想法的实现。

## C++

```cpp
// C++ program to check whether X can give change
// to every person in the Queue
#include <bits/stdc++.h>
using namespace std;

// Function to check if every person will
// get the change from X
int isChangeable(int notes[], int n)
{
    // To count the 5$ and 10& notes
    int fiveCount = 0;
    int tenCount = 0;

    // Serve the customer in order
    for (int i = 0; i < n; i++) {

        // Increase the number of 5$ note by one
        if (notes[i] == 5)
            fiveCount++ ;
        else if (notes[i] == 10) {

            // decrease the number of note 5$ and
            // increase 10$ note by one
            if (fiveCount > 0) {
                fiveCount--;
                tenCount++ ;
            }
            else
                return 0;
        }
        else {

            // decrease 5$ and 10$ note by one
            if (fiveCount > 0 && tenCount > 0) {
                fiveCount--;
                tenCount--;
            }

            // decrease 5$ note by three
            else if (fiveCount >= 3) {
                fiveCount -= 3;
            }
            else
                return 0;
        }
    }

    return 1;
}
// Driver Code
int main()
{
    // queue of customers with available notes.
    int a[] = { 5, 5, 5, 10, 20 };
    int n = sizeof(a) / sizeof(a[0]);

    // Calling function
    if (isChangeable(a, n))
        cout << "YES";
    else
        cout << "NO";

    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
// Java program to check
// whether X can give
// change to every person
// in the Queue
import java.io.*;

class GFG
{

// Function to check if
// every person will
// get the change from X
static int isChangeable(int notes[],
                        int n)
{
    // To count the 5$
    // and 10& notes
    int fiveCount = 0;
    int tenCount = 0;

    // Serve the customer
    // in order
    for (int i = 0; i < n; i++)
    {

        // Increase the number
        // of 5$ note by one
        if (notes[i] == 5)
            fiveCount++ ;
        else if (notes[i] == 10)
        {

            // decrease the number
            // of note 5$ and
            // increase 10$ note by one
            if (fiveCount > 0)
            {
                fiveCount--;
                tenCount++ ;
            }
            else
                return 0;
        }
        else
        {

            // decrease 5$ and
            // 10$ note by one
            if (fiveCount > 0 &&
                tenCount > 0)
            {
                fiveCount--;
                tenCount--;
            }

            // decrease 5$
            // note by three
            else if (fiveCount >= 3)
            {
                fiveCount -= 3;
            }
            else
                return 0;
        }
    }

    return 1;
}

// Driver Code
public static void main (String[] args)
{

// queue of customers
// with available notes.
int a[] = {5, 5, 5, 10, 20};
int n = a.length;

// Calling function
if (isChangeable(a, n) > 0)
    System.out.print("YES");
else
    System.out.print("NO");
}
}

// This code is contributed
// by anuj_67.
```

## 蟒蛇 3

```cpp
# Python program to check whether X can
# give change to every person in the Queue

# Function to check if every person
# will get the change from X
def isChangeable(notes, n):

    # To count the 5$ and 10& notes
    fiveCount = 0
    tenCount = 0

    # Serve the customer in order
    for i in range(n):

        # Increase the number of 5$ note by one
        if (notes[i] == 5):
            fiveCount += 1
        elif(notes[i] == 10):

            # decrease the number of note 5$
            # and increase 10$ note by one
            if (fiveCount > 0):
                fiveCount -= 1
                tenCount += 1
            else:
                return 0
        else:

            # decrease 5$ and 10$ note by one
            if (fiveCount > 0 and tenCount > 0):
                fiveCount -= 1
                tenCount -= 1

            # decrease 5$ note by three
            elif (fiveCount >= 3):
                fiveCount -= 3
            else:
                return 0
    return 1

# Driver Code

# queue of customers with available notes.
a = [5, 5, 5, 10, 20 ]
n = len(a)

# Calling function
if (isChangeable(a, n)):
    print("YES")
else:
    print("NO")

# This code is contributed by PrinciRaj1992
```

## C#

```cpp
// C# program to check
// whether X can give
// change to every person
// in the Queue
using System;

class GFG
{

// Function to check if
// every person will
// get the change from X
static int isChangeable(int []notes,
                        int n)
{
    // To count the 5$
    // and 10& notes
    int fiveCount = 0;
    int tenCount = 0;

    // Serve the customer
    // in order
    for (int i = 0; i < n; i++)
    {

        // Increase the number
        // of 5$ note by one
        if (notes[i] == 5)
            fiveCount++ ;
        else if (notes[i] == 10)
        {

            // decrease the number
            // of note 5$ and
            // increase 10$ note by one
            if (fiveCount > 0)
            {
                fiveCount--;
                tenCount++ ;
            }
            else
                return 0;
        }
        else
        {

            // decrease 5$ and
            // 10$ note by one
            if (fiveCount > 0 &&
                tenCount > 0)
            {
                fiveCount--;
                tenCount--;
            }

            // decrease 5$
            // note by three
            else if (fiveCount >= 3)
            {
                fiveCount -= 3;
            }
            else
                return 0;
        }
    }

    return 1;
}

// Driver Code
public static void Main ()
{

// queue of customers
// with available notes.
int []a = {5, 5, 5, 10, 20};
int n = a.Length;

// Calling function
if (isChangeable(a, n) > 0)
    Console.WriteLine("YES");
else
    Console.WriteLine("NO");
}
}

// This code is contributed
// by anuj_67.
```

## java 描述语言

```cpp
<script>
    // Javascript program to check
    // whether X can give
    // change to every person
    // in the Queue

    // Function to check if
    // every person will
    // get the change from X
    function isChangeable(notes, n)
    {
        // To count the 5$
        // and 10& notes
        let fiveCount = 0;
        let tenCount = 0;

        // Serve the customer
        // in order
        for (let i = 0; i < n; i++)
        {

            // Increase the number
            // of 5$ note by one
            if (notes[i] == 5)
                fiveCount++ ;
            else if (notes[i] == 10)
            {

                // decrease the number
                // of note 5$ and
                // increase 10$ note by one
                if (fiveCount > 0)
                {
                    fiveCount--;
                    tenCount++ ;
                }
                else
                    return 0;
            }
            else
            {

                // decrease 5$ and
                // 10$ note by one
                if (fiveCount > 0 &&
                    tenCount > 0)
                {
                    fiveCount--;
                    tenCount--;
                }

                // decrease 5$
                // note by three
                else if (fiveCount >= 3)
                {
                    fiveCount -= 3;
                }
                else
                    return 0;
            }
        }

        return 1;
    }

    // queue of customers
    // with available notes.
    let a = [5, 5, 5, 10, 20];
    let n = a.length;

    // Calling function
    if (isChangeable(a, n) > 0)
        document.write("YES");
    else
        document.write("NO");

</script>
```

**Output:** 

```cpp
YES
```