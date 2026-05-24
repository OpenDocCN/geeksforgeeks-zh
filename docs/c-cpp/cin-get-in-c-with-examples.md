# cin 在 C++ 中用例子得到()

> 原文:[https://www.geeksforgeeks.org/cin-get-in-c-with-examples/](https://www.geeksforgeeks.org/cin-get-in-c-with-examples/)

**cin.get()** 用于访问字符数组。它包括空白字符。通常，当发现空白时，带有提取操作符(> >)的 [cin](https://www.geeksforgeeks.org/basic-input-output-c/) 终止。但是，cin.get()读取带有空格的字符串。

**语法:**

```cpp
cin.get(string_name, size);
```

**例 1:**

```cpp
// C++ program to demonstrate cin.get()

#include <iostream>
using namespace std;

int main()
{
    char name[25];
    cin.get(name, 25);
    cout << name;

    return 0;
}
```

**输入:**

```cpp
Geeks for Geeks
```

**输出:**

```cpp
Geeks for Geeks
```

**例 2:**

```cpp
// C++ program to demonstrate cin.get()

#include <iostream>
using namespace std;

int main()
{
    char name[100];
    cin.get(name, 3);
    cout << name;

    return 0;
}
```

**输入:**

```cpp
GFG
```

**输出:**

```cpp
GF
```