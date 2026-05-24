# c++ 中的 feupdateenv()函数

> 原文:[https://www.geeksforgeeks.org/feupdateenv-function-in-c/](https://www.geeksforgeeks.org/feupdateenv-function-in-c/)

C++ 中的**feupdatenv()**函数首先保存当前引发的浮点异常。它从给定的 **fenv_t 对象**恢复浮点环境，然后引发之前保存的异常。

**语法:**

```cpp
int feupdateenv( fenv_t* envp )
```

**参数:**它接受单个强制参数 *envp* ，该参数指定了指向 fenv_t 对象的指针，该指针是由对 *feholdexcept* 或 *fegetenv* 的早期调用设置的，或者等于 *FE_DFL_ENV* 。该函数还接受 fenv_t 类型的指针作为其参数，该指针保存一个先前使用 feholdexcept 或 fegetenv 设置的浮点环境，并与当前环境一起恢复该浮点环境。

**返回值:**该函数返回两种如下所述的值:

*   它在成功时归零
*   它在失败时返回非零值

下面的程序说明了上述功能。

**程序 1:**

```cpp
// C++ program to illustrate the 
// feupdateenv() function 
#include <bits/stdc++.h> 
#pragma STDC FENV_ACCESS on 

// Function to use the function 
double answer(double y) 
{ 

    // struct defined 
    fenv_t trial; 

    // use the function feholdexcept 
    feholdexcept(&trial); 

    // find log valye 
    y = log(y); 

    // clears exception 
    feclearexcept(FE_OVERFLOW | FE_DIVBYZERO); 

    // call the function for success or not 
    feupdateenv(&trial); 
    return y; 
} 

int main() 
{ 
    // It is a combination of all of 
    // the possible floating-point exception 
    feclearexcept(FE_ALL_EXCEPT); 

    // it returns the log value 
    // if it is to be found 
    printf("log(0.0): %f\n", answer(0.0)); 

    // the function does not throws any exception 
    if (!fetestexcept(FE_ALL_EXCEPT)) { 
        printf("no exceptions raised"); 
    } 
    return 0; 
} 
```

**输出:**

```cpp
log(0.0): -inf
no exceptions raised
```

**程序 2:**

```cpp
// C++ program to illustrate the 
// feupdateenv() function 
#include <bits/stdc++.h> 
#pragma STDC FENV_ACCESS on 

// Function to use the function 
double answer(double y) 
{ 

    // struct defined 
    fenv_t trial; 

    // use the function feholdexcept 
    feholdexcept(&trial); 

    // find log valye 
    y = log(y); 

    // clears exception 
    feclearexcept(FE_OVERFLOW | FE_DIVBYZERO); 

    // call the function for success or not 
    feupdateenv(&trial); 
    return y; 
} 

int main() 
{ 
    // It is a combination of all of 
    // the possible floating-point exception 
    feclearexcept(FE_ALL_EXCEPT); 

    // it returns the log value 
    // if it is to be found 
    printf("log(10.0): %f\n", answer(10.0)); 

    // the function does not throws any exception 
    if (!fetestexcept(FE_ALL_EXCEPT)) { 
        printf("no exceptions raised"); 
    } 
    else
        printf("exceptions raised"); 

    return 0; 
} 
```

**输出:**

```cpp
log(10.0): 2.302585
exceptions raised
```