# 高级 C++ 带增强库

> 原文:[https://www.geeksforgeeks.org/advanced-c-boost-library/](https://www.geeksforgeeks.org/advanced-c-boost-library/)

[增强库](https://en.wikipedia.org/wiki/Boost_(C%2B%2B_libraries)#License)旨在广泛使用，并可用于广泛的应用领域。例如，它们有助于在 C++ 中处理超出长整型、长双精度数据类型(2 <sup>64</sup> )范围的大数。

**<u>安装</u>**

*   增压的安装请参考[本篇](http://www.boost.org/doc/libs/1_62_0/more/getting_started/unix-variants.html#errors-and-warnings)。我们可以下载压缩文件。之后，我们只需要提取 gcc 的指定文件夹中的整体，或者我们可以通过命令提示符轻松做到这一点。
*   如果你有一个代码块编译器，那么这里的是一篇非常好的文章，有完整的解释。

**<u>示例应用程序</u>**

我们可以在**竞技编程**中高效使用这个库，但是在此之前我们必须确保你的在线裁判必须支持 boost。这里有一些很酷的技巧，你可以使用

1.  **Big Integer data type** We can use either **int128_t, int256_t, int512_t or int1024_t** data type according to your requirement. By using these one, we can achieve precision up to 1024 easily.
    Below C++ implementation code of finding the product of large numbers.

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

    **输出:**

    ```cpp
    Product of 98745636214564698 * 7459874565236544789 =
    736630060025131838840151335215258722

    ```

2.  **Arbitrary precision data type:** We can use any precision with the help of cpp_int data type if we are not sure about how much precision is needed in future. It automatically converts the desired precision at the Run-time.
    Below implementation of C++ code for finding the factorial of 30.

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

    **输出:**

    ```cpp
    Factorial of 30 = 265252859812191058636308480000000
    ```

3.  **multi precision float:**借助 Boost Multiprecision float，我们可以分别用 cpp_float_50 和 cpp_dec_float_100 实现精度高达 50 和 100 的小数。
    下面是 C++ 代码，使用 float、decimal 和 cpp_float_50 类型计算不同精度的圆的面积。

    ```cpp
    #include<iostream>
    #include <boost/multiprecision/cpp_dec_float.hpp>
    #include <boost/math/constants/constants.hpp>

    using boost::multiprecision::cpp_dec_float_50;

    using namespace std;

    template<typename T>
    inline T area_of_a_circle(T r)
    {  
       // pi represent predefined constant having value
       // 3.1415926535897932384...
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

        // numeric_limits::digits10 represent the number
        // of decimal digits that can be held of particular
        // data type without any loss.

        // Area by using float data type
        cout << "Float: "
             << setprecision(numeric_limits<float>::digits10)
             << area_f << endl;

        // Area by using double data type
        cout << "Double: "
             <<setprecision(numeric_limits<double>::digits10)
             << area_d << endl;

        // Area by using Boost Multiprecision 
        cout << "Boost Multiprecision: "
             << setprecision(numeric_limits<cpp_dec_float_50>::digits10)
             << area_mp << endl;
        return 0;
    }
    ```

    **输出:**

    ```cpp
    Float: 4.75292
    Double: 4.752915525616
    Boost Multiprecision: 4.7529155256159980531876290929438093413108253981451

    ```

**参考文献:**[http://www . boost . org/doc/libs/1 _ 61 _ 0/libs/multi precision/doc/html/index . html](http://www.boost.org/doc/libs/1_61_0/libs/multiprecision/doc/html/index.html)

本文由 [Shubham Bansal](https://www.facebook.com/banalshubham) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。