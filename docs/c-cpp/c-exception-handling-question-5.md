# C++ |异常处理|问题 5

> 原文:[https://www . geesforgeks . org/c-异常处理-问题-5/](https://www.geeksforgeeks.org/c-exception-handling-question-5/)

```cpp
#include <iostream>
using namespace std;

int main()
{
    try
    {
       throw 'a';
    }
    catch (int param)
    {
        cout << "int exception\n";
    }
    catch (...)
    {
        cout << "default exception\n";
    }
    cout << "After Exception";
    return 0;
}
```

**(甲)**

```cpp
default exception
After Exception
```

**(B)**

```cpp
int exception
After Exception
```

**(C)**

```cpp
int exception
```

**(D)**

```cpp
default exception
```

**回答:** **(A)**

**说明:**块 *catch(…)* 用于 catch all，当抛出异常的数据类型与其他任何 catch 块不匹配时，执行 catch(…)内部的代码。

请注意，当捕捉到异常时，隐式类型转换不会发生。字符“a”不会自动转换为 int。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)