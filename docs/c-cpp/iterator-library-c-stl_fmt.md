# C++ STL 中的迭代器库

> 原文: [https://www.geeksforgeeks.org/iterator-library-c-stl/](https://www.geeksforgeeks.org/iterator-library-c-stl/)

[c++ STL 中的迭代器|简介](https://www.geeksforgeeks.org/introduction-iterators-c/)

## 功能

### 迭代器操作

*   [`std::advance`](https://www.geeksforgeeks.org/stdadvance-in-cpp/)：Advance 迭代器
*   [`std::distance`](https://www.geeksforgeeks.org/stddistance-in-c/)：迭代器之间的返回距离
*   `std::begin`：迭代器到开始
*   `std::end`：迭代器结束
*   [`std::prev`](https://www.geeksforgeeks.org/stdprev-in-cpp/)：获取前一个元素的迭代器
*   [`std::next`](https://www.geeksforgeeks.org/stdnext-in-cpp/)：获取下一个元素的迭代器
*   [`std::next vs std::advance`](https://www.geeksforgeeks.org/stdnext-vs-stdadvance-in-cpp/)
*   [c++ STL 迭代器中的所有函数](https://www.geeksforgeeks.org/iterators-c-stl/)

### 迭代器生成器

*   [`std::back_inserter`](https://www.geeksforgeeks.org/stdback_inserter-in-cpp/)：构造 back insert 迭代器
*   [`std::front_inserter`](https://www.geeksforgeeks.org/stdfront_inserter-in-cpp/)：构造前端插入迭代器
*   [`std::inserter`](https://www.geeksforgeeks.org/stdinserter-in-cpp/)：构造插入迭代器
*   `std::make_move_iterator`：构造移动迭代器

### 迭代器类的类型

*   [`input-iterators`](https://www.geeksforgeeks.org/input-iterators-in-cpp/)：输入迭代器类别
*   [`output-iterators`](https://www.geeksforgeeks.org/output-iterators-cpp/)：输出迭代器类别
*   [`forward-iterators`](https://www.geeksforgeeks.org/forward-iterators-in-cpp/)：正向迭代器类别
*   [`bidirectional-iterators`](https://www.geeksforgeeks.org/bidirectional-iterators-in-cpp/)：双向迭代器类别
*   [`random-access-iterators`](https://www.geeksforgeeks.org/random-access-iterators-in-cpp/)：随机访问迭代器类别

### 预定义迭代器

*   `std::reverse_iterator`：Reverse iterator(类模板)
*   `std::move_iterator`：Move 迭代器(类模板)
*   [`std::back_insert_iterator`](https://www.geeksforgeeks.org/stdback_inserter-in-cpp/)：Back insert 迭代器(类模板)
*   [`std::front_insert_iterator`](https://www.geeksforgeeks.org/stdfront_inserter-in-cpp/)：Front insert 迭代器(类模板)
*   [`std::insert_iterator`](https://www.geeksforgeeks.org/stdinserter-in-cpp/)：Insert iterator(类模板)
*   [`std::istream_iterator`](https://www.geeksforgeeks.org/stdistream_iterator-stdostream_iterator-c-stl/)：istream 迭代器(类模板)
*   [`std::ostream_iterator`](https://www.geeksforgeeks.org/stdistream_iterator-stdostream_iterator-c-stl/)：Ostream iterator(类模板)
*   `std::istreambuf_iterator`：输入流缓冲区迭代器(类模板)
*   `std::ostreambuf_iterator`：输出流缓冲区迭代器(类模板)