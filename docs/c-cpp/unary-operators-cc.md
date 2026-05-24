# C/c++ 中的一元运算符

> 原文:[https://www.geeksforgeeks.org/unary-operators-cc/](https://www.geeksforgeeks.org/unary-operators-cc/)

**一元运算符:**是作用于单个操作数以产生新值的运算符。

**一元运算符的类型:**

1.  一元减号(-)
2.  增量(++)
3.  减量(-)
4.  不是(！)
5.  Addressof 运算符(&)
6.  sizeof()

1.  **unary minus**
    The minus operator changes the sign of its argument. A positive number becomes negative, and a negative number becomes positive.

    ```cpp
     int a = 10;
     int b = -a;  // b = -10

    ```

    一元减号不同于减法运算符，因为减法需要两个操作数。

2.  **增量**
    用于将变量的值增加 1。增量可以通过两种方式完成:

1.  **前缀增量**
    在此方法中，运算符位于操作数之前(例如，++ a)。在使用之前，操作数的值将被改变*。

    ```cpp
      int a = 1;
      int b = ++ a;  // b = 2

    ```* 
2.  **后缀增量**
    在这个方法中，运算符跟在操作数后面(例如 a++)。使用后，值操作数将被更改*。

    ```cpp
     int a = 1;
     int b = a++ ;   // b = 1
     int c = a;     // c = 2

    ```* 

6.  **decrement**
    It is used to decrement the value of the variable by 1\. The decrement can be done in two ways:
    1.  **前缀递减**
        在此方法中，运算符位于操作数之前(例如–- a)。在使用之前，操作数的值将被改变*。

        ```cpp
          int a = 1;
          int b = --a;  // b = 0

        ```* 
    2.  **后缀减量**
        在这个方法中，运算符跟在操作数后面(例如 a-)。使用后，操作数的值将被更改*。

        ```cpp
         int a = 1;
         int b = a--;   // b = 1
         int c = a;     // c = 0

        ```* 

    **组合前缀和后缀操作的 C++ 程序:**

    ```cpp
    // C++ program to demonstrate working of unary increment
    // and decrement operators
    #include <iostream>
    using namespace std;

    int main()
    {
        // Post increment
        int a = 1;
        cout << "a value: " << a << endl;
        int b = a++ ;
        cout << "b value after a++ : " << b << endl;
        cout << "a value after a++ : " << a << endl;

        // Pre increment
        a = 1;
        cout << "a value:" << a << endl;
        b = ++ a;
        cout << "b value after ++ a : " << b << endl;
        cout << "a value after ++ a : "<< a << endl;

        // Post decrement
        a = 5;
        cout << "a value before decrement: " << a << endl;
        b = a--;
        cout << "b value after a-- : " << b << endl;
        cout << "a value after a-- : " << a << endl;

        // Pre decrement
        a = 5;
        cout << "a value: "<< a<<endl;
        b = --a;
        cout << "b value after --a : " << b << endl;
        cout << "a value after --a : " << a << endl;

        return 0;
    }
    ```

    **输出:**

    ```cpp
    a value: 1
    b value after a++ : 1
    a value after a++ : 2
    a value:1
    b value after ++ a : 2
    a value after ++ a : 2
    a value before decrement: 5
    b value after a-- : 5
    a value after a-- : 4
    a value: 5
    b value after --a : 4
    a value after --a : 4

    ```

    上面的程序展示了后缀和前缀是如何工作的。

7.  **不是(！):**用于反转其操作数的逻辑状态。如果条件为真，则逻辑非运算符将使其为假。

    ```cpp
       If x is true, then !x is false
       If x is false, then !x is true

    ```

8.  **Addressof 运算符(& ):** 它给出了一个变量的地址。它用于返回变量的内存地址。由 address-of 运算符返回的这些地址被称为指针，因为它们“指向”内存中的变量。

    ```cpp
    & gives an address on variable n
    int a;
    int *ptr;
    ptr = &a; // address of a is copied to the location ptr. 

    ```

9.  **sizeof():** This operator returns the size of its operand, in bytes. The *sizeof* operator always precedes its operand.The operand is an expression, or it may be a cast.

    ```cpp
    #include <iostream>
    using namespace std;

    int main()
    {
       float n = 0;
       cout << "size of n: " << sizeof(n);
       return 1;
    }
    ```

    **输出:**

    ```cpp
    size of n: 4

    ```

    本文由 **I. HARISH KUMAR** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。