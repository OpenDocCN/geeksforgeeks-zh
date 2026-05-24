# std::fixed，std::scientific，std::hexfloat，std::defaultfloat 在 C++ 中

> 原文:[https://www . geesforgeks . org/STD fixed-stdscientific-stdhexfloat-stddefaultfloat-c/](https://www.geeksforgeeks.org/stdfixed-stdscientific-stdhexfloat-stddefaultfloat-c/)

标准 C++ 库中的格式化是通过使用放置在输出流上的操纵器、特殊变量或对象来完成的。浮点操纵器有两种类型，即固定浮点和科学浮点。这些都在表头 **< iostream >** 中定义。

**Use of precision :** 

**exactly how many digits to display after the decimal point, even if they are trailing decimal zeros.**

1.  **STD::Fixed–固定浮点表示法**:用定点表示法写浮点值。该值以精确字段(精度)指定的小数位数表示，没有指数部分。
2.  **STD::Scientific–科学浮点表示法:**它以科学浮点表示法写入浮点值。该值始终仅用小数点前一位数字表示，后跟小数点和与精度字段(精度)一样多的小数位数。最后，这个符号总是包含一个由字母“ **e** ”组成的**指数部分**，后跟一个可选符号和三个指数数字。
3.  **STD::hex float–hex float 浮点表示法:**在数字精度初始化后，转换为**十六进制格式**后输出所需的数字(如前所述。案例)。
4.  **std::defaultfloat – defaultfloat floating-point notation :** It outputs the desired number same as **default** after the precision of no. is initialized ( as discussed in prev. cases ). It is mainly used to distinguish among other used formats for understandability of code.

    ```cpp
    // C++ code to demonstrate the 
    // working of 
    // std::fixed
    // std::scientific
    // std::hexfloat
    // std::defaultfloat

    #include <iostream> 
    using namespace std;
    int main()
    {
        // Initializing floating point variable
        double a = 4.223234232;
        double b = 2323.0;

        // Specifying precision
        cout.precision(4);

        // Printing normal values
        cout << "Normal values of floating point numbers\na = ";
        cout << a << "\nb = " << b << '\n' ;

        // Printing values using fixed ( till 4 )
        cout << "Values using fixed \n" << std::fixed;
        cout << a << "\n" << b << '\n' ; 

        // Printing values using scientific ( till 4 )
        // after 4, exponent is used
        cout << "Values using scientific are : " << std::scientific << endl;
        cout << a << '\n' << b << '\n' ; 

        // Printing values using hexfloat ( till 4 )
        cout << "Values using hexfloat are : " << std::hexfloat << endl;
        cout << a << '\n' << b << '\n' ; 

        // Printing values using defaultfloat ( till 4 )
        // same as normal
        cout << "Values using defaultfloat are : " << std::defaultfloat << endl;
        cout << a << '\n' << b << '\n' ; 

        return 0;
    }
    ```

    输出:

    ```cpp
    Normal values of floating point numbers
    a = 4.223
    b = 2323
    Values using fixed 
    4.2232
    2323.0000
    Values using scientific are : 
    4.2232e+00
    2.3230e+03
    Values using hexfloat are : 
    0x1.0e49783b72695p+2
    0x1.226p+11
    Values using defaultfloat are : 
    4.223
    2323

    ```

    本文由 **Astha Tyagi** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。