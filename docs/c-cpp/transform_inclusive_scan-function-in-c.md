# c++ 中的 transform_inclusive_scan()函数

> 原文:[https://www . geesforgeks . org/transform _ inclusive _ scan-function-in-c/](https://www.geeksforgeeks.org/transform_inclusive_scan-function-in-c/)

transform_inclusive_scan()是 C++ 中的内置函数，它与 inclusive_scan()相同，只是一元函数首先应用于每个输入项。
它的功能是用一元运算在第一个和最后一个元素之间转换每个元素，然后在特定范围的*二元运算*的帮助下计算包含前缀和运算。定义第 I 个输入元素的*包含*包含在第 I 个求和操作中。
我们可以取一个可选的 init(初始值)，并将结果写入从 d_first 开始的范围。

**语法:**

```cpp
template < class InputItrator, class OutputItrator,
          class BinaryOperation, class UnaryOperation >

OutputItrator transform_inclusive_scan( InputItrator first, 
                                        InputItrator last,
                                        OutputItrator d_first,
                                        BinaryOperation binary_op,
                                        UnaryOperation unary_op 
                                     );
```

**使用的参数:**

*   **第一个和最后一个:-** 第一个和最后一个元素定义了元素和的范围。
*   **d_first:-** 其目的地范围的开始。
*   **一元运算:-** 要应用于输入范围内每个元素的运算。
*   **binary_op:-** 将应用于一元 _op 的结果和其他 binary_op 的结果的运算，以及是否将提供 init(初始值)。

**型式要求:**

*   *输入滴定器*:输入操作器是迭代器的一个类，它能够读取指向的元素。如果一旦我已经增加，那么所有其他副本无效，其有效性为单程算法。
*   *输出迭代器*:输出迭代器是一个可以写入指向元素的迭代器。

**返回值:**元素的迭代器，经过最后写入的元素。

**注意:**一元运算在此函数中是可选的，不应用于 init。实际上，init 参数终于出现了。

下面是上述问题的实现。

## C++

```cpp
// C++ program by used std::transform_inclusive_scan() function
// to transforms each and every elements between first
// and last with unary_op, then computes an inclusive prefix sum
#include <iostream>
#include <vector>
using namespace std;

namespace geeksInputIterator {
template <class InputItrator, class OutputItrator,
          class BinaryOperation, class UnaryOperation>

OutputItrator transform_inclusive_scan(InputItrator first,
                                       InputItrator last,
                                       OutputItrator d_first,
                                       BinaryOperation binary_op,
                                       UnaryOperation unary_op)
{
    *d_first = unary_op(*first);
    first++ ;
    d_first++ ;
    for (auto it = first; it != last; it++) {

        // calculate the prefix sum
        *d_first = binary_op(unary_op(*it), *(d_first - 1));
        d_first++ ;
    }
    return d_first;
}
}

// Driver code
int main()
{
    // input elements
    vector<int> InputVector{ 11, 22, 33, 44, 55, 66, 77, 88 };

    // OutputVector elements size
    vector<int> OutputVector(8);

    // inclusive transform function with begin and ending
    geeksInputIterator::transform_inclusive_scan(InputVector.begin(),
                   InputVector.end(), OutputVector.begin(),
                   [](auto xx, auto yy) {
                     return xx + yy;
                      },
                   [](auto xx) {
                     return xx * xx;
});
    // for loop for print output
    for (auto item : OutputVector) {

        // Print the output item
        cout << item << " ";
    }

    // to move next line
    cout << std::endl;
    return 0;
}
```

**输出:**

```cpp
121 605 1694 3630 6655 11011 16940 24684 
```

**注意:**以上程序可能不会在很多 IDE 上运行。