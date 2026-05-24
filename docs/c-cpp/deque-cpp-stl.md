# c++ 标准模板库(STL)中的 Deque

> 哎哎哎:# t0]https://www . geeksforgeeks . org/dequa-CPP-STL/

双端队列是序列容器，具有两端扩展和收缩的特性。
它们类似于载体，但在插入和删除元素的情况下效率更高。与向量不同，可能无法保证连续的存储分配。
双端队列基本上是数据结构双端队列的一种实现。队列数据结构只允许在末尾插入，从前面删除。这就像现实生活中的排队，人从前面被移走，在后面被加上。双端队列是队列的一种特殊情况，可以在两端进行插入和删除操作。
德格的功能与[矢量](https://www.geeksforgeeks.org/vector-in-cpp-stl/)相同，只是增加了前后推送和弹出操作。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <iostream>
#include <deque>

using namespace std;

void showdq(deque <int> g)
{
    deque <int> :: iterator it;
    for (it = g.begin(); it != g.end(); ++ it)
        cout << '\t' << *it;
    cout << '\n';
}

int main()
{
    deque <int> gquiz;
    gquiz.push_back(10);
    gquiz.push_front(20);
    gquiz.push_back(30);
    gquiz.push_front(15);
    cout << "The deque gquiz is : ";
    showdq(gquiz);

    cout << "\ngquiz.size() : " << gquiz.size();
    cout << "\ngquiz.max_size() : " << gquiz.max_size();

    cout << "\ngquiz.at(2) : " << gquiz.at(2);
    cout << "\ngquiz.front() : " << gquiz.front();
    cout << "\ngquiz.back() : " << gquiz.back();

    cout << "\ngquiz.pop_front() : ";
    gquiz.pop_front();
    showdq(gquiz);

    cout << "\ngquiz.pop_back() : ";
    gquiz.pop_back();
    showdq(gquiz);

    return 0;
}
```

上述程序的输出为:

```cpp
The deque gquiz is :     15    20    10    30

gquiz.size() : 4
gquiz.max_size() : 4611686018427387903
gquiz.at(2) : 10
gquiz.front() : 15
gquiz.back() : 30
gquiz.pop_front() :     20    10    30

gquiz.pop_back() :     20    10
```

**德清之法:**

*   [c++ STL 中的 deque insert()函数](https://www.geeksforgeeks.org/deque-insert-function-in-c-stl/):插入一个元素。并返回一个指向第一个新插入元素的迭代器。
*   [c++ STL 中的 deque rbegin()函数](https://www.geeksforgeeks.org/deque-rbegin-function-in-c-stl/):返回一个反向迭代器，该迭代器指向 deque 的最后一个元素(即它的反向开始)。
*   [c++ STL](https://www.geeksforgeeks.org/deque-rend-function-in-c-stl/)中的 deque rend()函数:返回一个反向迭代器，该迭代器指向 deque 开始之前的位置(这被认为是它的反向结束)。
*   [c++ STL 中的 deque CBE gin()](https://www.geeksforgeeks.org/deque-cbegin-in-c-stl/):返回指向容器第一个元素的常量迭代器，即迭代器不能用来修改，只能遍历 deque。
*   [c++ STL 中的 deque max_size()函数](https://www.geeksforgeeks.org/deque-max_size-function-in-c-stl/):返回一个 deque 容器可以容纳的最大元素个数。
*   [c++ STL 中的 deque assign()函数](https://www.geeksforgeeks.org/deque-assign-function-in-c-stl/):给相同或不同的 deque 容器赋值。
*   [c++ STL 中的 deque resize()函数](https://www.geeksforgeeks.org/deque-resize-function-in-c-stl/):改变 deque 大小的函数。
*   [dequee::push _ front()在 C++ STL 中](https://www.geeksforgeeks.org/dequepush_front-c-stl/):这个功能是用来将元素从前面推入一个 dequee。
*   [dequee::push _ back()在 C++ STL 中](https://www.geeksforgeeks.org/dequepush_back-c-stl/):这个函数是用来将元素从后面推入一个 dequee。
*   [c++ STL](https://www.geeksforgeeks.org/dequepop_front-dequepop_back-c-stl/):**pop _ front()**函数中的 de quee::pop _ front()和 de quee::pop _ back()用于从前面弹出或移除 de quee 中的元素。 **pop_back()** 功能用于从背面弹出或移除背景中的元素。
*   [deque::front()和 deque::back()在 C++ STL 中](https://www.geeksforgeeks.org/dequefront-dequeback-c-stl/) : **front()** 函数用来引用 deque 容器的第一个元素。 **back()** 函数用于引用德格容器的最后一个元素。
*   [de quee::clear()和 de quee::erase()在 C++ STL 中](https://www.geeksforgeeks.org/dequeclear-dequeerase-c-stl/) : **clear()** 函数用于移除 de quee 容器的所有元素，从而使其大小为 0。 **erase()** 功能用于从指定位置或范围移除容器中的元素。
*   [c++ STL](https://www.geeksforgeeks.org/dequeempty-dequesize-c-stl/):**empty()**函数中的 dequee::empty()和 dequee::size()用于检查 dequee 容器是否为空。 **size()** 函数用于返回 deque 容器的大小或 deque 容器中的元素数量。
*   [de quee::operator =和 C++ STL 中的 de quee::operator[]](https://www.geeksforgeeks.org/dequeoperator-dequeoperator-c-stl/):
    **operator =**运算符用于通过替换现有内容为容器分配新内容。**操作符[]** 操作符用于引用操作符内部给定位置的元素。
*   [在 C++ STL](https://www.geeksforgeeks.org/dequeat-dequeswap-c-stl/) : **at()** 函数中的 deque::at()和 deque::swap()用于引用作为函数参数给出的位置上的元素。 **swap()** 功能用于将一个德格的内容与另一个相同类型和大小的德格进行交换。
*   [de quee::begin()和 de quee::end 在 C++ STL 中](https://www.geeksforgeeks.org/dequebegin-dequeend-c-stl/) : **begin()** 函数用于返回指向 de quee 容器第一个元素的迭代器。 **end()** 函数用于返回一个指向 deque 容器最后一个元素的迭代器。
*   [在 C++ STL](https://www.geeksforgeeks.org/deque-emplace_front-deque-emplace_back-cpp-stl/) : **中的 dequee::侵位 _front()和 dequee::侵位 _back()函数用于向 dequee 容器中插入新元素。新元素被添加到 deque 的开头。**retain _ back()**功能用于向 deque 容器中插入新元素。新元素被添加到 deque 的末尾。**
*   在 C++ STL 中:在给定的数字范围内查找元素。返回范围[第一个，最后一个]中第一个元素的迭代器，该元素与 val 比较相等。如果没有找到这样的元素，函数返回 last。

[**德清**](https://www.geeksforgeeks.org/tag/cpp-deque/)
近期文章如发现有不正确的地方，或想分享以上讨论话题的更多信息，请写评论。