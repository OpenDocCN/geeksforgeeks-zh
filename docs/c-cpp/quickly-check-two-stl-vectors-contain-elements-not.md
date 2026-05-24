# 快速检查两个 STL 向量是否包含相同元素

> 原文:[https://www . geesforgeks . org/quick-check-two-STL-vectors-contain-elements-not/](https://www.geeksforgeeks.org/quickly-check-two-stl-vectors-contain-elements-not/)

与普通的 C/C++ 数组不同，我们不需要进行逐个元素的比较来发现两个给定的向量是否包含相同的元素。
在向量的情况下，运算符“==”被重载以快速找到结果。下面是一个例子来证明这一点。

## C++ 14

```cpp
// C++ implementation to check whether elements
// in vector is equal or not
#include<bits/stdc++.h>
using namespace std;

// Check if all elements is equal or not
int main()
{
  // Comparing equal vectors
  vector<int> v1{3, 1, 2, 3};
  vector<int> v2{3, 1, 2, 3};
  (v1 == v2)?  cout << "Equal\n" : cout << "Not Equal\n";

  // Comparing non-equal vectors
  vector<int> v3{1, 2, 3, 4};
  (v1 == v3)?  cout << "Equal\n" : cout << "Not Equal\n";

  // comparing with empty
  vector<int> v4;
  (v1 == v4)?  cout << "Equal\n" : cout << "Not Equal\n";

  // comparing two empty
  vector<int> v5;
  (v5 == v4)?  cout << "Equal\n" : cout << "Not Equal\n";

   return 0;
}
```

**输出:**

```cpp
Equal
Not Equal
Not Equal
Equal
```

本文由**沙钦·毕斯特**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。