# c++ STL 中的什么位置

> 哎哎哎:# t0]https://www . geeksforgeeks . org/dequa-place in-c-STL/

[德格或双端队列](https://www.geeksforgeeks.org/deque-set-1-introduction-applications/)是序列容器，具有两端伸缩的特点。它们类似于向量，但是在末尾和开头插入和删除元素的情况下效率更高。与向量不同，可能无法保证连续的存储分配。
**侵位()**功能在指定位置前插入新元素，容器的大小增加一。
**语法:**

```cpp
iterator emplace(const_iterator position, value_type val);
```

**参数:**该方法接受以下参数:

*   **位置:**定义新元素要插入的位置。
*   **值:**要插入的新值。

**返回值:**向新构造的元素返回一个迭代器。
下面的例子说明这个方法:
**例子-1:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <deque>
#include <iostream>
using namespace std;

int main()
{

    // initialization of deque named sample
    deque<int> sample = { 2, 3, 4, 5 };

    // initializing an iterator
    deque<int>::iterator itr;

    // adding 1 at the first position in
    // the sample as itr points to
    // first position in the sample
    sample.emplace(sample.begin(), 1);

    // Looping the whole
    for (itr = sample.begin(); itr != sample.end(); ++ itr)
        // sample for printing
        cout << *itr << " ";

    cout << endl;
    return 0;
}
```

**Output:** 

```cpp
1 2 3 4 5
```

**示例-2:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <deque>
#include <iostream>
using namespace std;
int main()
{

    // initialization of deque named sample
    deque<char> sample = { 'G', 'E', 'K', 'S' };

    // initialising an iterator
    deque<char>::iterator itr = sample.begin();

    // incrementing the iterator by one place
    ++ itr;

    // adding E at the second position in
    // the sample as itr points to
    // second position in the sample
    sample.emplace(itr, 'E');

    // Looping the whole
    for (itr = sample.begin(); itr != sample.end(); ++ itr)

        // sample for printing
        cout << *itr;

    cout << endl;
    return 0;
}
```

**Output:** 

```cpp
GEEKS
```