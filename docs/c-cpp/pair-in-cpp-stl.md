# 在 C++ 标准模板库中配对(STL)

> 原文:[https://www.geeksforgeeks.org/pair-in-cpp-stl/](https://www.geeksforgeeks.org/pair-in-cpp-stl/)

配对容器是在 **<实用工具>** 头中定义的简单容器，由两个数据元素或对象组成。

*   第一个元素被称为“第一”，第二个元素被称为“第二”，顺序是固定的(第一，第二)。
*   Pair 用于将两个类型可能不同的值组合在一起。Pair 提供了一种将两个异构对象存储为一个单元的方法。
*   配对可以被分配、复制和比较。默认情况下，映射或 hash_map 中分配的对象数组属于“对”类型，其中所有“第一”元素都是与其“第二”值对象相关联的唯一键。
*   要访问元素，我们使用变量名后跟点运算符，后跟关键字 first 或 second。

**语法:**

```cpp
pair (data_type1, data_type2) Pair_name
```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate pair STL
#include <iostream>
#include <utility>
using namespace std;

int main()
{
    pair<int, char> PAIR1;

    PAIR1.first = 100;
    PAIR1.second = 'G';

    cout << PAIR1.first << " ";
    cout << PAIR1.second << endl;

    return 0;
}
```

**Output**

```cpp
100 G
```