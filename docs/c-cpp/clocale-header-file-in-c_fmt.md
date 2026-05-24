# C++ 中的时钟头文件

> 原文：[https://www.geeksforgeeks.org/clocale-header-file-in-c/](https://www.geeksforgeeks.org/clocale-header-file-in-c/)

`clocale`：这个头文件包含一组函数的声明和国际化支持任务的类型。它支持日期格式或国家特定的货币符号。例如，日期/时间格式、货币格式等等。

## `clocale` 头文件中的方法

### 1. `localeconv()`

此函数返回一个对象，该对象表示当前 C 语言环境的数字和货币格式化规则。其对应的头文件是 `<clocale>`。“C”语言环境是最小的语言环境。它是一个在所有编译器中设置都相同、因此结果可预测的语言环境。默认情况下，所有 C 程序都使用它。

**原型**

```cpp
lconv* localeconv();
```

**参数：** 该方法没有参数。

**返回值：** 该函数返回一个指向静态对象的指针，该静态对象包含当前 C 语言环境的数字和货币格式规则。

**程序：**

```cpp
#include <iostream>
#include <locale.h>
using namespace std;

int main()
{
    setlocale(LC_MONETARY, "en_US.utf8");
    struct lconv* lc = localeconv();
    printf("%s ", lc->currency_symbol);
    return 0;
}
```

**输出：**

```cpp
$
```

### 2. `setlocale()`

`setlocale()` 函数安装指定的系统语言环境。此外，它还为当前 C 程序设置语言环境信息。它也可用于查询当前的 C 语言环境。它有一些参数，分别是：
*   `LC_ALL`：选择所有的 C 语言环境
*   `LC_NUMERIC`：选择数字格式类别
*   `LC_MONETARY`：货币格式类别
*   `LC_CTYPE`：字符分类类别
*   `LC_TIME`：时间格式类别

**原型：**

```cpp
int setlocale(int category, const char* locale);
```

**返回值：** 应用更改后返回一个标识 C 语言环境的字符串指针。否则，它将返回空指针。

**程序：**

```cpp
#include <clocale>
#include <iostream>
using namespace std;

int main()
{
    char* s;
    setlocale(LC_ALL, "en_UA.utf8");
    s = setlocale(LC_ALL, NULL);
    cout << s << "\n";
    return 0;
}
```

**输出：**

```cpp
C
```