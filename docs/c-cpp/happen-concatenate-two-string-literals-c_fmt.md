# 如果我们在 C++ 中连接两个字符串会发生什么？

> 原文: [https://www.geeksforgeeks.org/happen-concatenate-two-string-literals-c/](https://www.geeksforgeeks.org/happen-concatenate-two-string-literals-c/)

如果您要在 C++ 中执行串联，您必须记住的一些事情是:
*   如果 `a+b` 是一个显示字符串串联的表达式，该表达式的结果将是 `"a"` 中字符的副本，后跟 `"b"` 中的字符。
*   `"A"` 或 `"B"` 可以是一个字符串或一个 `char` 值，但不能两者都是。这就是为什么下面的连接不会导致错误，而上面的连接会。

例如:
```cpp
Input : "geeks"+"forgeeks"
Output : It will not compile, an error will be thrown.
```

## 案例 1 :
由于上述原因，我们无法串联以下表达式:
```cpp
"geeks" + "forgeeks" + geekstring
```
这里，`+` 的左结合性也在创建错误中起作用，因为 `+` 是左结合的，所以首先 `"geeks" + "forgeeks"` 将连接起来，这将创建如上所述的错误。

## 案例 2 :
我们可以连接以下:
```cpp
geekstring + "geeks" + "forgeeks"
```
这里，左结合不会产生错误，因为它将连接 `geekstring` 和 `"geeks"`，使其不是一个字面量，然后 `"forgeeks"` 将被添加，不会产生错误。

```cpp
Input : geekstring = "geeks"
Input : geekstring + "forgeeks"
Output: geeksforgeeks
```

```cpp
// Program to illustrate two string
// literal can not be concatenate
#include <iostream>
using namespace std;
int main()
{
    string geekstring = "geeks";
    cout << geekstring + "forgeeks" << endl;

// while this will not work
    // cout<<"geeks" + "forgeeks";

// this will work
    cout << geekstring + "forgeeks" + " Hello";

// but again this will not work
    // cout<<"forgeeks" + "hello" + geekstring;
    return 0;
}
```

输出:
```cpp
geeksforgeeks
geeksforgeeks Hello
```