# C/c++ 中“int main()”和“int main(void)”的区别？

> 原文:[https://www . geesforgeks . org/difference-int-main-int-main void/](https://www.geeksforgeeks.org/difference-int-main-int-mainvoid/)

考虑 main()的以下两个定义。

```cpp
int main()
{
   /*  */
   return 0;
}
```

和

```cpp
int main(void)
{
   /*  */
   return 0;
}
```

有什么区别？

在 C++ 中，没有区别，两者是一样的。

这两个定义在 C 语言中也有效，但是第二个带有 void 的定义被认为在技术上更好，因为它明确规定 main 只能在没有任何参数的情况下调用。
在 C 语言中，如果一个函数签名没有指定任何参数，则意味着该函数可以用任意数量的参数调用，也可以不用任何参数调用。例如，尝试编译并运行以下两个 C 程序(记住将文件另存为。c)。请注意 fun()的两个签名之间的区别。

```cpp
// Program 1 (Compiles and runs fine in C, but not in C++)
void fun() {  } 
int main(void)
{
    fun(10, "GfG", "GQ");
    return 0;
}
```

以上程序编译运行良好(见[本](http://ideone.com/AQoVZW)，以下程序编译失败(见[本](http://ideone.com/IXojiK)

```cpp
// Program 2 (Fails in compilation in both C and C++)
void fun(void) {  }
int main(void)
{
    fun(10, "GfG", "GQ");
    return 0;
}
```

与 C 不同，在 C++ 中，上述两种程序在编译时都会失败。在 C++ 中，fun()和 fun(void)都是一样的。

所以区别在于，在 C 中， *int main()* 可以用任意数量的参数调用，但是 *int main(void)* 只能在没有任何参数的情况下调用。虽然大多数情况下没有什么区别，但是在 c 语言中使用“int main(void)”是一个推荐的做法。

**练习:**
预测以下 **C** 程序的输出。

**问题 1**

```cpp
#include <stdio.h>
int main()
{
    static int i = 5;
    if (--i){
        printf("%d ", i);
        main(10);
    }
}
```

**问题 2**

```cpp
#include <stdio.h>
int main(void)
{
    static int i = 5;
    if (--i){
        printf("%d ", i);
        main(10);
    }
}
```

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论