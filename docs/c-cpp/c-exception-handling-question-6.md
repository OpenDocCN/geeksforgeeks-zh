# C++ |异常处理|问题 6

> 原文:[https://www . geesforgeks . org/c-异常处理-问题-6/](https://www.geeksforgeeks.org/c-exception-handling-question-6/)

```cpp
#include <iostream>
using namespace std;

int main()
{
    try
    {
       throw 10;
    }
    catch (...)
    {
        cout << "default exception\n";
    }
    catch (int param)
    {
        cout << "int exception\n";
    }

    return 0;
}
```

**(A)** 默认异常
**(B)** int 异常
**(C)** 编译器错误

**答案:****(C)**

**解释:**将 catch 全部块放在任何其他 catch 之前是编译器错误。捕捉(…)必须是最后一个捕捉块。

[本题小测验](https://www.geeksforgeeks.org/quiz-corner-gq/)