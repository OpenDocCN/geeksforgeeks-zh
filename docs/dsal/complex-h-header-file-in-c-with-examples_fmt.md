# C 中头文件 `<complex.h>` 带示例

> 原文: [https://www.geeksforgeeks.org/complex-h-header-file-in-c-with-examples/](https://www.geeksforgeeks.org/complex-h-header-file-in-c-with-examples/)

大部分 C 程序都是使用 `complex.h` 头文件来处理[复数](https://www.geeksforgeeks.org/complex-numbers-c-set-1/)运算和操作。这个头文件是在 **C99 标准**中添加的。

C++标准库有一个表头，实现复数作为模板类，`<[T](https://www.geeksforgeeks.org/complex-numbers-c-set-1/)>`，不同于 C 中的 `<complex.h>`。

## 宏与 `<complex.h>`

相关联 `<complex.h>` 的一些宏如下所示。左侧的值描述了 `complex.h` 中的宏，右侧描述了 C99 标准中添加了关键字(`_Imaginary`, `_Complex`)的宏的扩展。

| 宏名字 | 延伸至 |
| --- | --- |
| `complex` | `_Complex` |
| `imaginary` | `_Imaginary` |
| `_Complex_I` | `(const float _Complex)I` |
| `_Imaginary_I` | `(const float _Imaginary)I` |
| `I` | `_Imaginary_I` (`_Complex_I` 如果 `_Imaginary_I` 不存在) |

下面的程序有助于创建复数。

### 例 1

```c
// C program to show the working
// of complex.h library

#include <complex.h>
#include <stdio.h>

int main(void)
{
    double real = 1.3,
           imag = 4.9;
    double complex z
        = CMPLX(real, imag);
    printf(
        "z = %.1f% + .1fi\n",
        creal(z), cimag(z));
}
```

**Output:**

```
z = 1.3+4.9i
```

**说明:**

*   `CMPLX()` 函数以实部和虚部为参数创建复数对象。这个函数返回复数的对象。
*   `creal()` 函数返回复数的实部。
*   `cimag()` 函数返回复数的虚部。
*   如果我们的实部和虚部是 `float` 类型，我们使用 `CMPLXF()` 函数来生成复数，为了得到实部和虚部，我们使用 `crealf()`、`cimagf()` 函数。
*   如果我们的实部和虚部是 `long double` 类型，我们使用 `CMPLXL()` 函数来生成复数，为了得到实部和虚部，我们使用 `creall()`、`cimagl()` 函数。

### 例 2

我们也可以使用宏 `I` 创建复数对象。

```c
// C program to create a complex
// number using macro I

#include <complex.h>
#include <stdio.h>

int main(void)
{
    double complex
        z
        = 3.2 + 4.1 * I;

    // Creates complex number
    // with 3.2 and 4.1 as
    // real and imaginary parts
    printf(
        "z = %.1f% + .1fi\n",
        creal(z), cimag(z));
}
```

**Output:**

```
z = 3.2+4.1i
```

## 与 `<complex.h>` 关联的函数

`<complex.h>` 头文件还提供了一些内置函数来处理复数。这里的“arg”代表复数对象。

| 功能 | 描述 |
| --- | --- |
| `float cabsf(float complex arg)`<br>`double cabs(double complex arg)`<br>`long double cabsl(long double complex arg)` | 它返回复数参数的绝对值。 |
| `float complex cacosf(float complex arg)`<br>`double complex cacos(double complex arg)`<br>`long double complex cacosl(long double complex arg)` | 它返回复变元的复弧余弦值。 |
| `float complex cacoshf(float complex arg)`<br>`double complex cacosh(double complex arg)`<br>`long double complex cacoshl(long double complex arg)` | 它返回复变元的复弧双曲余弦值。 |
| `float cargf(float complex arg)`<br>`double carg(double complex arg)`<br>`long double cargl(long double complex arg)` | 它返回复变元的相位角(以弧度为单位)。 |
| `float complex casinf(float complex arg)`<br>`double complex casin(double complex arg)`<br>`long double complex casinl(long double complex arg)` | 它返回复变元的复反正弦值。 |
| `float complex casinhf(float complex arg)`<br>`double complex casinh(double complex arg)`<br>`long double complex casinhl(long double complex arg)` | 它返回复变元的复弧双曲正弦值。 |
| `float complex catanf(float complex arg)`<br>`double complex catan(double complex arg)`<br>`long double complex catanl(long double complex arg)` | 它返回复变元的复反正切值。 |
| `float complex catanhf(float complex arg)`<br>`double complex catanh(double complex arg)`<br>`long double complex catanhl(long double complex arg)` | 它返回复变元的复弧双曲正切值。 |
| `float complex ccosf(float complex arg)`<br>`double complex ccos(double complex arg)`<br>`long double complex ccosl(long double complex arg)` | 它返回复变元的复余弦值。 |
| `float complex cexpf(float complex arg)`<br>`double complex cexp(double complex arg)`<br>`long double complex cexpl(long double complex arg)` | 它返回复数值 `e^arg`，其中 `e` 是自然对数基数。 |
| `float crealf(float complex arg)`<br>`double creal(double complex arg)`<br>`long double creall(long double complex arg)` | 它返回复数参数的实部。 |
| `float cimagf(float complex arg)`<br>`double cimag(double complex arg)`<br>`long double cimagl(long double complex arg)` | 它返回复变元的虚部。 |
| `float complex clogf(float complex arg)`<br>`double complex clog(double complex arg)`<br>`long double complex clogl(long double complex arg)` | 它返回复变元的复自然对数。 |
| `float complex conjf(float complex arg)`<br>`double complex conj(double complex arg)`<br>`long double complex conjl(long double complex arg)` | 它返回复变元的共轭。 |
| `float complex cpowf(float complex a, long double complex b)`<br>`double complex cpow(double complex a, long double complex b)`<br>`long double complex cpowl(long double complex a, long double complex b)` | 它返回 `a^b` 的复数值。 |
| `float complex csqrtf(float complex arg)`<br>`double complex csqrt(double complex arg)`<br>`long double complex csqrtl(long double complex arg)` | 它返回参数的复数平方根。 |

### 例 3

求复数共轭的程序。

```c
#include <complex.h>
#include <stdio.h>

int main(void)
{
    double real = 1.3,
           imag = 4.9;
    double complex z
        = CMPLX(real, imag);
    double complex
        conj_f
        = conjf(z);
    printf("z = %.1f% + .1fi\n",
           creal(conj_f),
           cimag(conj_f));
}
```

**Output:**

```
z = 1.3-4.9i
```

### 例 4

求复数绝对值的程序。

```c
#include <complex.h>
#include <stdio.h>

int main(void)
{
    double real = 1.3,
           imag = 4.9;
    double complex z
        = CMPLX(real, imag);
    printf("Absolute value = %.1f",
           cabsf(z));
}
```

**Output:**

```
Absolute value = 5.1
```

### 例 5

求复数相角的程序。

```c
#include <complex.h>
#include <stdio.h>

int main(void)
{
    double real = 1.3,
           imag = 4.9;
    double complex z
        = CMPLX(real, imag);
    printf(
        "Phase Angle = %.1f radians\n",
        cargf(z));
}
```

**Output:**

```
Phase Angle = 1.3 radians
```