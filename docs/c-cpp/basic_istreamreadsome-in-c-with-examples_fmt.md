# basic_istream::readsome() in C++ with Examples

> 原文: [https://www.geeksforgeeks.org/basic_istreamreadsome-in-c-with-examples/](https://www.geeksforgeeks.org/basic_istreamreadsome-in-c-with-examples/)

`basic_istream::readsome()` 用于从缓冲区读取数据，并从输入字符串中提取最多 `n` 个立即可用的字符。该函数返回提取的字符数。下面是相同的语法：

## 头文件

```cpp
#include<iostream>
```

## 语法

```cpp
streamsize readsome(char_type* a,
                    streamsize n);
```

## 参数

*   `n`: 表示要读取最大字符数。
*   `a`: 是存储提取字符的数组指针。

## 返回值

`std::basic_istream::readsome()` 返回提取的字符数。

以下是以更好的方式理解 `std::basic_istream::readsome()` 实现的程序：

### 程序 1

```cpp
// C++ code for basic_istream::readsome()
#include <bits/stdc++.h>
using namespace std;

// main method
int main()
{
    char gfg[50] = {};
    istringstream gfg1("GeeksforGeeks");

    // reads 'Gee' and
    // stores in c[0] .. c[2]
    gfg1.readsome(gfg, 3);

    // reads 'ksforG' and
    // stores in c[0] .. c[5]
    gfg1.readsome(gfg, 6);
    cout << gfg << endl;
}
```

**输出:**

```cpp
ksforG
```

### 程序 2

```cpp
// C++ code for basic_istream::readsome()
#include <bits/stdc++.h>
using namespace std;

// main method
int main()
{
    char gfg[50] = {};
    istringstream gfg1("Computer");

    // reads 'Co' and
    // stores in c[0] .. c[1]
    gfg1.readsome(gfg, 2);

    // reads 'mpu' and
    // stores in c[0] .. c[4]
    gfg1.readsome(gfg, 3);
    cout << gfg << endl;
}
```

**输出:**

```cpp
mpu
```

**参考:** [http://www.cplusplus.com/reference/istream/basic_istream/readsome/](http://www.cplusplus.com/reference/istream/basic_istream/readsome/)