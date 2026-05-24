# 在 C++ 中使用 STL 的数组的所有反向排列

> 原文:[https://www . geeksforgeeks . org/all-reverse-置换数组-使用-stl-in-c/](https://www.geeksforgeeks.org/all-reverse-permutations-of-an-array-using-stl-in-c/)

给定一个数组，任务是在 C++ 中使用 STL 打印或显示这个数组的所有反向排列。反向排列意味着，对于数组{1，2，3}:

```cpp
[forward permutations:](https://www.geeksforgeeks.org/all-permutations-of-an-array-using-stl-in-c/)
1  2  3  
1  3  2  
2  1  3  
2  3  1  
3  1  2  
3  2  1  

reverse permutations:
3 2 1
3 1 2
2 3 1
2 1 3
1 3 2
1 2 3

```

**例:**

```cpp
Input: a[] = {1, 2, 3}
Output:
3 2 1
3 1 2
2 3 1
2 1 3
1 3 2
1 2 3

Input: a[] = {10, 20, 30, 40}
Output:
Possible permutations are:
40 30 20 10 
40 30 10 20 
40 20 30 10 
40 20 10 30 
40 10 30 20 
40 10 20 30 
30 40 20 10 
30 40 10 20 
30 20 40 10 
30 20 10 40 
30 10 40 20 
30 10 20 40 
20 40 30 10 
20 40 10 30 
20 30 40 10 
20 30 10 40 
20 10 40 30 
20 10 30 40 
10 40 30 20 
10 40 20 30 
10 30 40 20 
10 30 20 40 
10 20 40 30 
10 20 30 40 

```

**方法:**可以使用 STL 中提供的[prev _ arrangement()](https://www.geeksforgeeks.org/stdnext_permutation-prev_permutation-c/)函数找到数组的下一个可能的逆序排列。

**语法:**

```cpp
bool prev_permutation (BidirectionalIterator first,
                       BidirectionalIterator last);

```

以下是上述方法的实现:

```cpp
// C++ program to display all permutations
// in reverse order
// of an array using STL in C++

#include <bits/stdc++.h>
using namespace std;

// Function to display the array
void display(int a[], int n)
{
    for (int i = 0; i < n; i++) {
        cout << a[i] << " ";
    }
    cout << endl;
}

// Function to find the permutations
void findPermutations(int a[], int n)
{

    // Sort the given array
    sort(a, a + n);

    reverse(a, a + n);

    // Find all possible permutations
    cout << "Possible permutations are:\n";
    do {
        display(a, n);
    } while (prev_permutation(a, a + n));
}

// Driver code
int main()
{

    int a[] = { 10, 20, 30, 40 };

    int n = sizeof(a) / sizeof(a[0]);

    findPermutations(a, n);

    return 0;
}
```

**输出:**

```cpp
Possible permutations are:
40 30 20 10 
40 30 10 20 
40 20 30 10 
40 20 10 30 
40 10 30 20 
40 10 20 30 
30 40 20 10 
30 40 10 20 
30 20 40 10 
30 20 10 40 
30 10 40 20 
30 10 20 40 
20 40 30 10 
20 40 10 30 
20 30 40 10 
20 30 10 40 
20 10 40 30 
20 10 30 40 
10 40 30 20 
10 40 20 30 
10 30 40 20 
10 30 20 40 
10 20 40 30 
10 20 30 40

```

**相关文章:** [在 C++ 中使用 STL 的数组的所有排列](https://www.geeksforgeeks.org/all-permutations-of-an-array-using-stl-in-c/)