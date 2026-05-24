# C++ |异常处理|问题 7

> 原文:[https://www . geesforgeks . org/c-异常处理-问题-7/](https://www.geeksforgeeks.org/c-exception-handling-question-7/)

```cpp
#include <iostream>
using namespace std;

int main()
{
    try
    {
        try
        {
            throw 20;
        }
        catch (int n)
        {
            cout << "Inner Catch\n";
            throw;
        }
    }
    catch (int x)
    {
        cout << "Outer Catch\n";
    }
    return 0;
}
```

**(甲)**

```cpp
Outer Catch
```

**(B)**

```cpp
Inner Catch
```

**(C)**

```cpp
Inner Catch
Outer Catch
```

**(D)** 编译器错误

**答案:** **(C)**

**解释:**语句“抛出；”用于重新引发异常。当函数可以处理部分异常处理，然后将剩余部分委托给调用方时，这很有用。catch 块清理其函数的资源，然后重新引发异常，以便在其他地方处理。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)