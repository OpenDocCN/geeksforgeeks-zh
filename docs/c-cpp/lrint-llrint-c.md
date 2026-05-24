# c++ 中的 lrint()和 llrint()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/lrint-llrint-c/

lrint()函数使用当前舍入模式将参数中给出的小数值舍入为整数值。
这里，电流模式由函数 fesetround()决定。

**注意:**该函数返回长整型的最终值。
**语法:**

```cpp
lrint(double a);
lrint(float a);

```

> **参数:**
> 
> *   The lrint() function takes double or float or integer value as an argument.
>     
>     **返回:**
>     
>     
>     
>     *   The lrint() function rounds the fractional value given in the argument to an integral value using the current rounding mode and return value in a long int. Here, the current mode is determined by the function fesetround(). By default, the rounding direction is set to ‘to-nearest’.
>     It can be changed using fesetround().
>     
>     **错误:**
>     
>     *   必须给出一个参数，否则会给出错误**没有匹配的函数来调用像这样的‘lrint()’**。

**#代码 1**

```cpp
// CPP code to illustrate
// the functionality of lrint()
#include <cfenv>
#include <cmath>
#include <iostream>
using namespace std;

int main()
{
    int a = 15;
    long int answer;

    // setting rounding direction to DOWNWARD
    fesetround(FE_DOWNWARD);
    answer = lrint(a);
    cout << "Downward rounding of " << a 
         << " is " << answer << endl;

    return 0;
}
```

**输出:**

```cpp
Downward rounding of 15 is 15

```

**#代码 2**

```cpp
// CPP code to illustrate
// the functionality of lrint()
#include <cfenv>
#include <cmath>
#include <iostream>
using namespace std;

int main()
{
    double a;
    long int answer;

    // By default, the rounding direction
    // is set to 'to-nearest'.
    // fesetround(FE_TONEAREST)
    a = 50.35;
    answer = lrint(a);
    cout << "Nearest rounding of " << a 
         << " is " << answer << endl;

    // mid values are rounded off to higher integer
    a = 50.5;
    answer = lrint(a);
    cout << "Nearest rounding of " << a 
         << " is " << answer << endl;

    return 0;
}
```

**输出:**

```cpp
Nearest rounding of 50.35 is 50
Nearest rounding of 50.5 is 50

```

**#代码 3**

```cpp
// CPP code to illustrate
// the functionality of lrint()
#include <cfenv>
#include <cmath>
#include <iostream>
using namespace std;

int main()
{
    double a;
    long int answer;

    // Now, the rounding direction
    // is set to UPWARD
    fesetround(FE_UPWARD);
    a = 50.3;
    answer = lrint(a);
    cout << "Upward rounding of " << a 
         << " is " << answer << endl;

    // Now, the rounding direction
    //  is set to DOWNWARD
    fesetround(FE_DOWNWARD);
    a = 50.88;
    answer = lrint(a);
    cout << "Downward rounding of " << a 
         << " is " << answer << endl;

    return 0;
}
```

**输出:**

```cpp
Upward rounding of 50.3 is 51
Downward rounding of 50.88 is 50

```

c++ 中的 llrint()

llrint()函数使用当前舍入模式将参数中给定的小数值舍入为整数值。
这里，电流模式由函数 fesetround()决定。

**注意:**因此函数返回长整型值
**语法:**

```cpp
llrint(double a);
llrint(float a);

```

> **参数:**
> 
> *   The llrint() function takes double or float or integer value as an argument.
>     
>     **返回:**
>     
>     *   The llrint() function rounds the fractional value given in the argument to
>     an integral value using the current rounding mode and and return value in
>     long long int.
>     Here, the current mode is determined by the function fesetround().
>     By default, the rounding direction is set to ‘to-nearest’.
>     It can be changed using fesetround().
>     
>     **错误:**
>     
>     *   必须给出一个参数，否则会给出错误**没有匹配的函数来调用像这样的‘ll rint()’**。

**#代码 1**

```cpp
// CPP code to illustrate
// the functionality of llrint()
#include <cfenv>
#include <cmath>
#include <iostream>
using namespace std;

int main()
{
    int a = 15;
    long long int answer;

    // setting rounding direction to DOWNWARD
    fesetround(FE_DOWNWARD);
    answer = llrint(a);
    cout << "Downward rounding of " << a 
         << " is " << answer << endl;

    return 0;
}
```

**输出:**

```cpp
Downward rounding of 15 is 15

```

**#代码 2**

```cpp
// CPP code to illustrate
// the functionality of llrint()
#include <cfenv>
#include <cmath>
#include <iostream>
using namespace std;

int main()
{
    double a;
    long long int answer;

    // By default, the rounding direction is 
    // set to 'to-nearest'. fesetround(FE_TONEAREST)
    a = 50.35;
    answer = llrint(a);
    cout << "Nearest rounding of " << a 
         << " is " << answer << endl;

    // mid values are rounded off to higher integer
    a = 50.5;
    answer = llrint(a);
    cout << "Nearest rounding of " << a 
         << " is " << answer << endl;

    return 0;
}
```

**输出:**

```cpp
Nearest rounding of 50.35 is 50
Nearest rounding of 50.5 is 50

```

**#代码 3**

```cpp
// CPP code to illustrate
// the functionality of llrint()
#include <cfenv>
#include <cmath>
#include <iostream>
using namespace std;

int main()
{
    double a;
    long long int answer;

    // Now, the rounding direction
    // is set to UPWARD
    fesetround(FE_UPWARD);
    a = 50.3;
    answer = llrint(a);
    cout << "Upward rounding of " << a 
         << " is " << answer << endl;

    // Now, the rounding direction is set to DOWNWARD
    fesetround(FE_DOWNWARD);
    a = 50.88;
    answer = llrint(a);
    cout << "Downward rounding of " << a 
         << " is " << answer << endl;

    return 0;
}
```

**输出:**

```cpp
Upward rounding of 50.3 is 51
Downward rounding of 50.88 is 50

```