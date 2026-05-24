# c++ STL 中的 strtol()函数

> 原文:[https://www.geeksforgeeks.org/strtol-function-in-c-stl/](https://www.geeksforgeeks.org/strtol-function-in-c-stl/)

**strtol()** 函数是 C++ STL 中的内置函数，它将字符串的内容转换为指定基数的整数，并将其值作为长整型返回。

**语法**:

```cpp
strtol(s, &end, b)
```

**参数**:该功能接受三个强制参数，描述如下:

*   **s** :指定表示整数的字符串。
*   **end** :引用一个已经分配的 char*类型的对象。结束值由函数设置为 s 中最后一个有效字符之后的下一个字符。它也可以是空指针，在这种情况下不使用它。
*   **b** :指定到整数值的基数。

**返回值**:函数返回值有两种类型:

*   如果发生有效转换，则返回长整型值。
*   如果没有发生有效的转换，则返回 0。

下面的程序说明了上述功能。

**程序 1** :

```cpp
// C++ program to illustrate the
// strtol() function when decimal base
#include <cstdlib>
#include <cstring>
#include <iostream>
#include <string>
using namespace std;

int main()
{
    int b = 10;
    char s[] = "6010IG_2016p";
    char* end;
    long int n;

    n = strtol(s, &end, b);
    cout << "Number in  String = " << s << endl;
    cout << "Number in Long Int = " << n << endl;
    cout << "End String = " << end << endl
         << endl;

    // the pointer to invalid
    // characters can be null
    strcpy(s, "47");
    cout << "Number in  String = " << s << endl;
    n = strtol(s, &end, b);
    cout << "Number in Long Int = " << n << endl;
    if (*end) {
        cout << end;
    }
    else {
        cout << "Null pointer";
    }
    return 0;
}
```

**Output:**

```cpp
Number in  String = 6010IG_2016p
Number in Long Int = 6010
End String = IG_2016p

Number in  String = 47
Number in Long Int = 47
Null pointer

```

**程序 2** :

```cpp
// C++ program to illustrate the
// strtol() function
#include <cstdlib>
#include <cstring>
#include <iostream>
using namespace std;

int main()
{
    char* end;

    cout << "489bc"
         << " to Long Int with base-4 = "
         << strtol("489bc", &end, 4) << endl;
    cout << "End String = " << end << endl;

    cout << "123s"
         << " to Long Int with base-11 = "
         << strtol("123s", &end, 11) << endl;
    cout << "End String = " << end << endl;

    cout << "56xyz"
         << " to Long Int with base-36 = "
         << strtol("56xyz", &end, 36) << endl;
}
```

**Output:**

```cpp
489bc to Long Int with base-4 = 0
End String = 489bc
123s to Long Int with base-11 = 146
End String = s
56xyz to Long Int with base-36 = 8722043

```

**程序 3** :

```cpp
// C++ program to illustrate the
// strtol() function when base is 0
#include <cstdlib>
#include <iostream>

using namespace std;

int main()
{
    char* end;

    // octal base
    cout << "312gfg"
         << " to Long Int with base-0 = "
         << strtol("312gfg", &end, 0) << endl;
    cout << "End String = " << end << endl
         << endl;

    // hexadecimal base
    cout << "0q15axtz"
         << " to Long Int with base-0 = "
         << strtol("0q15axtz", &end, 0) << endl;
    cout << "End String = " << end << endl
         << endl;

    // decimal base
    cout << "33ffn"
         << " to Long Int with base-0 = "
         << strtol("33ffn", &end, 0) << endl;
    cout << "End String = ";

    return 0;
}
```

**Output:**

```cpp
312gfg to Long Int with base-0 = 312
End String = gfg

0q15axtz to Long Int with base-0 = 0
End String = q15axtz

33ffn to Long Int with base-0 = 33
End String =

```

**程序 4**

```cpp
// C++ program to illustrate the
// strtol() function for invalid
// conversions and leading whitespaces.
#include <cstdlib>
#include <iostream>
using namespace std;

int main()
{
    char* end;

    cout << "22abcd"
         << " to Long Int with base-6 = "
         << strtol("  22abcd", &end, 6) << endl;
    cout << "End String = " << end << endl
         << endl;

    cout << "114cd"
         << " to Long Int with base-2 = "
         << strtol("   114cd", &end, 2) << endl;
    cout << "End String = " << end << endl
         << endl;

    cout << "e10.79"
         << " to Long Int with base-10 = "
         << strtol("e10.79", &end, 10) << endl;

    cout << "End String = " << end << endl
         << endl;

    return 0;
}
```

**Output:**

```cpp
22abcd to Long Int with base-6 = 14
End String = abcd

114cd to Long Int with base-2 = 3
End String = 4cd

e10.79 to Long Int with base-10 = 0
End String = e10.79

```