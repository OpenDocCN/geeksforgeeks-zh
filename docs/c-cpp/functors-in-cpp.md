# c++ 中的函子

> 原文:[https://www.geeksforgeeks.org/functors-in-cpp/](https://www.geeksforgeeks.org/functors-in-cpp/)

请注意标题是**函子**(不是函数)！！

考虑一个只接受一个参数的函数。然而，在调用这个函数时，我们有更多的信息要传递给这个函数，但是我们不能，因为它只接受一个参数。能做什么？

一个显而易见的答案可能是全局变量。然而，好的编码实践并不提倡使用全局变量，并说只有在没有其他选择的情况下才必须使用它们。

**函子**是可以视为函数或函数指针的对象。在如下场景中，函子最常用于 STl:

下面的程序使用 STL 中的[变换()为 arr[]的所有元素添加 1。](https://www.geeksforgeeks.org/transform-c-stl-perform-operation-elements/)

```cpp
// A C++ program uses transform() in STL to add 
// 1 to all elements of arr[]
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
        cout << arr[i] <<" ";

    return 0;
}
```

输出:

```cpp
2 3 4 5 6
```

这段代码片段只给 arr[]的内容添加了一个值。现在，假设我们想在 arr[]的内容中添加 5。

看到发生什么了吗？由于转换需要一个数组的一元函数(一个只有一个参数的函数)，我们不能传递一个数字来递增()。这实际上会让我们编写几个不同的函数来添加每个数字。真是一团糟。这就是函子开始使用的地方。

函子(或函数对象)是一个类似函数的 C++ 类。使用相同的旧函数调用语法调用函子。为了创建一个函子，我们创建了一个重载*运算符()*的对象。

```cpp
The line,
MyFunctor(10);

Is same as
MyFunctor.operator()(10);
```

让我们更深入地研究并理解这实际上是如何与 STl 结合使用的。

```cpp
// C++ program to demonstrate working of
// functors.
#include <bits/stdc++.h>
using namespace std;

// A Functor
class increment
{
private:
    int num;
public:
    increment(int n) : num(n) {  }

    // This operator overloading enables calling
    // operator function () on objects of increment
    int operator () (int arr_num) const {
        return num + arr_num;
    }
};

// Driver code
int main()
{
    int arr[] = {1, 2, 3, 4, 5};
    int n = sizeof(arr)/sizeof(arr[0]);
    int to_add = 5;

    transform(arr, arr+n, arr, increment(to_add));

    for (int i=0; i<n; i++)
        cout << arr[i] << " ";
}
```

输出:

```cpp
6 7 8 9 10
```

因此，在这里，增量是一个函子，一个充当函数的 c++ 类。

```cpp
 The line,
transform(arr, arr+n, arr, increment(to_add));
 is the same as writing below two lines,
// Creating object of increment
increment obj(to_add); 

// Calling () on object
transform(arr, arr+n, arr, obj); 

```

因此，创建了一个重载*运算符()*的对象 *a* 。因此，函子可以有效地与 c++ STl 结合使用。

本文由 **Supriya Srivatsa** 供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论