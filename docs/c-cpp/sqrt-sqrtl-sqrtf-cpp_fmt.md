# c++ 中的 `sqrt`、`sqrtl` 和 `sqrtf`

> 哎哎哎:# t0]https://www . geeksforgeeks . org/sqrt-sqrtl-sqrtf-CPP/

`cmath` 头文件定义了另外两个用于计算一个数的平方根的内置函数（除了 `sqrt` 之外，`sqrt` 以 `double` 作为参数），`sqrt` 的参数类型为 `float` 和 `long double`。

## `double sqrt(double arg)`

它返回一个数字的平方根，类型为 `double`。

语法：`double sqrt(double arg)`

```cpp
// CPP code to illustrate
// the use of sqrt function.
#include <cmath>
#include <iomanip>
#include <iostream>

using namespace std;

int main()
{
    double val1 = 225.0;
    double val2 = 300.0;

    cout << fixed << setprecision(12) << sqrt(val1) << endl;
    cout << fixed << setprecision(12) << sqrt(val2) << endl;

    return (0);
}
```

**输出：**

```cpp
15.000000000000
17.320508075689
```

### 与此功能相关的错误和异常
（感谢 sunny6041 对此部分的贡献）

1.  必须提供参数，否则会引发错误，例如 `no matching function for call to ‘sqrt()’`。

```cpp
#include <iostream>
#include <cmath>
using namespace std;

int main()
{
    double answer;

    answer = sqrt();
    cout << "Square root of " << a
         << " is " << answer << endl;

    return 0;
}
```

**输出：**

```cpp
prog.cpp:9:16: error: no matching function for call to 'sqrt()'
```

2.  如果我们向参数传递一个负值，则会发生定义域错误。输出将是 `Square root of -a is -nan`。

```cpp
#include <iostream>
#include <cmath>
using namespace std;

int main()
{
    double a = -2 ,  answer;

    answer = sqrt(a);
    cout << "Square root of " << a
         << " is " << answer << endl;

    return 0;
}
```

**输出：**

```cpp
Square root of -2 is -nan
```

## `float sqrtf(float arg)`

返回一个数字的平方根，输入 `float` 类型。

语法：`float sqrtf(float arg)`

```cpp
// CPP code to illustrate
// the use of sqrtf function.
#include <cmath>
#include <iomanip>
#include <iostream>

using namespace std;

int main()
{
    float val1 = 225.0;
    float val2 = 300.0;

    cout << fixed << setprecision(12) << sqrtf(val1) << endl;
    cout << fixed << setprecision(12) << sqrtf(val2) << endl;

    return (0);
}
```

**输出：**

```cpp
15.000000000000
17.320508956909
```

## `long double sqrtl(long double arg)`

它返回一个数字的平方根，类型为 `long double`，精度更高。使用此函数的优点是，当处理数量级为 `10^18` 的整数时，由于编程语言中的默认函数使用浮点数/双精度数进行计算，使用 `sqrt` 函数计算其平方根可能会因精度错误而给出错误的答案。但 `sqrtl` 总是能给出准确的答案。

语法：`long double sqrtl(long double arg)`

下图显示了使用 `sqrt` 和 `sqrtl` 处理长整数时的确切区别。

### 使用 `sqrt` 功能

```cpp
// CPP code to illustrate
// the incorrectness of sqrt function.
#include <cmath>
#include <iomanip>
#include <iostream>

using namespace std;

int main()
{
    long long int val1 = 1000000000000000000;
    long long int val2 = 999999999999999999;

    cout << fixed << setprecision(12) << sqrt(val1) << endl;
    cout << fixed << setprecision(12) << sqrt(val2) << endl;

    return (0);
}
```

**输出：**

```cpp
1000000000.000000000000
1000000000.000000000000
```

### 使用 `sqrtl` 功能

```cpp
// CPP code to illustrate
// the correctness of sqrtl function.
#include <cmath>
#include <iomanip>
#include <iostream>

using namespace std;

int main()
{
    long long int val1 = 1000000000000000000;
    long long int val2 = 999999999999999999;

    cout << fixed << setprecision(12) << sqrtl(val1) << endl;
    cout << fixed << setprecision(12) << sqrtl(val2) << endl;

    return (0);
}
```

**输出：**

```cpp
1000000000.000000000000
999999999.999999999476
```