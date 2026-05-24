# c++ 中的 smatch | Regex(正则表达式)

> 原文:[https://www . geesforgeks . org/smatch-regex-正则表达式-in-c/](https://www.geeksforgeeks.org/smatch-regex-regular-expressions-in-c/)

smatch 是 match_results 类模板的一个实例，用于字符串对象上的匹配。
**可以使用 smatch 调用的函数:**
可以调用 match_results 对象的 str()、position()和 length()成员函数来获取匹配的文本，或者匹配相对于主题字符串的起始位置及其长度。

*   在没有参数或以 0 作为参数的情况下调用这些成员函数，以获得整体正则表达式匹配。
*   调用它们传递 1 或更大的值以获得特定捕获组的匹配。
*   size()成员函数指示捕获组的数量加上总匹配的数量。
*   因此，您可以将大小为()-1 的值传递给其他三个成员函数(str()、position()、length())。

**什么是攻组？**
**例:**

```cpp
Example-1:
Suppose you create a regex object like : regex re("(geeks)(.*)") 
Here no of capturing group is = 2 
[ one is "geeks" and second is any character after "geeks" ].

Example-2:
regex re("a(b)c")
Here no of capturing group is = 1[ 'b' is the capturing group].
whatever within '(' and ')' braces is treated as capturing group.

```

下面是展示 smatch 工作原理的程序:

```cpp
#include <bits/stdc++.h>
using namespace std;
int main()
{
    string sp("geeksforgeeks");
    regex re("(geeks)(.*)");

    // flag type for determining the matching behavior
    // && here it is for matches on strings.
    smatch match;

    // we can use member function on match
    // to extract the matched pattern.
    if (regex_search(sp, match, re) == true) {

        // The size() member function indicates the
        // number of capturing groups plus one for the overall match
        // match size = Number of capturing group + 1
        // (.*) which "forgeeks" ).
        cout << "Match size = " << match.size() << endl;

        // Capturing group is index from 0 to match_size -1 
        // .....here 0 to 2
        // pattern at index 0 is the overall match "geeksforgeeks"
        // pattern at index 1 is the first capturing group "geeks"
        // pattern at index 2 is the 2nd capturing group "forgeeks"

        cout << "Whole match : " << match.str(0) << endl;
        cout << "First capturing group is '" << match.str(1)
             << "' which is captured at index " << match.position(1)
             << endl;
        cout << "Second capturing group is '" << match.str(2)
             << "' which is captured at index " << match.position(2)
             << endl;
    }
    else {
        cout << "No match is found" << endl;
    }
    return 0;
}
```

**Output:**

```cpp
Match size = 3
Whole match : geeksforgeeks
First capturing group is 'geeks' which is captured at index 0
Second capturing group is 'forgeeks' which is captured at index 5

```