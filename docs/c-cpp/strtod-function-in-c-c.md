# strtod()函数在 C/C++ 中

> 原文:[https://www.geeksforgeeks.org/strtod-function-in-c-c/](https://www.geeksforgeeks.org/strtod-function-in-c-c/)

**strtod()** 是 C 和 C++ STL 中的一个内置函数，它将字符串的内容解释为浮点数，并将其值返回为双精度值。
它设置一个指针指向字符串最后一个有效字符之后的第一个字符，如果有的话，否则将指针设置为空。

**语法**:

```cpp
double strtod(str, &end)
```

**参数** :
**字符串**:指定表示浮点数的字符串。
**结束:指定的参数是指已经分配的 char*类型的对象。**

****返回值**:返回一个双精度值，由字符串转换而来，如果无法进行有效转换，则返回 0。**

**以下程序说明了上述功能:**

****程序 1** :**

```cpp
// C++ program to illustrate the
// strtod() function
#include <cstdlib>
#include <iostream>

using namespace std;

int main()
{
    char str[] = "11.03e 0mn";
    char* end;
    double number;

    number = strtod(str, &end);
    cout << "number = " << str << endl;
    cout << "double = " << number << endl;
    cout << "end string = " << end << endl;

    return 0;
}
```

****Output:**

```cpp
number = 11.03e 0mn
double = 11.03
end string = e 0mn

```** 

****程序 2** :**

```cpp
// C++ program to illustrate the
// strtod() function without trailing characters
#include <cstdlib>
#include <iostream>

using namespace std;

int main()
{
    char str[] = "4.06";
    char* end;
    double number;

    number = strtod(str, &end);
    cout << "number= " << str << endl;
    cout << "double= " << number << endl;

    // If end is not Null
    if (*end) {
        cout << end;
    }
    // If end is Null
    else {
        cout << "null";
    }
    return 0;
}
```

****Output:**

```cpp
number= 4.06
double= 4.06
null

```** 

****程序 3** :
用指数和十六进制数构造()函数**

```cpp
// C++ program to illustrate the
// strtod() function with exponents and hexadecimals
#include <cstdlib>
#include <cstring>
#include <iostream>

using namespace std;
int main()
{
    // initialize a exponential value
    char str[] = "-89.04e-3win gfg";
    char* end;
    double number;

    number = strtod(str, &end);
    cout << "str = " << str << endl;
    cout << "double = " << number << endl;
    cout << "end string = " << end << endl
         << endl;

    // initialize a new hexadecimal value
    strcpy(str, "1998gupta.1204ishwar");

    number = strtod(str, &end);
    cout << "str = " << str << endl;
    cout << "double = " << number << endl;
    cout << "end string = " << end << endl;

    return 0;
}
```

****Output:**

```cpp
str = -89.04e-3win gfg
double = -0.08904
end string = win gfg

str = 1998gupta.1204ishwar
double = 1998
end string = gupta.1204ishwar

```** 

****程序 4** :**

```cpp
// C++ program to illustrate the
// strtod() function for Infinity and NaN
#include <cstdlib>
#include <iostream>

using namespace std;

int main()
{
    char* end;

    cout << "Infinity"
         << " to double = " 
         << strtod("infinity", &end) << endl;
    cout << "end string = " << end << endl
         << endl;

    cout << "Infpqrs"
         << " to double = " << 
         strtod("Infpqrs", &end) << endl;
    cout << "end string = " << end << endl
         << endl;

    cout << "NaN11x"
         << " to double = " 
         << strtod("NaN11x", &end) << endl;
    cout << "end string = " << end << endl
         << endl;

    return 0;
}
```

****Output:**

```cpp
Infinity to double = inf
end string = 

Infpqrs to double = inf
end string = pqrs

NaN11x to double = nan
end string = 11x

```** 

****程序 5** :带前导空格的
strtod()函数**

```cpp
// C++ program to illustrate the
// strtod() function with leading whitespace
#include <cstdlib>
#include <iostream>

using namespace std;

int main()
{
    char* end;

    cout << "99.99"
         << " to double = " 
         << strtod(" 19.99", &end) << endl;
    // end pointer is set to null
    cout << "end string = " 
         << end << endl
         << endl;

    // Returns 0 because of invalid conversion
    cout << "xyz1.80"
         << " to double = " 
         << strtod("xyz1.80", &end) << endl;
    cout << "end string = " << end << endl
         << endl;

    return 0;
}
```

****Output:**

```cpp
99.99 to double = 19.99
end string = 

xyz1.80 to double = 0
end string = xyz1.80

```**