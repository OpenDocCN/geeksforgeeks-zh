# c++ 中的复数|集合 2

> 原文:[https://www.geeksforgeeks.org/complex-numbers-c-set-2/](https://www.geeksforgeeks.org/complex-numbers-c-set-2/)

我们在 C++ 中引入并讨论了[复数的概念|集合 1](https://www.geeksforgeeks.org/complex-numbers-c-set-1/)
剩下的函数用例子讨论如下:

*   **log()**–用于返回复数的 log。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate the use of log()
#include <iostream>    

// for std::complex, std::log
#include <complex>
using namespace std;

// driver program
int main ()
{   
  // initializing the complex: (-1.0+0.0i)
  complex<double> mycomplex (-1.0, 0.0);

  // use of log()
  cout << "The log of " << mycomplex << " is "
       << log(mycomplex) <<endl;

  return 0;
}
```

*   输出:

```cpp
The log of (-1,0) is (0,3.14159)
```

*   **cos()**–它计算复数值 z 的复余弦。余弦的数学定义是

```cpp
cos z = (e^(iz) + e^(-iz))/2
```

*   **sin()**–它计算复数值 z 的复正弦。余弦的数学定义为

```cpp
 sin z = (e^(iz) - e^(-iz))/2i
```

*   **tan()**–它计算复数值 z 的复切线。切线的数学定义为

```cpp
tan z = i(e^(-iz) - e^(iz)) / (e^(-iz) + e^iz)
```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// example to illustrate the use of sin(), cos() and tan()
#include <iostream>    

// CPP program to illustrate
// std::complex, std::cos, std::sin, std::tan
#include <complex>
using namespace std;

// driver program
int main ()
{   
  // initializing the complex: (-1.0+0.0i)
  complex<double> mycomplex (0.0, 1.0);

  // use of cos()
  cout << "The cos of " << mycomplex << " is "
       << cos(mycomplex) <<endl;

  // use of sin()
  cout << "The sin of " << mycomplex << " is "
       << sin(mycomplex) <<endl;

  // use of tan()
  cout << "The tan of " << mycomplex << " is "
       << tan(mycomplex) <<endl;

  return 0;
}
```

*   输出:

```cpp
The cos of (0,1) is (1.54308,-0)
The sin of (0,1) is (0,1.1752)
The tan of (0,1) is (0,0.761594)
```

*   **cosh()**–它找到给定复数的双曲余弦。双曲余弦的数学函数是:

```cpp
cosh(z)=(e^z+e^(-z))/2
```

*   **sinh()**–它找到给定复数的双曲正弦。双曲正弦的数学函数是:

```cpp
  sinh(z)=(e^z-e^(-z))/2.
```

*   **tanh()**–它找到给定复数的双曲正切。双曲线 tan 的数学函数是:

```cpp
tanh(z)=(e^(2z)-1)/(e^(2z)+1)
```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate the
// use of cosh(),sinh(),tanh()
#include <iostream>
#include <cmath>

// For std::complex
#include <complex>
using namespace std;

// Driver program
int main()
{      
    // behaves like real cosh, sinh, tanh along the real line;
    // z = a + 0i
    complex<double> z(1, 0);
    cout << "cosh" << z << " = " << cosh(z)
              << " (cosh(1) = " << cosh(1) << ")"<<endl;
    cout << "sinh" << z << " = " << sinh(z)
              << " (sinh(1) = " << sinh(1) << ")"<<endl;
    cout << "tanh" << z << " = " << tanh(z)
              << " (tanh(1) = " << tanh(1) << ")"<<endl;

    // behaves like real cosine,sine,tangent along the imaginary line; z2=0+1i
    complex<double> z2(0, 1);
    cout << "cosh" << z2 << " = " << cosh(z2)
              << " ( cos(1) = " << cos(1) << ")"<<endl;
    cout << "sinh" << z2 << " = " << sinh(z2)
              << " ( sin(1) = " << sin(1) << ")"<<endl;
    cout << "tanh" << z2 << " = " << tanh(z2)
              << " ( tan(1) = " << tan(1) << ")"<<endl;
}
```

*   输出:

```cpp
cosh(1.000000,0.000000) = (1.543081,0.000000) (cosh(1) = 1.543081)
sinh(1.000000,0.000000) = (1.175201,0.000000) (sinh(1) = 1.175201)
tanh(1.000000,0.000000) = (0.761594,0.000000) (tanh(1) = 0.761594)
cosh(0.000000,1.000000) = (0.540302,0.000000) ( cos(1) = 0.540302)
sinh(0.000000,1.000000) = (0.000000,0.841471) ( sin(1) = 0.841471)
tanh(0.000000,1.000000) = (0.000000,1.557408) ( tan(1) = 1.557408)
```

本文由**香巴拉维·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](http://www.write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。