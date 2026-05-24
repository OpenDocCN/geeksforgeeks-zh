# c++ STL 中的 regex_iterator()函数

> 原文:[https://www . geeksforgeeks . org/regex _ iterator-function-in-c-STL/](https://www.geeksforgeeks.org/regex_iterator-function-in-c-stl/)

**regex_iterator()** 是 C++ 中**双向迭代器类**的一个函数。此方法返回一个迭代器类型，以迭代序列中相同正则表达式模式的不同匹配项。

**语法:**

```cpp
template<
    class BidirectionalIterator,
    class CharT = typename std::iterator_traits::value_type,
    class Traits = std::regex_traits > class regex_iterator

```

**C++ 14 语法**

```cpp
template <class BidirectionalIterator,
          class charT=typename iterator_traits::value_type,
          class traits=regex_traits > class regex_iterator;

```

**C++ 11 语法:**

```cpp
template <class BidirectionalIterator,
          class charT=typename iterator_traits::value_type,
          class traits=regex_traits > class regex_iterator;

```

**参数:**该方法接受以下参数:

*   **双向迭代器:**迭代目标字符序列。
*   图表:这是一个字符类型。
*   **性状:**为 regex 性状类型。

**返回值:**这个方法返回一个带有结果序列的字符串对象。

以下示例说明了 regex_iterator()方法:

**示例:**

```cpp
#include <iostream>
#include <iterator>
#include <regex>
#include <string>
using namespace std;

int main()
{
    const string
        strg
        = "Geeksforgeeks welcome geeks.";

    regex words_regex("[^\\s]+");
    auto
        words_begin
        = sregex_iterator(
            strg.begin(),
            strg.end(),
            words_regex);

    auto words_end = sregex_iterator();

    cout << "Trying to find words"
         << " using regex_iterator:\n\n";

    cout << "Number of words found: "
         << distance(words_begin, words_end);

    cout << "\n\nThe words are:\n";
    for (sregex_iterator k = words_begin;
         k != words_end;
         ++ k) {

        smatch match = *k;
        string match_str = match.str();

        cout << match_str
             << endl;
    }
}
```

**Output:**

```cpp
Trying to find words using regex_iterator:

Number of words found: 3

The words are:
Geeksforgeeks
welcome
geeks.

```