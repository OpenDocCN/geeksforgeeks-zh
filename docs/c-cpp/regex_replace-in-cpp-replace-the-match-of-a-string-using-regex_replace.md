# c++ 中的 regex_replace |使用 regex _ Replace 替换字符串的匹配项

> 原文:[https://www . geeksforgeeks . org/regex _ replace-in-CPP-replace-the-match-of-string-use-regex _ replace/](https://www.geeksforgeeks.org/regex_replace-in-cpp-replace-the-match-of-a-string-using-regex_replace/)

**std::regex_replace()** 用于替换字符串中的所有匹配项，

**语法:**

```cpp
regex_replace(subject, regex_object, replace_text)

```

**参数:**接受三个参数，描述如下:

1.  主题字符串作为第一个参数。
2.  regex 对象作为第二个参数。
3.  替换文本作为第三个参数的字符串。

**返回值:**函数返回应用了替换的新字符串。

1.  { content } amp 或者$0 用于插入整个正则表达式匹配。
2.  $1、$2、…最多$9 用于插入前九个捕获组匹配的文本。
3.  # c++ 中的 regex_replace |使用正则表达式 _ 替换替换字符串的匹配项

    (back-tick)用于插入比赛左边的字符串。
4.  { content } ' 2019；(引号)用于插入匹配项右侧的字符串。
5.  如果捕获组的数量少于请求的数量，那么它将被替换为空。

**示例:**
假设一个正则表达式对象 **re(((极客))(。*)”**被创建，主题字符串为:**主题(“都是关于 geeks forgeeks”)**，你想用任何[捕获组](https://www.geeksforgeeks.org/smatch-regex-regular-expressions-in-c/)的内容替换匹配(例如$0，$1，…最多 9)。

> **示例-1:**
> 将匹配替换为$1 的内容。
> 这里匹配的是“极客 forgeeks”，将被 1 美元(“极客”)取代。
> 因此，结果“这一切都是关于极客”。
> 
> **示例-2:**
> 将匹配替换为$2 的内容。
> 这里 match 是“geeksforgeeks”，将被$ 2(“forgeeks”)代替。
> 因此，结果“这一切都是伪造的”。

下面是展示 regex_replace 工作原理的程序。

```cpp
// C++ program to show the working
// of regex_replace
#include <bits/stdc++.h>
using namespace std;

int main()
{
    string subject("its all about geeksforgeeks");

    string result1, result2, result3, result4;
    string result5;

    // regex object
    regex re("(geeks)(.*)");

    // $2 contains, 2nd capturing group which is (.*) means
    // string after "geeks" which is "forgeeks". hence
    // the match(geeksforgeeks) will be replaced by "forgeeks".
    // so the result1 = "its all about forgeeks"
    result1 = regex_replace(subject, re, "$2");

    // similarly $1 contains, 1 st capturing group which is
    // "geeks" so the match(geeksforgeeks) will be replaced
    // by "geeks".so the result2 = "its all about geeks".
    result2 = regex_replace(subject, re, "$1");

    // $0 contains the whole match
    // so result3 will remain same.
    result3 = regex_replace(subject, re, "$0");

    // $0 and {content}amp; contains the whole match
    // so result3 will remain same
    result4 = regex_replace(subject, re, "{content}amp;");

    // Here number of capturing group
    // is 2 so anything above 2
    // will be replaced by nothing.
    result5 = regex_replace(subject, re, "$6");

    cout << result1 << endl << result2 << endl;
    cout << result3 << endl << result4 << endl
         << result5;

    return 0;
}
```

**Output:**

```cpp
its all about forgeeks
its all about geeks
its all about geeksforgeeks
its all about geeksforgeeks
its all about

```