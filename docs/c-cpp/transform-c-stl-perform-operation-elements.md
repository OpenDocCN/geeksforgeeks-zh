# c++ STL 中的 std::transform()(对所有元素执行操作)

> 原文:[https://www . geesforgeks . org/transform-c-STL-perform-operation-elements/](https://www.geeksforgeeks.org/transform-c-stl-perform-operation-elements/)

考虑将两个数组的内容添加到第三个数组中的问题。假设所有数组的大小都相同。
下面是没有转换()的简单 C++ 程序。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// A C++ code to add two arrays
#include <bits/stdc++.h>
using namespace std;

int main()
{
  int arr1[] = {1, 2, 3};
  int arr2[] = {4, 5, 6};
  int n = sizeof(arr1)/sizeof(arr1[0]);
  int res[n];

  // Code to add two arrays
  for (int i=0; i<n; i++)
    res[i] = arr1[i] + arr2[i];

  for (int i=0; i<3; i++)
    cout << res[i] << " ";
}
```

输出:

```cpp
5 7 9
```

利用 STL 的变换功能，可以单行添加数组。

## C

```cpp
// Using transform() in STL to add two arrays
#include <bits/stdc++.h>
using namespace std;

int main()
{
  int arr1[] = {1, 2, 3};
  int arr2[] = {4, 5, 6};
  int n = sizeof(arr1)/sizeof(arr1[0]);
  int res[n];

  // Single line code to add arr1[] and arr2[] and
  // store result in res[]
  transform(arr1, arr1+n, arr2, res, plus<int>());

  for (int i=0; i<n; i++)
    cout << res[i] << " ";
}
```

输出:

```cpp
5 7 9
```

**transform()在 C++ 中有两种使用形式:**

1.  **一元运算**:对输入应用一元运算符转换为输出

```cpp
transform(Iterator inputBegin, Iterator inputEnd, 
         Iterator OutputBegin, unary_operation) 
```

1.  下面是 C++ 的例子。

## C

```cpp
// C++ program to demonstrate working of
// transform with unary operator.
#include <bits/stdc++.h>
using namespace std;

int increment(int x) {  return (x+1); }

int main()
{
    int arr[] = {1, 2, 3, 4, 5};
    int n = sizeof(arr)/sizeof(arr[0]);

    // Apply increment to all elements of
    // arr[] and store the modified elements
    // back in arr[]
    transform(arr, arr+n, arr, increment);

    for (int i=0; i<n; i++)
        cout << arr[i] << " ";

    return 0;
}
```

1.  输出:

```cpp
2 3 4 5 6 
```

2.  **二进制运算**:对输入应用二进制运算符转换为输出

```cpp
transform(Iterator inputBegin1, Iterator inputEnd1, 
         Iterator inputBegin2, Iterator OutputBegin, 
         binary_operation) 
```

1.  上面提到的将两个数组相加的例子是用二进制运算进行转换的例子。

**更多示例:**
我们可以使用 transform 将字符串转换为大写(参见[这个](http://en.cppreference.com/w/cpp/algorithm/transform) )
我们还可以修改上面的矢量示例。

```cpp

    // vect is a vector of integers.
    transform(vect.begin(), vect.end(), 
              vect.begin(), increment); 
```

**相关话题:**
[c++ 中的函子](https://www.geeksforgeeks.org/functors-in-cpp/)
如果发现有不正确的地方，请写评论，或者想分享更多以上讨论话题的信息