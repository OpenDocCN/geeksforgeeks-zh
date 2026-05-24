# 使用 STL 在 C++ 中数组积

> 原文:[https://www.geeksforgeeks.org/array-product-c-using-stl/](https://www.geeksforgeeks.org/array-product-c-using-stl/)

在 C++ 中，我们可以使用[累加()](https://www.geeksforgeeks.org/numeric-header-in-c-stl-set-1-accumulate-and-partial_product/)和乘法<T4()快速找到数组乘积。

initialProduct 指定要考虑的初始值。

对于乘法，初始值为 1。

例如:数组= [5，10，15]，

因此，乘积= 1 x 5 x 10 x 15 = 750(注意这里 1 是初始值)

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to find array product
#include <iostream>
#include <numeric>
using namespace std;

// User defined function that returns product of
// arr[] using accumulate() library function.
int arrayProduct(int a[], int n)
{
    int initialProduct = 1;
    return accumulate(a, a + n, initialProduct, multiplies<int>());
}

int main()
{
    int a[] = { 5, 10, 15 };
    int n = sizeof(a) / sizeof(a[0]);
    cout << arrayProduct(a, n);
    return 0;
}
```

**Output:** 

```cpp
750
```

**向量的乘积**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to find vector product
#include <iostream>
#include <numeric>
#include <vector>
using namespace std;

// User defined function that returns product of
// v using accumulate() library function.
int arrayProduct(vector<int>& v)
{
    int initialProduct = 1;
    return accumulate(v.begin(), v.end(), initialProduct, multiplies<int>());
}

int main()
{
    vector<int> v{ 5, 10, 15 };
    cout << arrayProduct(v);
    return 0;
}
```

**Output:** 

```cpp
750
```

我们也可以在累加中使用自定义函数。详见 C++ STL | Set 1(累加()和 partial_product()) 中的[数值表头。](https://www.geeksforgeeks.org/numeric-header-in-c-stl-set-1-accumulate-and-partial_product/)