# 在 C 中使用布尔

> 原文:[https://www.geeksforgeeks.org/bool-in-c/](https://www.geeksforgeeks.org/bool-in-c/)

**先决条件:**[c++ 中的 bool 数据类型](https://www.geeksforgeeks.org/bool-data-type-in-c/)
C 语言的 [C99 标准](http://en.wikipedia.org/wiki/C99)支持 Bool 变量。与使用 bool 不需要头文件的 C++ 不同，在 C 中使用 bool 必须包含头文件“stdbool.h”。c，它不会编译，但是如果我们把它另存为。cpp，它会工作得很好。

## C

```cpp
int main()
{
  bool arr[2] = {true, false};
  return 0;
}
```

如果我们在上面的程序中包含头文件“stdbool.h”，它将作为一个 C 程序正常工作。

## C

```cpp
#include <stdbool.h>
int main()
{
    bool arr[2] = { true, false };
    return 0;
}
```

用 C 语言的枚举函数还有一种方法。您可以使用枚举创建一个 bool。一个枚举将被创建为 bool，然后将枚举的元素分别设置为 True 和 False。false 将在第一个位置，因此它将保持 0，true 将在第二个位置，因此它将获得值 1。

下面是上述想法的实现:

## C

```cpp
// C implementation of the above idea
#include <stdio.h>

// Declaration of enum
typedef enum { F, T } boolean;

int main()
{
    boolean bool1, bool2;
    bool1 = F;

    if (bool1 == F) {
        printf("bool1 is false\n");
    }
    else {
        printf("bool1 is true\n");
    }
    bool2 = 2;
    if (bool2 == F) {
        printf("bool2 is false\n");
    }
    else {
        printf("bool2 is true\n");
    }
}
```

**Output**

```cpp
bool1 is false
bool2 is true

```