# 如果我们在 C++ 中连接两个字符串会发生什么？

> 原文:[https://www . geeksforgeeks . org/发生-连接-两个字符串文字-c/](https://www.geeksforgeeks.org/happen-concatenate-two-string-literals-c/)

如果您要在 C++ 中执行串联，您必须记住的一些事情是:

*   If a+b is an expression showing string concatenation, the result of the expression will be a copy of the characters in "a" followed by the characters in "b".
*   "A" or "B" can be a string or a char value, but not both. That's why the connection below does not cause errors, while the connection above does.

例如:

```cpp
Input : "geeks"+"forgeeks"
Output : It will not compile, an error will be thrown.

```

**案例 1 :** 由于上述原因，我们**无法**串联以下表达式:

```cpp
"geeks" + "forgeeks" + geekstring  
```

这里，+的左结合性也在创建错误中起作用，因为+是左结合的，所以首先“极客”+“伪造者”将连接起来，这将创建如上所述的错误。

**案例 2 :** 我们**可以**连接以下:

```cpp
geekstring + "geeks" + "forgeeks" 
```

这里，左结合不会产生错误，因为它将连接极客字符串和“极客”，使其不是一个字面意思，然后“伪造”将被添加，不会产生错误。

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