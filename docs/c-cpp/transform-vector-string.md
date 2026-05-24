# 如何将向量转化为字符串？

> 原文:[https://www.geeksforgeeks.org/transform-vector-string/](https://www.geeksforgeeks.org/transform-vector-string/)

[向量:](https://www.geeksforgeeks.org/vector-sequence-containers-the-c-standard-template-library-stl-set-1/)向量与动态数组相同，能够在插入或删除元素时自动调整自身大小，其存储由容器自动处理。将向量转换成字符串的 C++ 程序。
[字符串:](https://www.geeksforgeeks.org/stdstring-class-in-c/) C++ 在其定义中有一种将字符序列表示为类对象的方式。这个类叫做 std:: string。

**std::ostringstream** :对字符串进行操作的输出流类。此类的对象使用包含一系列字符的字符串缓冲区。这个字符序列可以使用成员字符串作为字符串对象直接访问。

```cpp
// C++ program transform a vector into
// a string.
#include <vector>
#include <string>
#include <algorithm>
#include <sstream>
#include <iterator>
#include <iostream>

int main()
{
  std::vector<int> vec;
  vec.push_back(1);
  vec.push_back(2);
  vec.push_back(3);
  vec.push_back(4);
  vec.push_back(5);
  vec.push_back(6);

  std::ostringstream vts;

  if (!vec.empty())
  {
    // Convert all but the last element to avoid a trailing ","
    std::copy(vec.begin(), vec.end()-1,
        std::ostream_iterator<int>(vts, ", "));

    // Now add the last element with no delimiter
    vts << vec.back();
  }

  std::cout << vts.str() << std::endl;
}
```

输出:

```cpp
1, 2, 3, 4, 5, 6

```

本文由 **Jatin Goyal** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。