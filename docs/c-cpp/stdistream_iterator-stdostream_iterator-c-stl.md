# c++ STL 中的 std::istream_iterator 和 STD::ostream _ iterator

> 原文:[https://www . geeksforgeeks . org/stdi stream _ iterator-stdostream _ iterator-c-STL/](https://www.geeksforgeeks.org/stdistream_iterator-stdostream_iterator-c-stl/)

STL 是 C++ 中一个非常强大的库。它建立在模板编程的原则之上。
**STL 库有三个主要组件:**

1.  **容器:**这些类定义了用于包含数据的数据结构。数据可以存储在链表、树或数组中。STL 中提供的容器有向量、出列、列表、转发列表、集合、多集合、映射和多映射。
2.  **算法:**STL 库还为我们提供了处理存储在容器中的数据的功能。这些功能在*算法*头文件中提供
3.  **迭代器:**迭代器是容器和算法之间的链接。它们是这些类的公共接口。迭代器是一个对象，可以用来迭代器容器中的元素。因此，算法使用迭代器来修改容器。

所有三个组件的设计都符合数据抽象的原则。因此，任何保存数据并且*表现得像容器*的对象都是容器。类似地，任何遍历容器中元素的迭代器都是迭代器。

如果迭代器可以用来访问数据容器的元素，那么流呢？为了与设计保持一致，Streams 也是数据容器，因此 C++ 为我们提供了迭代器来迭代任何流中存在的元素。这些迭代器被称为**流迭代器**。要使用这些迭代器，必须包含*迭代器*头文件。
 **流迭代器**要么是输入流迭代器，要么是输出流迭代器。这些迭代器的类是 *istream_iterator* 和 *ostream_iterator。这些迭代器的行为分别类似于输入迭代器和输出迭代器*。

**istream_iterator**

【istream _ iterator 的类定义

```cpp
namespace std {
    template < typename T, typename charT=char, 
               typename traits=char_traits <charT> >
    class istream_iterator;
}

```

**语法:**

```cpp
istream_iterator<T>(stream)
T:      Template parameter for specifying type of data
stream: The object representing the stream

```

```cpp
ostream_iterator<T>(stream, delim).
stream: The object representing the stream.
T:      Template Parameter for data type in the stream
delim:  An optional char sequence that is used to 
        separate the data items while displaying them.

```

**注:**

*   使用迭代器，我们只能访问一种类型的元素。
*   istream_iterator 有一个特殊的状态*流结束*迭代器，当到达流结束或者输入操作失败时获取。默认构造函数返回流迭代器的结尾。

**ostream_iterator**

【ostream _ iterator 的类定义

```cpp
namespace std {
    template < typename T, typename charT=char, 
               typename traits=char_traits <charT> >
    class ostream_iterator;
}

```

**语法:**

```cpp
OutputIterator copy (InputIterator first, InputIterator last, OutputIterator result);

first: Input Iterator to the first element 
in source from where elements need to be copied.
last:  Input Iterator to the last element 
in source till where elements need to be copied.
result: Output iterator to the first element 
in the destination container to where elements will copied.
 Return Value: Iterator pointing to the last element that was copied to the destination.

```

第二个和第三个模板参数被赋予了默认值。我们只需要指定第一个模板参数，该参数指定流中存在的数据类型，即流是否包含整数、浮点数或字符串。

**示例:**

```cpp
istream_iterator cin_it(cin) is an iterator for the stream cin.
ostream_iterator cout_it(cout, " ") is an iterator for the stream cout.
ostream_iterator cout_it(cout) is an iterator for stream cout, with no delimeter.

```

**流迭代器的重要性**

流迭代器的优势在于，它们提供了一个公共接口，可以将输入/输出流、文件流以及其他流中的元素访问到外部物理设备。

*   一旦获得了相应流的迭代器，接下来的代码几乎与所有类型的流相同。
*   因此，像从输入流读取和从另一个外部流读取这样的任务变得相似。
*   流迭代器允许我们访问所有强大的 STL 算法，比如 for_each，replace_if，它们需要一个输入范围来操作。一个特别有用的功能是[复制()功能](https://www.geeksforgeeks.org/different-methods-copy-c-stl-stdcopy-copy_n-copy_if-copy_backwards/)。该函数用于将元素从一个容器复制到另一个容器。
*   使用 copy()函数，我们可以轻松地将数据从流传输到容器，反之亦然。这里有几个示例程序来演示如何使用流迭代器

**例 1**

```cpp
// Cpp program to illustrate
// Read a bunch of integers from the input stream
// and print them to output stream

#include <algorithm>
#include <iostream>
#include <iterator>

using namespace std;
int main()
{

    // Get input stream and end of stream iterators
    istream_iterator<int> cin_it(cin);
    istream_iterator<int> eos;

    // Get output stream iterators
    ostream_iterator<int> cout_it(cout, " ");

    // We have both input and output iterators, now we can treat them
    // as containers. Using copy function we transfer data from one
    // container to another.
    // Copy elements from input to output using copy function
    copy(cin_it, eos, cout_it);

    return 0;
}
```

```cpp
Input: 1 2 3 4 5 
Output: 1 2 3 4 5

```

**例 2**

```cpp
// Cpp program to illustrate
// Read a bunch of strings from a file
// sort them lexicographically and print them to output stream

#include <algorithm>
#include <fstream>
#include <iostream>
#include <iterator>
#include <string>
#include <vector>

using namespace std;
int main()
{

    // Define a vector to store the strings received from input
    vector<string> strings_v;

    // Define the filestream object used to read data from file
    ifstream fin("input_file.txt");

    // Get input stream and end of stream iterators
    istream_iterator<string> fin_it(fin);
    istream_iterator<string> eos;

    // Get output stream iterators
    ostream_iterator<string> cout_it(cout, " ");

    // Copy elements from input to vector using copy function
    copy(fin_it, eos, back_inserter(strings_v));

    // Sort the vector
    sort(strings_v.begin(), strings_v.end());

    // Copy elements from vector to output
    copy(strings_v.begin(), strings_v.end(), cout_it);

    return 0;
}
```

```cpp
Contents of File "input_file.txt": quick brown fox jumps over the lazy dog
Output: brown dog fox jumps lazy over quick the 

```

**例 3:**

```cpp
// Cpp program to illustrate

// Read a bunch of integers from the stream
// print the sorted order of even integers only

#include <algorithm>
#include <iostream>
#include <iterator>
#include <vector>

using namespace std;
int main()
{

    // Define a vector to store the even integers received from input
    vector<int> vi;

    // Get input stream and end of stream iterators
    istream_iterator<int> cin_it(cin);
    istream_iterator<int> eos;

    // Get output stream iterators
    ostream_iterator<int> cout_it(cout, " ");

    // Copy even integer elements from input to vector using for_each function
    for_each(cin_it, eos, [&](int a) {
        if (a % 2 == 0) {
            // if a is even push it to vector
            vi.push_back(a);
        }
    });

    // Sort the vector
    sort(vi.begin(), vi.end());

    // Copy elements from vector to output
    copy(vi.begin(), vi.end(), cout_it);

    return 0;
}
```

```cpp
Input: 1 4 3 2 6 8 31 52 
Output: 2 4 6 8 52 

```

**参考文献:**
[is tream _ iterator](http://en.cppreference.com/w/cpp/iterator/istream_iterator)
[ostream _ iterator](http://www.cplusplus.com/reference/iterator/ostream_iterator/)