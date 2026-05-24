# 在 C++ 中失败

> 原文:[https://www.geeksforgeeks.org/fallthrough-in-c/](https://www.geeksforgeeks.org/fallthrough-in-c/)

**Fall through** 是出现在各种编程语言中的一种错误，如[C](https://www.geeksforgeeks.org/c-programming-language/)[c++ ](https://www.geeksforgeeks.org/c-plus-plus/)[Java](https://www.geeksforgeeks.org/java/)[Dart](https://www.geeksforgeeks.org/dart-standard-input-output/)等。它出现在 [switch-case 语句](https://www.geeksforgeeks.org/switch-statement-cc/) 中，当我们忘记添加 a [break 语句](https://www.geeksforgeeks.org/break-statement-cc/) 时，在这种情况下 [的控制流会跳转到下一行](https://www.geeksforgeeks.org/decision-making-c-c-else-nested-else/) 。因此，当任何情况与指定值匹配时，控制会转移到后续情况，直到找到 break 语句。在 [C++ ](https://www.geeksforgeeks.org/c-plus-plus/) 中，[错误](https://www.geeksforgeeks.org/program-error-signals/)不是在**通过**出现，而是在像 [Dart](https://www.geeksforgeeks.org/exception-handling-in-dart/) 这样的语言中，每当**通过**出现时，就会出现错误。

不一定要避免**从**滑落，但也可以作为优势。

**程序 1:**

以下是说明跌落是如何发生的程序:

## C++

```cpp
// C++ program to illustrate
// Fallthrough in C++
#include <iostream>
using namespace std;

// Driver Code
int main()
{
    int n = 2;

    // Switch Cases
    switch (n) {
    case 1: {
        cout << "this is one \n";
    }
    case 2: {
        cout << "this is two \n";
    }
    case 3: {
        cout << "this is three \n";
    }
    default: {
        cout << "this is default \n";
    }
    }

    return 0;
}
```

**Output:**

```cpp
this is two 
this is three 
this is default

```

**说明:**在上面的代码中，没有 break 语句，因此在与第二种情况匹配后，控件将失败，后续语句也将被打印。

**<u>如何避免坠入</u>？**

为了避免失败，我们的想法是在每个案例之后使用一个 break 语句，这样在匹配之后，它就脱离了 switch 语句，控制权转移到 switch 语句旁边的语句。

**程序 2:**

下面是说明如何避免失败的程序:

## C++

```cpp
// C++ program to illustrate how to
// avoid fall through
#include <iostream>
using namespace std;

// Driver Code
int main()
{
    int n = 2;

    // Switch Cases
    switch (n) {
    case 1: {
        cout << "this is one \n";
        break;
    }

    case 2: {
        cout << "this is two \n";

        // After this break statement
        // the control goes out of
        // the switch statement
        break;
    }
    case 3: {
        cout << "this is three \n";
        break;
    }
    default: {
        cout << "this is default \n";
        break;
    }
    }

    return 0;
}
```

**Output:**

```cpp
this is two

```