# 用 C++ 中的 tellg()函数举例

> 原文:[https://www.geeksforgeeks.org/tellg-function-c-example/](https://www.geeksforgeeks.org/tellg-function-c-example/)

**tellg()** 函数用于输入流，并返回指针在流中的当前“获取”位置。它没有参数，并返回一个成员类型 pos_type 的值，这是一个整数数据类型，表示获取流指针的当前位置。

**语法:-**

```cpp
pos_type tellg(); 

```

**返回:**成功时获取指针的当前位置，失败时 pos_type(-1)。

**例 1**

```cpp
// C++ program to demonstrate 
// example of tellg() function.
#include <bits/stdc++.h>
using namespace std;

int main()
{
    string str = "geeksforgeeks";
    istringstream in(str);

    string word;
    in >> word;
    cout << "After reading the word \"" << word
        << "\" tellg() returns " << in.tellg() << '\n';
}
```

**Output:**

```cpp
After reading the word "geeksforgeeks" tellg() returns -1

```

**例 2 :**

```cpp
// C++ program to demonstrate 
// example of tellg() function.
#include <bits/stdc++.h>
using namespace std;

int main()
{
    string str = "Hello, GFG";
    istringstream in(str);

    string word;    
    in >> word;

    cout << "After reading the word \"" << word
        << "\" tellg() returns " << in.tellg() << '\n';
}
```

**Output:**

```cpp
After reading the word "Hello," tellg() returns 6

```

**属性:-**
tellg()不报告文件的大小，也不报告从开始的偏移量(以字节为单位)。它报告一个令牌值，以后可以用来寻找同一个地方，仅此而已。(甚至不能保证可以将类型转换为整型)