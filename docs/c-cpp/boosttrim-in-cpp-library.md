# c++ 库中的 boost::trim

> 原文:[https://www.geeksforgeeks.org/boosttrim-in-cpp-library/](https://www.geeksforgeeks.org/boosttrim-in-cpp-library/)

该功能包含在“[boost/算法/字符串](https://www.geeksforgeeks.org/c-boost-string-algorithms-library/)”库中。**增强字符串算法库**提供了[字符串相关算法](https://www.geeksforgeeks.org/string-data-structure/)的通用实现，这些算法在 [STL](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) 中缺失。**修剪功能**用于从字符串中移除所有前导或尾随空格。输入序列被就地修改。

*   **trim_left():** 从字符串中删除所有前导空格。
*   **trim_right():** 从字符串中删除所有尾随空格。
*   **trim():** 从字符串中删除所有前导和尾随空格。

**语法:**

> **模板:**
> **修剪(输入，锁定)；**
> 
> **参数:**
> **输入:**输入序列
> **锁定:**用于“空间”分类的区域设置
> 
> **返回:**修改后的输入序列，没有前导或尾随空格。

**示例:**

> **输入:**“geeks _ for _ geeks”
> **输出:**应用左修剪:“geeks _ for _ geeks”
> 应用右修剪:“geeks _ for _ geeks”
> 应用修剪:“geeks _ for _ geeks”
> **解释:**
> trim _ left()函数删除所有前导空格。
> trim _ right()函数删除所有尾随空格。
> trim()函数删除所有前导和尾随空格。

下面是使用函数 **boost::trim()** 从字符串中删除空格的实现:

## C++

```cpp
// C++ program to remove white spaces
// from string using the function
// boost::trim function
#include <boost/algorithm/string.hpp>
#include <iostream>
using namespace boost::algorithm;
using namespace std;

// Driver Code
int main()
{
    // Given Input
    string s1 = "    geeks_for_geeks    ";
    string s2 = "    geeks_for_geeks    ";
    string s3 = "    geeks_for_geeks    ";

    // Apply Left Trim on string, s1
    cout << "The original string is: \""
         << s1 << "\" \n";
    trim_left(s1);
    cout << "Applied left trim: \""
         << s1 << "\" \n\n";

    // Apply Right Trim on string, s2
    cout << "The original string is: \""
         << s2 << "\" \n";
    trim_right(s2);
    cout << "Applied right trim: \""
         << s2 << "\" \n\n";

    // Apply Trim on string, s3
    cout << "The original string is: \""
         << s3 << "\" \n";
    trim(s3);
    cout << "Applied trim: \"" << s3
         << "\" \n";

    return 0;
}
```

**Output:**

```cpp
The original string is: "    geeks_for_geeks    " 
Applied left trim: "geeks_for_geeks    " 

The original string is: "    geeks_for_geeks    " 
Applied right trim: "    geeks_for_geeks" 

The original string is: "    geeks_for_geeks    " 
Applied trim: "geeks_for_geeks"

```

***时间复杂度:**O(N)*
T5**辅助空间:** O(1)