# c++ STL 中的 count _ if()

> 原文:[https://www.geeksforgeeks.org/count_if-in-c/](https://www.geeksforgeeks.org/count_if-in-c/)

count_if()函数返回一个范围内满足条件的元素个数。

语法:

```cpp
template <class InputT, class UnaryPredicate>
typename iterator_traits <InputT> :: difference_type
    count_if(InputT first, InputT last, UnaryPredicate p);
```

示例:

```cpp
Input: 0 1 2 3 4 5 6 7 8 9
Output: Total no of even numbers is: 5

Input: 2 3 4 5 6 7 8 9 10 11 12 13
Output: Total no of even numbers is: 6
```

count_if 函数采用三个参数，其中前两个参数是元素序列的第一个和最后一个位置(其中最后一个位置不包含在范围内)，而第三个参数是一元谓词(采用单个参数来检查条件并返回 true 或 false)，它将给定序列的元素逐个作为参数，并基于该函数中指定的条件
返回布尔值。我们应该记住的一点是，谓词的类型应该与容器的类型相同。

然后，count_if()返回给定序列中比较器函数
(第三个参数)返回真的元素数。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to show the working
// of count_if()
#include <bits/stdc++.h>
using namespace std;

// Function to check the
// number is even or odd
bool isEven(int i)
{
    if (i % 2 == 0)
        return true;
    else
        return false;
}

// Drivers code
int main()
{
    vector<int> v;
    for (int i = 0; i < 10; i++) {
        v.push_back(i);
    }
    int noEven = count_if(v.begin(), v.end(),
                                     isEven);

    cout << "Total no of even numbers is: "
         << noEven;

    return 0;
}
```

**Output:** 

```cpp
Total no of even numbers is: 5
```