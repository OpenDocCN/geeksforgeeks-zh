# 高级 C++ 增强库

> 原文：[https://www.geeksforgeeks.org/advanced-c-boost-library/](https://www.geeksforgeeks.org/advanced-c-boost-library/)

[增强库](https://en.wikipedia.org/wiki/Boost_(C%2B%2B_libraries)#License)旨在广泛使用，并可用于广泛的应用领域。例如，它们有助于在 C++ 中处理超出长整型、长双精度数据类型（2<sup>64</sup>）范围的大数。

## 安装

*   增强库的安装请参考[本篇](http://www.boost.org/doc/libs/1_62_0/more/getting_started/unix-variants.html#errors-and-warnings)。我们可以下载压缩文件。之后，我们只需要提取 gcc 的指定文件夹中的整体，或者我们可以通过命令提示符轻松做到这一点。
*   如果你有一个代码块编译器，那么这里的是一篇非常好的文章，有完整的解释。

## 示例应用程序

我们可以在**竞技编程**中高效使用这个库，但是在此之前我们必须确保你的在线裁判必须支持 boost。这里有一些很酷的技巧，你可以使用。

1.  **大整数数据类型**：我们可以根据需求使用 `int128_t`、`int256_t`、`int512_t` 或 `int1024_t` 数据类型。通过使用这些，我们可以轻松实现高达 1024 位的精度。
    下面是查找大数乘积的 C++ 实现代码。

    ```cpp
    #include <boost/multiprecision/cpp_int.hpp>
    using namespace boost::multiprecision;
    using namespace std;

    int128_t boost_product(long long A, long long B)
    {
        int128_t ans = (int128_t) A * B;
        return ans;
    }

    int main()
    {
        long long first = 98745636214564698;
        long long second=7459874565236544789;
        cout << "Product of "<< first << " * "
             << second << " = \n"
             << boost_product(first,second) ;
        return 0;
    }
    ```

    **输出：**

    ```cpp
    Product of 98745636214564698 * 7459874565236544789 =
    ```

2.  **任意精度数据类型**：如果我们不确定将来需要多少精度，可以在 `cpp_int` 数据类型的帮助下使用任意精度。它会在运行时自动转换为所需的精度。
    下面是计算 30 的阶乘的 C++ 代码实现。

    ```cpp
    #include <boost/multiprecision/cpp_int.hpp>
    using namespace boost::multiprecision;
    using namespace std;

    cpp_int boost_factorial(int num)
    {
        cpp_int fact = 1;
        for (int i=num; i>1; --i)    
            fact *= i;
        return fact;
    }

    int main()
    {   
        int num=30;
        cout << "Factorial of " << num << " = " 
             << boost_factorial(num) ;
        return 0;
    }
    ```

    **输出：**

    ```cpp
    Factorial of 30 = 265252859812191058636308480000000
    ```

3.  **多精度浮点数**：借助 Boost Multiprecision float，我们可以分别用 `cpp_float_50` 和 `cpp_dec_float_100` 实现精度高达 50 和 100 的小数。
    下面是 C++ 代码，使用 `float`、`double` 和 `cpp_dec_float_50` 类型计算不同精度的圆的面积。

    ```cpp
    #include<iostream>
    #include <boost/multiprecision/cpp_dec_float.hpp>
    #include <boost/math/constants/constants.hpp>

    using boost::multiprecision::cpp_dec_float_50;
    using namespace std;

    template<typename T>
    inline T area_of_a_circle(T r)
    {   
       // pi 代表预定义的常量，其值为 3.1415926535897932384...
       using boost::math::constants::pi;
       return pi<T>() * r * r;
    }

    int main()
    {
        float radius_f = 123.0/ 100;
        float area_f = area_of_a_circle(radius_f);

        double radius_d = 123.0 / 100;
        double area_d = area_of_a_circle(radius_d);

        cpp_dec_float_50 r_mp = 123.0 / 100;
        cpp_dec_float_50 area_mp = area_of_a_circle(r_mp);

        // numeric_limits::digits10 表示特定数据类型在不丢失精度的情况下可以保存的十进制数字位数。

        // 使用 float 数据类型计算面积
        cout << "Float: "
             << setprecision(numeric_limits<float>::digits10)
             << area_f << endl;

        // 使用 double 数据类型计算面积
        cout << "Double: "
             <<setprecision(numeric_limits<double>::digits10)
             << area_d << endl;

        // 使用 Boost Multiprecision 计算面积
        cout << "Boost Multiprecision: "
             << setprecision(numeric_limits<cpp_dec_float_50>::digits10)
             << area_mp << endl;
        return 0;
    }
    ```

    **输出：**

    ```cpp
    Float: 4.75292
    Double: 4.752915525616
    Boost Multiprecision: 4.7529155256159980531876290929438093413108253981451
    ```

**参考文献：**[http://www.boost.org/doc/libs/1_61_0/libs/multiprecision/doc/html/index.html](http://www.boost.org/doc/libs/1_61_0/libs/multiprecision/doc/html/index.html)

本文由 [Shubham Bansal](https://www.facebook.com/banalshubham) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。