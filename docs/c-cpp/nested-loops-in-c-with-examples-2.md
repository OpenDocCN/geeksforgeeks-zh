# c++ 中的嵌套循环，示例

> 原文:[https://www . geesforgeks . org/nested-loops-in-c-with-examples-2/](https://www.geeksforgeeks.org/nested-loops-in-c-with-examples-2/)

**嵌套循环**是指另一个循环语句中的一个[循环语句](https://www.geeksforgeeks.org/loops-in-c-and-cpp/)。这就是为什么嵌套循环也被称为“循环内循环”。

**嵌套 for 循环的语法:**

```cpp
for ( initialization; condition; increment ) {

   for ( initialization; condition; increment ) {

      // statement of inside loop
   }

   // statement of outer loop
}

```

**嵌套 While 循环的语法:**

```cpp
while(condition) {

   while(condition) {

      // statement of inside loop
   }

   // statement of outer loop
}

```

**嵌套边做边循环的语法:**

```cpp
do{

   do{

      // statement of inside loop
   }while(condition);

   // statement of outer loop
}while(condition);

```

> **注意:**没有规定循环必须嵌套在自己的类型中。事实上，可以有任何类型的循环嵌套在任何类型和任何级别。

**语法:**

```cpp
do{

   while(condition) {

      for ( initialization; condition; increment ) {

         // statement of inside for loop
      }

      // statement of inside while loop
   }

   // statement of outer do-while loop
}while(condition);

```

下面是一些演示嵌套循环使用的示例:

**示例 1:** 下面的程序使用嵌套的 for 循环来打印一个 3×3 的 2D 矩阵。

```cpp
// C++ program that uses nested for loop
// to print a 2D matrix

#include <bits/stdc++.h>
using namespace std;

#define ROW 3
#define COL 3

// Driver program
int main()
{

    int i, j;

    // Declare the matrix
    int matrix[ROW][COL] = { { 1, 2, 3 },
                             { 4, 5, 6 },
                             { 7, 8, 9 } };
    cout << "Given matrix is \n";

    // Print the matrix using nested loops
    for (i = 0; i < ROW; i++) {

        for (j = 0; j < COL; j++)
            cout << matrix[i][j];

        cout << "\n";
    }

    return 0;
}
```

**Output:**

```cpp
Given matrix is 
123
456
789

```

**示例 2:** 下面的程序使用嵌套 for 循环打印一个数的所有质因数。

```cpp
// C++ Program to print all prime factors
// of a number using nested loop

#include <bits/stdc++.h>
using namespace std;

// A function to print all prime factors of a given number n
void primeFactors(int n)
{
    // Print the number of 2s that divide n
    while (n % 2 == 0) {
        cout << 2;
        n = n / 2;
    }

    // n must be odd at this point. So we can skip
    // one element (Note i = i +2)
    for (int i = 3; i <= sqrt(n); i = i + 2) {
        // While i divides n, print i and divide n
        while (n % i == 0) {
            cout << i;
            n = n / i;
        }
    }

    // This condition is to handle the case when n
    // is a prime number greater than 2
    if (n > 2)
        cout << n;
}

/* Driver program to test above function */
int main()
{
    int n = 315;
    primeFactors(n);
    return 0;
}
```

**Output:**

```cpp
3357

```