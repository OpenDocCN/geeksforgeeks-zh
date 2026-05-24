# C/C++ 中的宏及其类型

> 原文：[https://www.geeksforgeeks.org/macros-and-its-types-in-c-cpp/](https://www.geeksforgeeks.org/macros-and-its-types-in-c-cpp/)

一个[**宏**](https://www.geeksforgeeks.org/c-language-2-gq/macro-preprocessor-gq/)是程序中的一段代码，由宏的值代替。宏由`#define`指令定义。每当编译器遇到宏名时，它会用宏的定义替换该名称。宏定义不用分号（`;`）终止。

下面是说明宏在 C/C++ 中使用的程序：

### 程序 1

#### C

```cpp
// C program to illustrate macros
#include <stdio.h>

// Macro definition
#define LIMIT 5

// Driver Code
int main()
{
    // Print the value of macro defined
    printf("The value of LIMIT"
           " is %d",
           LIMIT);

    return 0;
}
```

#### C++

```cpp
// C++ program to illustrate macros
#include <iostream>
using namespace std;

// Macro definition
#define LIMIT 5

// Driver Code
int main()
{
    // Print the value of macro defined
    cout << "The value of LIMIT"
         << " is " << LIMIT;

    return 0;
}
```

**输出：**

```cpp
The value of LIMIT is 5
```

### 程序 2

#### C

```cpp
// C program to illustrate macros
#include <stdio.h>

// Macro definition
#define AREA(l, b) (l * b)

// Driver Code
int main()
{
    // Given lengths l1 and l2
    int l1 = 10, l2 = 5, area;

    // Find the area using macros
    area = AREA(l1, l2);

    // Print the area
    printf("Area of rectangle"
           " is: %d",
           area);

    return 0;
}
```

#### C++

```cpp
// C++ program to illustrate macros
#include <iostream>
using namespace std;

// Macro definition
#define AREA(l, b) (l * b)

// Driver Code
int main()
{
    // Given lengths l1 and l2
    int l1 = 10, l2 = 5, area;

    // Find the area using macros
    area = AREA(l1, l2);

    // Print the area
    cout << "Area of rectangle"
         << " is: ",
        area;

    return 0;
}
```

**输出：**

```cpp
Area of rectangle is: 50
```