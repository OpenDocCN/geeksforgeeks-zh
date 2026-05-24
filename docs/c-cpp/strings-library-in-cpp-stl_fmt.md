# C++ STL 中的字符串库

> 原文：[https://www.geeksforgeeks.org/strings-library-in-cpp-stl/](https://www.geeksforgeeks.org/strings-library-in-cpp-stl/)

## 成员功能

*   [`String::constructor`](https://www.geeksforgeeks.org/constructors-c/)：构造 `string` 对象（公共成员函数）。
*   [`字符串析构函数`](https://www.geeksforgeeks.org/destructors-c/)：字符串析构函数（公共成员函数）。
*   [`String::operator=`](https://www.geeksforgeeks.org/operators-c-c/)：字符串赋值（公共成员函数）。

## 迭代器

*   [`begin`](https://www.geeksforgeeks.org/iterators-c-stl/)：返回迭代器开始（公共成员函数）。
*   [`end`](https://www.geeksforgeeks.org/iterators-c-stl/)：返回迭代器结束（公共成员函数）。
*   [`advance`](https://www.geeksforgeeks.org/iterators-c-stl/)：递增迭代器位置，直到其参数中提到的指定数字。
*   [`next`](https://www.geeksforgeeks.org/iterators-c-stl/)：返回迭代器在推进其参数中提到的位置后将指向的新迭代器。
*   [`prev()`](https://www.geeksforgeeks.org/iterators-c-stl/)：返回迭代器在其参数中提到的位置递减后将指向的新迭代器。
*   [`inserter`](https://www.geeksforgeeks.org/iterators-c-stl/)：将元素插入容器中的任何位置。
*   [`rbegin`](https://www.geeksforgeeks.org/stdstring-class-in-c/)：返回反向迭代器反向开始（公共成员函数）。
*   [`rend`](https://www.geeksforgeeks.org/stdstring-class-in-c/)：返回反向迭代器到反向结束（公共成员函数）。
*   `cbegin`：返回 `const_iterator` 到开头（公共成员函数）。
*   `cend`：返回 `const_iterator` 结束（公共成员函数）。
*   `crbegin`：返回 `const_reverse_iterator` 反转开始（公共成员函数）。
*   `crend`：返回 `const_reverse_iterator` 到 reverse end（公共成员函数）。

## 容量

*   [`size`](https://www.geeksforgeeks.org/5-different-methods-find-length-string-c/)：返回字符串长度（公共成员函数）。
*   [`length`](https://www.geeksforgeeks.org/5-different-methods-find-length-string-c/)：返回字符串长度（公共成员函数）。
*   [`max_size`](https://www.geeksforgeeks.org/stdbasic_stringmax_size-in-cpp/)：返回字符串的最大大小（公共成员函数）。
*   [`resize`](https://www.geeksforgeeks.org/stdstringresize-in-c/)：调整字符串大小（公共成员函数）。
*   [`capacity`](https://www.geeksforgeeks.org/stdstring-class-in-c/)：返回已分配存储的大小（公共成员函数）。
*   [`reserve`](https://www.geeksforgeeks.org/quickly-reverse-string-c/)：请求更改容量（公共成员功能）。
*   [`clear`](https://www.geeksforgeeks.org/stdstringclear-in-cpp/)：清除字符串（公共成员功能）。
*   [`empty`](https://www.geeksforgeeks.org/c-string-class-applications-set-2/)：测试字符串是否为空（公共成员函数）。
*   [`shrink_to_fit`](https://www.geeksforgeeks.org/stdstring-class-in-c/)：收缩到合适（公共成员功能）。

## 元素访问

*   [`at`](https://www.geeksforgeeks.org/stdstringat-in-c/)：获取字符串中的字符（公共成员函数）。
*   `back`：访问最后一个字符（公共成员函数）。
*   `front`：访问首字符（公共成员功能）。

## 修改器

*   `operator+=`：追加到字符串（公共成员函数）。
*   [`append`](https://www.geeksforgeeks.org/stdstringappend-in-c/)：追加到字符串（公共成员函数）。
*   [`push_back`](https://www.geeksforgeeks.org/stdstringpush_back-in-cpp/)：字符串追加字符（公共成员函数）。
*   [`assign`](https://www.geeksforgeeks.org/stdstringassign-in-c/)：给字符串赋值内容（公共成员函数）。
*   [`insert`](https://www.geeksforgeeks.org/stdstringinsert-in-c/)：插入到字符串中（公共成员函数）。
*   [`erase`](https://www.geeksforgeeks.org/stdstringerase-in-cpp/)：从字符串中擦除字符（公共成员功能）。
*   [`replace`](https://www.geeksforgeeks.org/stdstringreplace-stdstringreplace_if-c/)：替换部分字符串（公共成员函数）。
*   [`swap`](https://www.geeksforgeeks.org/stdstring-class-in-c/)：交换字符串值（公共成员函数）。
*   [`pop_back`](https://www.geeksforgeeks.org/stdstring-class-in-c/)：删除最后一个字符（公共成员功能）。

## 串操作

*   `operator[]`：获取字符串的字符（公共成员函数）。
*   `c_str`：获取 C 字符串等价物（公共成员函数）。
*   `data`：获取字符串数据（公共成员函数）。
*   `get_allocator`：Get 分配器（公共成员函数）。
*   `copy`：从字符串中复制字符序列（公共成员函数）。
*   [`find`](https://www.geeksforgeeks.org/stdfind-in-c/)：查找字符串中的内容（公共成员函数）。
*   [`rfind`](https://www.geeksforgeeks.org/c-string-class-applications-set-2/)：查找字符串中内容的最后一次出现（公共成员函数）。
*   [`find_first_of`](https://www.geeksforgeeks.org/c-string-class-applications-set-2/)：查找字符串中的字符（公共成员函数）。
*   [`find_last_of`](https://www.geeksforgeeks.org/c-string-class-applications-set-2/)：从末尾开始查找字符串中的字符（公共成员函数）。
*   [`find_first_not_of`](https://www.geeksforgeeks.org/stdstringfind_first_not_of-in-c/)：查找字符串中缺少字符（公共成员函数）。
*   [`find_last_not_of`](https://www.geeksforgeeks.org/stdstringfind_last_not_of-in-cpp/)：从末尾开始查找字符串中不匹配的字符（公共成员函数）。
*   [`substr`](https://www.geeksforgeeks.org/stdsubstr-in-ccpp/)：生成子串（公共成员函数）。
*   `compare`：比较字符串（公共成员函数）。

## 成员常量 & 非成员函数重载

*   `npos`：`size_t` 的最大值（公共静态成员常量）。
*   `operator+`：连接字符串。
*   [`关系运算符`](https://www.geeksforgeeks.org/comparing-string-objects-using-relational-operators-c/)：字符串的关系运算符。
*   `swap`：交换两个字符串的值。
*   `operator>>`：从流中提取字符串。
*   `operator<<`：插入字符串到流。
*   [`getline`](https://www.geeksforgeeks.org/stdstring-class-in-c/)：从流中读取一行到字符串。

## 更多有用链接

*   [最近关于 C++ 的文章](https://www.geeksforgeeks.org/category/cpp/)
*   [编码实践平台](https://practice.geeksforgeeks.org/)
*   [选择题](https://www.geeksforgeeks.org/c-programming-multiple-choice-questions/)
*   [C++ 类所有文章](https://www.geeksforgeeks.org/c-plus-plus/)