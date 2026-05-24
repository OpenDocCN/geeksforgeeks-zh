# C++ |模板|第 10 题

> 原文:[https://www.geeksforgeeks.org/c-templates-question-7/](https://www.geeksforgeeks.org/c-templates-question-7/)

以下程序的输出。

```cpp
#include <iostream>
using namespace std;

template <class T, int max>
int arrMin(T arr[], int n)
{
   int m = max;
   for (int i = 0; i < n; i++)
      if (arr[i] < m)
         m = arr[i];

   return m;
}

int main()
{
   int arr1[]  = {10, 20, 15, 12};
   int n1 = sizeof(arr1)/sizeof(arr1[0]);

   char arr2[] = {1, 2, 3};
   int n2 = sizeof(arr2)/sizeof(arr2[0]);

   cout << arrMin<int, 10000>(arr1, n1) << endl;
   cout << arrMin<char, 256>(arr2, n2);
   return 0;
}
```

**(A)** 编译器错误，模板参数必须是数据类型。
**(二)**

```cpp
10
1
```

**(C)**

```cpp
10000
256
```

**(D)**

```cpp
1
1
```

**回答:** **(B)**

**说明:**我们可以将非类型参数传递给模板。非类型参数主要用于为模板的特定实例指定最大值或最小值或任何其他常数值。关于非类型参数，需要注意的重要一点是，它们必须是常量。编译器必须在编译时知道非类型参数的值。因为编译器需要在编译时为指定的非类型值创建函数/类。

下面是另一个非类型参数的例子。

```cpp
#include <iostream>
using namespace std;

template 
 T fun (T arr[], int size)
{
    if (size > N)
      cout << "Not possible";
    T max = arr[0];
   for (int i = 1; i < size; i++)
      if (max < arr[i])
          max = arr[i];
   return max;
}

int main ()
{
    int arr[] = {12, 3, 14};
    cout << fun  (arr, 3);
}
```

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)