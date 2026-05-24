# 在 C 和 C++ 中将浮点数舍入到两位小数

> 原文:[https://www . geesforgeks . org/四舍五入-浮点数-小数点后两位-c-c/](https://www.geeksforgeeks.org/rounding-floating-point-number-two-decimal-places-c-c/)

如何将浮点值舍入到两个位置？例如，5.567 应该变成 5.57，5.534 应该变成 5.53

**第一种方法:-使用浮动精度**

## C++

```cpp
#include<bits/stdc++.h>
using namespace std;

int main()
{
    float var = 37.66666;

    // Directly print the number with .2f precision
    cout << fixed << setprecision(2) << var;
    return 0;
}

// This code is contributed by shivanisinghss2110
```

## C

```cpp
#include <iostream>
using namespace std;
int main()
{
    float var = 37.66666;

    // Directly print the number with .2f precision
    printf("%.2f", var);
    return 0;
}
```

```cpp
Output:
37.67
```

**第二种方法:使用整数类型转换**如果我们在函数中，那么如何返回两个小数点值

## C++

```cpp
#include <iostream>
using namespace std;
float round(float var)
{
    // 37.66666 * 100 =3766.66
    // 3766.66 + .5 =3767.16    for rounding off value
    // then type cast to int so value is 3767
    // then divided by 100 so the value converted into 37.67
    float value = (int)(var * 100 + .5);
    return (float)value / 100;
}

int main()
{
    float var = 37.66666;
    cout << round(var);
    return 0;
}
```

```cpp
Output:
37.67
```

**第三种方法:使用 sprintf()和 sscanf()**

## C++

```cpp
#include <iostream>
using namespace std;
float round(float var)
{
    // we use array of chars to store number
    // as a string.
    char str[40];

    // Print in string the value of var
    // with two decimal point
    sprintf(str, "%.2f", var);

    // scan string value in var
    sscanf(str, "%f", &var);

    return var;
}

int main()
{
    float var = 37.66666;
    cout << round(var);
    return 0;
}
```

```cpp
Output:
37.67
```

本文由**德万舒·阿加瓦尔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。