# C/c++ 写 void main()或者 main()可以吗？

> 原文:[https://www . geesforgeks . org/is-it-fine-to-write-void-main-or-main-in-c-CPP/](https://www.geeksforgeeks.org/is-it-fine-to-write-void-main-or-main-in-c-cpp/)

在 C 语言中， **void main()** 没有定义的(合法的)用法，它有时会抛出垃圾结果或错误。但是， **main()** 用于表示不带参数并返回整数数据类型的主函数。

定义不是也从来不是 C++，甚至不是 C，参见 [ISO C++ 标准 3.6.1[2]](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4296.pdf) 或 [ISO C 标准 5.1.2.2.1。](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4296.pdf)了解更多。

```cpp
void main(){
// Body
}
```

一致性实现接受下面给出的格式:

```cpp
int main(){ 
// Body
}
```

和

```cpp
int main(int argc, char* argv[]){
// Body
}
```

一致性实现可以提供更多版本的 main()，但它们都必须具有返回类型 int。main()返回的 int 是程序向调用它的“系统”返回值的一种方式。在不提供这种功能的系统上，返回值会被忽略，但这不会使“void main()”成为合法的 C++ 或合法的 C.

> **注意:**即使您的编译器接受 **void main()** 也要避免它，否则会有被 C 和 C++ 程序员认为无知的风险。在 C++ 中， **main()** 不需要包含显式的返回语句。在这种情况下，返回值为 0，意味着成功执行。

**示例:**

## CPP

```cpp
// CPP Program to demonstrate main() with
// return type
#include <iostream>

// Driver Code
int main()
{
    std::cout
        << "This program returns the integer value 0\n";
}
```

**输出**

```cpp
This program returns the integer value 0
```

> **注意:**ISO c++ 和 C99 都不允许将类型从声明中去掉。也就是说，与 C89 和 ARM C++ 相比， **int** 在声明中缺少类型的地方不被假定。
> 
> T21】

因此，

## C++

```cpp
#include <iostream>
using namespace std;

main()
{
    // Body
}
```

上面的代码没有错误。如果您编写了完整的无错误 main()函数，但在结尾没有返回语句，那么编译器会在程序的结尾自动添加一个具有适当数据类型的返回语句。

综上所述，使用 **void main()** 或者简单的说 **main()** 从来都不是一个好主意，因为它没有确认标准。尽管它可能被一些编译器所允许。

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论