# C++ |异常处理|问题 1

> 原文:[https://www . geesforgeks . org/c-异常处理-问题-1/](https://www.geeksforgeeks.org/c-exception-handling-question-1/)

```cpp
#include <iostream>
using namespace std;
int main()
{
   int x = -1;
   try {
      cout << "Inside try \n";
      if (x < 0)
      {
         throw x;
         cout << "After throw \n";
      }
   }
   catch (int x ) {
      cout << "Exception Caught \n";
   }

   cout << "After catch \n";
   return 0;
}
```

**(甲)**

```cpp
Inside try
Exception Caught
After throw 
After catch
```

**(B)**

```cpp
Inside try
Exception Caught
After catch
```

**(C)**

```cpp
Inside try
Exception Caught
```

**(D)**

```cpp
Inside try
After throw
After catch
```

**回答:** **(B)**

**说明:**抛出异常时，抛出语句后的 try block 行不执行。

当异常被捕获时，执行 catch 块之后的代码。Catch 块通常写在末尾。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)