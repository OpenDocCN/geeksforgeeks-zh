# c++ 中的模板非类型实参

> 原文:[https://www . geesforgeks . org/template-non-type-arguments-in-c/](https://www.geeksforgeeks.org/template-non-type-arguments-in-c/)

**先决条件:**[c++ 中的模板](https://www.geeksforgeeks.org/templates-cpp/)

通常，带有单个参数的 C++ 模板如下所示:

> 模板<typename template_name=""></typename>

但是已经看到一个模板可以有多个参数。同样的语法是:

> 模板<class t1="" class="" t2="" t3="" tn=""></class>
> 
> 其中，n 是参数的个数。

也可以使用非类型实参(basic/ [派生数据类型](https://www.geeksforgeeks.org/derived-data-types-in-c/))，即除了类型实参 T，还可以使用其他实参如[字符串](https://www.geeksforgeeks.org/string-data-structure/)、[函数](https://www.geeksforgeeks.org/functions-in-c/)名称、[常量表达式](https://www.geeksforgeeks.org/understanding-constexper-specifier-in-c/)、[内置数据类型](https://www.geeksforgeeks.org/c-data-types/)。

**例 1:**

```cpp
template <class T, int size>
class Array {
private:

    // Automatic array initialization
    T Arr[size]
    .....
    .....
};

```

**说明:**

在上面的例子中，模板提供了[数组](https://www.geeksforgeeks.org/introduction-to-arrays/)的大小作为参数。这意味着编译器在[编译时](https://www.geeksforgeeks.org/runtime-and-compile-time-constants-in-c/)本身就知道[数组](https://www.geeksforgeeks.org/array-data-structure/)的*大小*。每当创建模板类时，都必须指定参数。

**例 2:**

```cpp
// Array of 10 integers
Array<int, 10> a1

// Array of 5 double type numbers
Array<double, 5> a2

// String of size 9 
Array<char, 10>  a3 

where *size* is given as an argument to the template class.

```

以下是允许的参数:

*   常量表达式
*   [具有](https://www.geeksforgeeks.org/address-function-c-cpp/)[外部链接的功能](https://www.geeksforgeeks.org/internal-linkage-external-linkage-c/)或对象的地址
*   [静态类成员](https://www.geeksforgeeks.org/static-data-members-c/)的地址。

下面是说明非类型模板的程序:

## C++

```cpp
// C++ program to implement bubble sort
// by using Non-type as function parameters
#include <iostream>
using namespace std;

// Function to swap two numbers
template <class T>
void swap_(T* x, T* y)
{
    T temp = *x;
    *x = *y;
    *y = temp;
}

// Function to implement the Bubble Sort
template <class T, int size>
void bubble_sort(T arr[])
{
    for (int i = 0; i < size - 1; i++) {

        // Last i elements are already
        // in place
        for (int j = 0; j < size - i - 1; j++) {
            if (arr[j] > arr[j + 1]) {

                // Swap operation
                swap_(&arr[j], &arr[j + 1]);
            }
        }
    }
}

// Function to print an array
template <class T, int size>
void printArray(T arr[])
{
    int i;
    for (i = 0; i < size - 1; i++) {
        cout << arr[i] << ", ";
    }

    cout << arr[size - 1] << endl;
}

// Driver Code
int main()
{
    // Given array arr[]
    float arr[] = { 1.1, 1.2, 0.3, 4.55, 1.56, 0.6 };
    const int size_arr = sizeof(arr) / sizeof(arr[0]);

    // Size of the array passed as
    // an argument to the function
    bubble_sort<float, size_arr>(arr);

    cout << "Sorted Array is: ";
    printArray<float, size_arr>(arr);

    return 0;
}
```

**Output:**

```cpp
Sorted Array is: 0.3, 0.6, 1.1, 1.2, 1.56, 4.55

```