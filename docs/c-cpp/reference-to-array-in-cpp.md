# c++ 中对数组的引用

> 原文:[https://www.geeksforgeeks.org/reference-to-array-in-cpp/](https://www.geeksforgeeks.org/reference-to-array-in-cpp/)

[引用](https://www.geeksforgeeks.org/references-in-c/)到一个[数组](https://www.geeksforgeeks.org/introduction-to-arrays/)意味着在保持数组身份的同时混淆数组。对数组的引用不是 int*而是 int[]。让我们通过讨论这两者之间的区别来详细讨论这一点。 **int[]** 和 **int*** 是一样的，但是编译器对这两者的观点还是完全不同，这就很奇怪了。主要的两个区别如下:

1.  **int []** is an array to the compiler, so it provides an iterator for this purpose (that is why we have For-Each Loop), but **int *** is just a pointer to an integer. It may just be a pointer to an integer or a pointer to the beginning of an integer array, which depends entirely on our perspective. Therefore, there is no For-Each loop in this case.
2.  To the compiler, A and B are the same data type, that is, int*. Here, to the compiler, they are just int* pointing to the address. But for the compiler, the type of A as an array is int[2], and the type of B as an array is int[3], which are completely different. Again, it's just the perspective of compiler. For better understanding, let these two arrays be int a[2] and int b[3].

**实现:**

*   Pass-through arrays run in a classic way.
*   Later, try calling-every loop on it, and you can get obvious difference.

**例:**

## c++

```cpp
// C++ Program to demonstrate Above Approach

// Importing input output stream to take input
// and to display anything on the console
#include <iostream>

using namespace std;

// Method 1
// To print array elements
void print(int arr[], size_t n)
{

    // Iterating over elements on an array
    // using the foreach loop
    for (int element : arr) {
        // Print the elements of the array
        cout << element << " ";
    }

    // New line as all the desired elements are printed
    cout << endl;
}

// Method 2
// Main driver method
int main()
{
    // Declaring and initializing Integer array with
    // custom input entries
    int a[]{ 1, 2, 3, 4 };

    size_t size = sizeof(a) / sizeof(a[0]);

    // Calling the Method1 as created above
    // in the main) method to
    // print array elements
    print(a, size);
}
```