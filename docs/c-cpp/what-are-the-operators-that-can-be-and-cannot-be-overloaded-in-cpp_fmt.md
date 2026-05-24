# c++ 中有哪些可以重载和不能重载的运算符？

> 原文: [https://www.geeksforgeeks.org/what-are-the-operators-that-can-be-and-cannot-be-overloaded-in-cpp/](https://www.geeksforgeeks.org/what-are-the-operators-that-can-be-and-cannot-be-overloaded-in-cpp/)

在 C++ 中，有多种方法可以通过实现以下任何类型的函数来重载运算符：

- 成员功能
- 非成员功能
- 好友功能

## 可能超载的运算子清单为：

| 运算符 | 运算符 | 运算符 | 运算符 |
| :--- | :--- | :--- | :--- |
| `+` | `-` | `*` | `/` |
| `%` | `^` | `&` | `\|` |
| `~` | `!` | `,` | `=` |
| `<` | `>` | `<=` | `>=` |
| `++` | `--` | `<<` | `>>` |
| `==` | `!=` | `&&` | `\|\|` |
| `+=` | `-=` | `/=` | `%=` |
| `^=` | `&=` | `\|=` | `*=` |
| `<<=` | `>>=` | `[]` | `()` |
| `->` | `->*` | `new` | `new[]` |
| `delete` | `delete[]` | | |

## 例 1: 重载++ 运算符

### CPP program to illustrate operators that can be overloaded

```cpp
#include <iostream>
using namespace std;

class overload {
private:
    int count;

public:
    overload()
        : count(4)
    {
    }

    void operator++() { count = count + 1; }
    void Display() { cout << "Count: " << count; }
};

int main()
{
    overload i;
    // this calls "function void operator ++()" function
    ++ i;
    i.Display();
    return 0;
}
```

**Output**

```
Count: 5
```