# c++ STL 中的堆栈

> 原文:[https://www.geeksforgeeks.org/stack-in-cpp-stl/](https://www.geeksforgeeks.org/stack-in-cpp-stl/)

堆栈是一种采用后进先出(LIFO)工作方式的容器适配器，其中在一端(顶部)添加一个新元素，仅在该端移除一个元素。堆栈使用[向量](https://www.geeksforgeeks.org/vector-in-cpp-stl/)或[德奎](https://www.geeksforgeeks.org/deque-cpp-stl/)(默认)或[列表](https://www.geeksforgeeks.org/list-cpp-stl/)(顺序容器类)的封装对象作为其底层容器，提供一组特定的成员函数来访问其元素。

**堆栈语法:-**

为了创建堆栈，我们必须在代码中包含<stack>头文件。然后我们用这个语法来定义 std::stack:</stack>

<figure class="table">

| Template > class stack; |

</figure>

**类型**–是包含在标准::堆栈中的元素类型。它可以是任何有效的 C++ 类型，甚至是用户定义的类型。

**容器**–是底层容器对象的类型。

**成员类型:-**

第一个模板参数，它表示元素类型。

容器类型——第二个模板参数，容器。它表示底层容器类型。

size_type-无符号整数类型。

与堆栈相关联的函数有:
[empty()](https://www.geeksforgeeks.org/stack-empty-and-stack-size-in-c-stl/)–返回堆栈是否为空–时间复杂度:O(1)
[size()](https://www.geeksforgeeks.org/stack-empty-and-stack-size-in-c-stl/)–返回堆栈的大小–时间复杂度:O(1)
[top()](https://www.geeksforgeeks.org/stack-top-c-stl/)–返回对堆栈最顶部元素的引用–时间复杂度:O(1)
[push(g)](https://www.geeksforgeeks.org/stack-push-and-pop-in-c-stl/)–在堆栈顶部添加元素‘g’–时间复杂度

## C++

```cpp
#include <iostream>
#include <stack>
using namespace std;
int main() {
    stack<int> stack;
    stack.push(21);
    stack.push(22);
    stack.push(24);
    stack.push(25);

         stack.pop();
    stack.pop();

    while (!stack.empty()) {
        cout << ' ' << stack.top();
        stack.pop();
    }
}
```

**Output**

```cpp
 22 21
```

**代码说明:**

1.  在我们的代码中包含 iostream 头文件或<bits>来使用它的功能。</bits>
2.  在我们的代码中包含堆栈头文件来使用它的函数，如果已经包含了<bits>，那么就不需要堆栈头文件，因为它已经内置了函数。</bits>
3.  在我们的代码中包含 std 命名空间，以便在不调用它的情况下使用它的类。
4.  调用 main()函数。应该在这个函数中添加程序逻辑。
5.  创建一个堆栈来存储整数值。
6.  使用 push()函数将值 21 插入堆栈。
7.  使用 push()函数将值 22 插入堆栈。
8.  使用 push()函数将值 24 插入堆栈。
9.  使用 push()函数将值 25 插入堆栈。
10.  使用 pop()函数从堆栈中移除顶部元素，即 25。顶部元素现在变成了 24。
11.  使用 pop()函数从堆栈中移除顶部元素，即 24。顶部元素现在变成了 22。
12.  使用 while 循环和 empty()函数检查堆栈是否不为空。那个！是“非”运算符。
13.  在控制台上打印堆栈的当前内容。
14.  在堆栈上调用 pop()函数。
15.  while 循环主体的结尾。
16.  main()函数体的结尾。

**堆栈功能列表:**

*   [栈::top()在 C++ STL 中](https://www.geeksforgeeks.org/stacktop-c-stl/)
*   [c++ STL 中的栈::空()和栈::大小()](https://www.geeksforgeeks.org/stackempty-stacksize-c-stl/)
*   [c++ STL 中的栈::push()和栈::pop()](https://www.geeksforgeeks.org/stackpush-stackpop-c-stl/)
*   [c++ STL 中的堆栈::交换()](https://www.geeksforgeeks.org/stackswap-c-stl/)
*   [c++ STL 中的栈::侵位()](https://www.geeksforgeeks.org/stackemplace-c-stl/)
*   [最近关于 C++ 堆栈的文章](https://www.geeksforgeeks.org/tag/cpp-stack/)

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论