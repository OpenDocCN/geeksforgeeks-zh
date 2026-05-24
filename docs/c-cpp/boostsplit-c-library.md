# boost::在 C++ 库中拆分

> 原文:[https://www.geeksforgeeks.org/boostsplit-c-library/](https://www.geeksforgeeks.org/boostsplit-c-library/)

这个函数类似于 c 语言中的 strtok，输入序列被拆分成标记，用分隔符隔开。分隔符通过谓词给出。
**语法:**

```cpp
Template:
split(Result, Input, Predicate Pred);

Parameters:
Input: A container which will be searched.
Pred: A predicate to identify separators. 
This predicate is supposed to return true 
if a given element is a separator.
Result: A container that can hold copies of 
references to the substrings.

Returns: A reference the result
```

**应用:**用于将字符串拆分为子串，子串之间用分隔符隔开。
T3】例:

```cpp
Input : boost::split(result, input, boost::is_any_of("\t"))
       input = "geeks\tfor\tgeeks"
Output : geeks
        for
        geeks
Explanation: Here in input string we have "geeks\tfor\tgeeks"
and result is a container in which we want to store our result
here separator is "\t".

```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to split
// string into substrings
// which are separated by
// separator using boost::split

// this header file contains boost::split function
#include <bits/stdc++.h>
#include <boost/algorithm/string.hpp>
using namespace std;

int main()
{
    string input("geeks\tfor\tgeeks");
    vector<string> result;
    boost::split(result, input, boost::is_any_of("\t"));

    for (int i = 0; i < result.size(); i++)
        cout << result[i] << endl;
    return 0;
}
```

输出:

```cpp
geeks
for
geeks        
```