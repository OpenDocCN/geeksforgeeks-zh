# C/c++ 中连接字符串的方法，示例

> 原文:[https://www . geesforgeks . org/methods-to-concatenate-string-in-c-with-examples/](https://www.geeksforgeeks.org/methods-to-concatenate-string-in-c-c-with-examples/)

有多种方法可以连接字符串。我们将逐一讨论。

**方法一:使用 **strcat()** 功能。**

strcat()函数是在“string.h”头文件中定义的。

**语法:**

```cpp
char * strcat(char * init, const char * add)

```

初始化和添加字符串应该是字符数组(char*)。该函数将添加的字符串连接到 init 字符串的末尾。

**示例:**

```cpp
#include <bits/stdc++.h>
using namespace std;

int main()
{
    char init[] = "this is init";
    char add[] = " added now";

    // concatenating the string.
    strcat(init, add);

    cout << init << endl;

    return 0;
}
```

**Output:**

```cpp
this is init added now

```

**方法二:使用**追加()**功能。**

**语法:**

```cpp
string& string::append (const string& str)

str: the string to be appended.

```

这里 str 是 std::string 类的对象，它是 basic_string 类模板的实例，使用 char(即字节)作为其字符类型。append 函数在 init 字符串的末尾追加 add(变量)字符串。

**示例:**

```cpp
#include <bits/stdc++.h>
using namespace std;

int main()
{
    string init("this is init");
    string add(" added now");

    // Appending the string.
    init.append(add);

    cout << init << endl;
    return 0;
}
```

**Output:**

```cpp
this is init added now

```

**方法三:使用 **'+'** 算子**

**语法:**

```cpp
string new_string = string init + string add;

```

这是连接两个字符串最简单的方法。+运算符只是将两个字符串相加，并返回一个串联的字符串。

**示例:**

```cpp
#include <bits/stdc++.h>
using namespace std;

int main()
{
    string init("this is init");
    string add(" added now");

    // Appending the string.
    init = init + add;

    cout << init << endl;
    return 0;
}
```

**Output:**

```cpp
this is init added now

```