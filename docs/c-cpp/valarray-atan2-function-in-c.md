# valarray atan2()函数在 C++ 中

> 原文:[https://www.geeksforgeeks.org/valarray-atan2-function-in-c/](https://www.geeksforgeeks.org/valarray-atan2-function-in-c/)

[atan2()](https://www.geeksforgeeks.org/?p=205568) 函数在 valarray 头文件中定义。此函数计算 valarray 中每个元素的(y/x)值的反正切，并返回包含所有元素的反正切的 valarray。其中 y 是 y 坐标的比例，x 是 x 坐标的比例。

**语法:**

```cpp
std::valarray res = atan2 (y-coords, x-coords)
```

**参数:**该函数接受两个强制参数，即 X 坐标和 Y 坐标。

**注意:**如果两个参数都是 valarray 对象，并且它们的大小不匹配，那么它们的行为是未定义的。

**返回:**这个函数返回一个包含所有元素的反正切的 valarray。

以下程序说明了上述功能:

**实施例 1:-**

```cpp
// atan2 valarray example
// programs illustrate the atan2() function:

#include <iostream>
#include <valarray>
using namespace std;

int main()
{
    // intilaize both the array X and Y coords
    double y[] = { 0.0, 3.0, -2.0 };
    double x[] = { -3.0, 3.0, -1.0 };

    // intilaize both the valarray X and Y coords
    valarray<double> ycoords(y, 3);
    valarray<double> xcoords(x, 3);

    // store results in valarray res
    valarray<double> res = atan2(ycoords, xcoords);

    // print results of atan2() function
    cout << "results:";
    for (size_t i = 0; i < res.size(); ++ i)
        cout << ' ' << res[i];
    cout << '\n';

    return 0;
}
```

**输出:**

```cpp
results: results: 3.14159 0.785398 -2.03444
```

**实施例 2:-**

```cpp
// atan2 valarray example
// programs illustrate the atan2() function:

#include <iostream>
#include <valarray>
using namespace std;

int main()
{
    // intilaize both the array X and Y coords
    double y[] = { 4.0, 5.6, -2.8, 7.3 };
    double x[] = { 5.0, -1.5, 7.0, -0.8 };

    // intilaize both the valarray X and Y coords
    valarray<double> ycoords(y, 4);
    valarray<double> xcoords(x, 4);

    // store results in valarray res
    valarray<double> res = atan2(ycoords, xcoords);

    // print results of atan2() function
    cout << "results:";
    for (size_t i = 0; i < res.size(); ++ i)
        cout << ' ' << res[i];
    cout << '\n';

    return 0;
}
```

**输出:**

```cpp
results: 0.674741 1.83251 -0.380506 1.67995
```

**示例 3:-** 错误和异常:当不同大小的 valarray 对象作为参数传递时，该函数不返回匹配的函数进行错误调用。

```cpp
// atan2 valarray example
// programs illustrate the atan2() function:

#include <iostream>
#include <valarray>
using namespace std;

int main()
{
    // intilaize both the array X and Y coords
    double y[] = { -2.8, 7.3 };
    float x[] = { 5.0, -0.8, 3.2, 5, 1 };

    // intilaize both the valarray X and Y coords
    valarray<double> ycoords(y, 2);
    valarray<float> xcoords(x, 4);

    // store results in valarray res
    valarray<double> res = atan2(ycoords, xcoords);

    // print results of atan2() function
    cout << "results:";
    for (size_t i = 0; i < res.size(); ++ i)
        cout << ' ' << res[i];
    cout << '\n';

    return 0;
}
```

**输出:**

```cpp
prog.cpp: In function 'int main()':
prog.cpp:14:48: error: no matching function for call to 'atan2(std::valarray&, std::valarray&)'
   valarray res = atan2 (ycoords, xcoords);
                                                ^

```