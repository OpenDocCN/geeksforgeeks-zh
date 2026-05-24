# 对向量中与目标值或条件相匹配的元素进行计数

> 原文:[https://www . geesforgeks . org/count-elements-in-a-vector-match-a-target-value-or-condition/](https://www.geeksforgeeks.org/count-elements-in-a-vector-that-match-a-target-value-or-condition/)

确定向量中与特定值匹配的整数个数。

我们在 C++ STL 中使用[计数](https://www.geeksforgeeks.org/std-count-cpp-stl/)

```cpp
// CPP program to count vector elements that
// match given target value.
#include <algorithm>
#include <iostream>
#include <vector>
using namespace std;

int main()
{
    vector<int> v{ 10, 30, 30, 10, 30, 30 };
    int target = 30;
    int res = count(v.begin(), v.end(), target);
    cout << "Target: " << target << " Count : " << res << endl;
    return 0;
}
```

**Output:**

```cpp
Target: 30 Count : 4

```

**如何统计符合条件的元素？**
我们可以在 C++ 中使用[λ表达式来实现这一点。](https://www.geeksforgeeks.org/lambda-expression-in-c/)

我们在 C++ STL 中使用[count _ if](https://www.geeksforgeeks.org/count_if-in-c/)

```cpp
// lambda expression to count elements
// divisible by 3.
#include <algorithm>
#include <iostream>
#include <vector>
using namespace std;
int main()
{
    vector<int> v{ 10, 18, 30, 10, 12, 45 };
    int res = count_if(v.begin(), v.end(),
                       [](int i) { return i % 3 == 0; });
    cout << "Numbers divisible by 3: " << res << '\n';
    return 0;
}
```

**Output:**

```cpp
Numbers divisible by 3: 4

```