# C/C++ 中的 float.h，带示例

> 原文：[https://www.geeksforgeeks.org/cfloat-float-h-in-c-c-with-examples/](https://www.geeksforgeeks.org/cfloat-float-h-in-c-c-with-examples/)

这个头文件由*平台相关的*和*实现特定的*浮点值组成。一个浮点有*四个部分*。

*   **符号**
    它的值可以是负数，也可以是非负数。
*   **基**
    又称为**基**的指数表示，用一个数字表示不同的数字，即二进制为 2，十进制为 10，十六进制为 16，…
*   **尾数**
    又称**意符**。它是基数的一系列数字。数列中的位数称为 **精度**。
*   **指数**
    又称为**特征**是介于最小值 **e<sub>min</sub>** 和最大值 **e<sub>max</sub>** 之间的整数。

> **浮点值 = 精度 X 基数<sup>指数</sup>**

**宏常数**

库宏是浮点类型的硬件特定值。`FLT` 暗示类型 `float`、`DBL` 暗示 `double`、`LDBL` 暗示 `long double`、`DIG` 暗示 `digit`、`MANT` 暗示 `mantissa`、`EXP` 暗示 `exponent`。

1.  **`FLT_RADIX`**：所有浮点类型的基数。
    ```cpp
    Minimum value is 2
    ```

2.  **`FLT_DIG`**：可以舍入为浮点类型并再次舍入到相同十进制数的十进制数，而不会损失精度。
    ```cpp
    Minimum value is 6
    ```

3.  **`DBL_DIG`** 或 **`LDBL_DIG`**：可以四舍五入成浮点数并返回而小数位数不变的小数位数。
    ```cpp
    Minimum value is 10
    ```

4.  **`DECIMAL_DIG`**：表示浮点值所需的十进制数字。
    ```cpp
    No Minimum value
    ```

5.  **`FLT_MANT_DIG`** 或 **`DBL_MANT_DIG`** 或 **`LDBL_MANT_DIG`**：尾数的精度，即符合有效数字的位数。
    ```cpp
    No Minimum value
    ```

6.  **`FLT_MIN_EXP`** 或 **`DBL_MIN_EXP`** 或 **`LDBL_MIN_EXP`**：生成归一化浮点数的指数的最小负整数值。
    ```cpp
    No Minimum value
    ```

7.  **`FLT_MIN_10_EXP`** 或 **`DBL_MIN_10_EXP`** 或 **`LDBL_MIN_10_EXP`**：将生成规范化浮点数的基数为 10 的表达式的指数的最小负整数值。
    ```cpp
    Maximum value is -37
    ```

8.  **`FLT_MAX_EXP`** 或 **`DBL_MAX_EXP`** 或 **`LDBL_MAX_EXP`**：生成归一化浮点数的指数的最大整数值。
    ```cpp
    No Minimum value
    ```

9.  **`FLT_MAX_10_EXP`** 或 **`DBL_MAX_10_EXP`** 或 **`LDBL_MAX_10_EXP`**：将生成规范化浮点数的基数为 10 的表达式的指数的最大整数值。
    ```cpp
    Minimum value is 37
    ```

10. **`FLT_MAX`** 或 **`DBL_MAX`** 或 **`LDBL_MAX`**：最大有限可表示浮点数。
    ```cpp
    Minimum value is 1037
    ```

11. **`FLT_EPSILON`**：1 和可表示的大于 1 的最小值之间的差值。
    ```cpp
    Maximum value is 10-5
    ```

12. **`DBL_EPSILON`** 或 **`LDBL_EPSILON`**：1 和可表示的大于 1 的最小值之间的差值。
    ```cpp
    Maximum value is 10-9
    ```

13. **`FLT_MIN`** 或 **`DBL_MIN`** 或 **`LDBL_MIN`**：最小可表示正浮点数。
    ```cpp
    Maximum value is 10-37
    ```

14. **`FLT_ROUNDS`**：舍入浮点数。不同的可能值是：
    ```cpp
    -1 : indeterminate
     0 : towards zero
     1 : towards one
     2 : towards positive infinity
     3 : towards negative infinity
    ```

15. **`FLT_EVAL_METHOD`**：舍入浮点数。不同的可能值为：
    ```cpp
    -1 : undetermined
     0 : evaluate just to the range 
         and precision of the type
     1 : evaluate float and double as double,
         and long double as long double.
     2 : evaluate all as long double and Other 
         negative values indicate an 
         implementation defined behavior.
    ```

下面是演示 `cfloat` 库中宏常量工作的程序。

```cpp
// C++ program to demonstrate working
// of macros constants in cfloat library

#include <cfloat>
#include <iostream>
using namespace std;

int main()
{
    cout << "FLT_RADIX : "
         << FLT_RADIX << endl;
    cout << "FLT_DIG : "
         << FLT_DIG << endl;
    cout << "DECIMAL_DIG : "
         << DECIMAL_DIG << endl;
    cout << "FLT_MIN_10_EXP : "
         << FLT_MIN_10_EXP << endl;
    cout << "FLT_MAX_EXP : "
         << FLT_MAX_EXP << endl;
    cout << "FLT_MAX_10_EXP : "
         << FLT_MAX_10_EXP << endl;
    cout << "FLT_MAX : "
         << FLT_MAX << endl;
    cout << "FLT_MIN : "
         << FLT_MIN << endl;
    return 0;
}
```

**输出（机器相关）：**

```cpp
FLT_RADIX : 2
FLT_DIG : 6
DECIMAL_DIG : 21
FLT_MIN_10_EXP : -37
FLT_MAX_EXP : 128
FLT_MAX_10_EXP : 38
FLT_MAX : 3.40282e+38
FLT_MIN : 1.17549e-38
```

**参考：**
> [http://www.cplusplus.com/reference/cfloat/](http://www.cplusplus.com/reference/cfloat/)