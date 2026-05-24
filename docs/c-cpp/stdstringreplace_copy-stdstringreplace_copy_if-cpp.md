# std::string::replace_copy()，std::string::replace_copy_if 在 C++ 中

> 哎哎哎:# t0]https://www . geeksforgeeks . org/STD string replace _ copy-STD string replace _ copy _ if-CPP/

**替换 _ 复制**

replace_copy()是 copy()和 replace()的组合。

*   它将范围[第一个，最后一个]中的元素复制到从结果开始的范围，用新值替换旧值的外观。
*   复制的范围是[第一个，最后一个]，包含第一个和最后一个之间的所有元素，包括第一个指向的元素，但不包括最后一个指向的元素。
*   范围不得重叠，以至于结果指向范围内的元素[第一个，最后一个]。
*   该函数使用运算符==将各个元素与 old_value 进行比较。

```cpp
template <class InputIterator, class OutputIterator, class T>
  OutputIterator replace_copy (InputIterator first, InputIterator last,
                               OutputIterator result,
                               const T& old_value, const T& new_value); 
first, last : Input iterators to the initial and final positions 
in a sequence. 
old_value : Value to be replaced.
new_value : Replacement value.

Returns the position after the last copied element in the destination
range (the first element that is not overwritten). 
```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP to illustrate
// replace_copy

#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;

// Function to replace 'A' at v.begin() with Z and copy it
// to v.begin() position
void replace_copyDemo(vector<char>& v)
{
    replace_copy(v.begin(), v.begin()+1,
                    v.begin(), 'A', 'Z' );
}

// Function to print content of vector
void print(vector<char>& v)
{
    int len = v.size();
    for (int i = 0; i < len; i++)
        cout << v[i] << " ";
    cout << endl;
}

// Driver code
int main()
{

    vector<char> v;

    for (int i = 0; i <= 6; i++)
        v.push_back('A' + i);
    cout << "Before replace_copy " <<": ";
    print(v);
    replace_copyDemo(v);

    cout << "After replace_copy " << ": ";
    print(v);

    return 0;
}
```

**输出:**

```cpp
Before replace_copy : A B C D E F G 
After replace_copy : Z B C D E F G 

```

**替换 _ 复制 _if**

replace_copy_if()是 copy()和 replace_if()的组合。

*   将范围[第一个，最后一个]中的元素复制到从结果开始的范围，用 new_value 替换 pred 返回 true 的元素。
*   简单来说，它将一个序列的元素复制到另一个相同大小的序列中，用另一个值替换任何满足谓词的元素。
*   返回目标范围内最后一个复制元素(第一个未被覆盖的元素)之后的位置。

```cpp
Template <class InputIterator, class OutputIterator, class UnaryPredicate, class T>
  OutputIterator replace_copy_if (InputIterator first, InputIterator last,
                                  OutputIterator result, UnaryPredicate pred,
                                  const T& new_value);
first, last : Input iterators to the initial and final positions 
in a sequence. 
old_value : Value to be replaced.
new_value : Replacement value.
pred : Unary function that accepts an element in the range as argument, 
and returns a value convertible to bool. The value returned indicates whether the 
element is to be replaced in the copy (if true, it is replaced).

```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP code to illustrate
// replace_copy_if
#include <iostream>
#include <algorithm>
#include <vector>
using namespace std;

// Function to check if number is even
int IsEven(int i)
{
    return ((i % 2) == 0);
}

// Function to print content of vector
void print(vector<int>& v)
{
    int len = v.size();
    for (int i = 0; i < len; i++)
        cout << v[i] << " ";
    cout << endl;
}

// Function to replace all
// even numbers from vector v1 and
// copying them to v2
void replace_copy_ifDemo(vector<int>& v1,
                            vector<int>& v2)
{
    replace_copy_if(v1.begin(), v1.end(),
                       v2.begin(), IsEven, 0);
}

// Driver Code
int main()
{
    vector<int> v1, v2;

    for (int i = 1; i <= 10; i++)
        v1.push_back(i);

    cout << "Before replace_copy_if : ";
    print(v1);

    v2.resize(v1.size()); // allocate space
    replace_copy_ifDemo(v1, v2);

    cout << "After replace_copy_if : ";
    print(v2);

    return 0;
}
```

**输出:**

```cpp
Before replace_copy_if : 1 2 3 4 5 6 7 8 9 10 
After replace_copy_if : 1 0 3 0 5 0 7 0 9 0 

```

**注意:**两种算法，即 replace_copy 和 replace_copy_if，都会返回目标范围内最后一个复制元素(第一个未被覆盖的元素)之后的位置。
**相关文章:** [std::string::replace，std::string::replace_if](https://www.geeksforgeeks.org/stdstringreplace-stdstringreplace_if-c/)
本文由 **Sakshi Tiwari** 供稿。如果你喜欢极客(我们知道你喜欢！)并愿意投稿，也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者将文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。