# C++ 中对数组的引用

> 原文：[https://www.geeksforgeeks.org/reference-to-array-in-cpp/](https://www.geeksforgeeks.org/reference-to-array-in-cpp/)

[引用](https://www.geeksforgeeks.org/references-in-c/)到一个[数组](https://www.geeksforgeeks.org/introduction-to-arrays/)意味着在保持数组身份的同时混淆数组。对数组的引用不是 `int*` 而是 `int[]`。让我们通过讨论这两者之间的区别来详细讨论这一点。`int[]` 和 `int*` 是一样的，但是编译器对这两者的观点还是完全不同，这就很奇怪了。主要的两个区别如下：

1.  `int[]` 对编译器来说是一个数组，因此它为此提供了一个迭代器（这就是为什么我们有 For-Each 循环），但 `int*` 只是一个指向整数的指针。它可能只是一个指向整数的指针，或者是指向一个整数数组开头的指针，这完全取决于我们的视角。因此，在这种情况下没有 For-Each 循环。
2.  对编译器来说，`A` 和 `B` 是相同的数据类型，即 `int*`。这里，对编译器来说，它们只是指向地址的 `int*`。但是对编译器来说，`A` 作为数组的类型是 `int[2]`，而 `B` 作为数组的类型是 `int[3]`，这两者完全不同。再次强调，这只是编译器的视角。为了更好地理解，让这两个数组为 `int a[2]` 和 `int b[3]`。

**实现：**

*   以经典方式传递数组。
*   之后，尝试在它上面调用 For-Each 循环，你可以得到明显的区别。

**例：**

## C++

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