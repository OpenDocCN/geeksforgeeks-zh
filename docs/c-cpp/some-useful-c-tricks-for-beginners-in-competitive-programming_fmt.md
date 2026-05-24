# 竞技编程初学者的一些有用的 C++ 技巧

> 原文：[https://www.geeksforgeeks.org/some-useful-c-tricks-for-beginners-in-competitive-programming/](https://www.geeksforgeeks.org/some-useful-c-tricks-for-beginners-in-competitive-programming/)

下面是一些基本的 C++ 技巧，每个竞争编程初学者都应该遵循这些技巧来提高速度。然而，竞争性编程只能通过时间和大量实践来掌握。这些技巧将帮助你在比赛中节省一点时间，这有时很重要。

1.  使用 `auto` 关键字声明数据类型可以在编程竞赛中节省大量时间。
    当一个变量被定义为 `auto` 时，编译器可以自己确定数据类型。
    **例**:
    ```cpp
    auto a = 100; // a will become 'int'
    auto b = 1LL; // b will become 'long long'
    auto c = 1.0; // c will become 'double'
    auto d = "variable"; // d will become 'string'
    ```

2.  `watch` 宏是有史以来最有用的技巧之一。
    ```cpp
    #define watch(x) cout << (#x) << " is " << (x) << endl
    ```
    如果你正在调试你的代码，`watch(变量)`；将打印变量的名称及其值。（这是可能的，因为它是在预处理时间内构建的。）

3.  使用 `typedef` 可以节省您的大量时间，您可能会花费这些时间一次又一次地重新编写相同的代码片段。
    **例** :
    ```cpp
    typedef long long ll;
    typedef pair<int, int> pii;
    typedef vector<int> vi;
    typedef vector<ll> vll;
    typedef vector<pii> vpii;
    ```

4.  有一个内置函数来计算两个数字的最大公约数。它叫做 `__gcd()` ，存在于 `algorithm` 头文件中。要了解更多信息，请参考：[https://www.geeksforgeeks.org/stdgcd-c-inbuilt-function-finding-gcd/](https://www.geeksforgeeks.org/stdgcd-c-inbuilt-function-finding-gcd/)

5.  使用 `"\n"` 添加新的换行符比使用 `endl` 快得多。

6.  如果您在代码的开头使用 `ios::sync_with_stdio(false)` ，您将使 `cin` 和 `cout` 与 `printf` 和 `scanf` 一样快，但您将无法再使用 `printf` 和 `scanf` 。