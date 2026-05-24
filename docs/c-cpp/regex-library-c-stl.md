# <regex>c++ STL 中的库</regex>

> 原文:[https://www.geeksforgeeks.org/regex-library-c-stl/](https://www.geeksforgeeks.org/regex-library-c-stl/)

**主班**

这些类封装了一个正则表达式以及在目标字符序列中匹配正则表达式的结果。

*   [**basic_regex:**](https://www.geeksforgeeks.org/regex-regular-expression-in-c/) 正则表达式对象(类模板)
*   **子匹配:**标识子表达式(类模板)匹配的字符序列
*   **match_results:** 标识一个正则表达式匹配，包括所有子表达式匹配(类模板)

**算法**

这些函数用于将封装在正则表达式中的正则表达式应用于目标字符序列。

*   [**regex_match:**](https://www.geeksforgeeks.org/regex-regular-expression-in-c/) 尝试将正则表达式与整个字符序列(函数模板)进行匹配
*   [**regex_search:**](https://www.geeksforgeeks.org/regex-regular-expression-in-c/) 尝试将正则表达式与字符序列的任何部分进行匹配。(功能模板)
*   [**正则表达式替换:**](https://www.geeksforgeeks.org/regex-regular-expression-in-c/) 用格式化的替换文本替换正则表达式。(功能模板)

**迭代器**

regex 迭代器用于遍历序列中找到的整个正则表达式匹配集。

*   **正则表达式迭代器:**遍历字符序列中的所有正则表达式匹配项。(类模板)
*   **regex_token_iterator:** 遍历给定字符串中所有 regex 匹配项内的指定子表达式，或者遍历不匹配的子字符串(类模板)

**异常**

此类定义作为异常抛出的对象类型，以报告正则表达式库中的错误。

*   **regex_error:** 报告正则表达式库生成的错误。(类)

**性状**

regex traits 类用于封装 regex 的可本地化方面。

*   **正则表达式 _ 特征:**提供正则表达式库所需的关于字符类型的元信息。(类模板)

**更多有用链接**

*   [最近关于 C++ 的文章](https://www.geeksforgeeks.org/category/cpp/)
*   [编码实践平台](https://practice.geeksforgeeks.org/)
*   [选择题](https://www.geeksforgeeks.org/c-programming-multiple-choice-questions/)
*   [c++ 类所有文章](https://www.geeksforgeeks.org/c-plus-plus/)