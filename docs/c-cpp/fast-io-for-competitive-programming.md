# 用于竞争性编程的快速输入/输出

> 原文:[https://www . geesforgeks . org/fast-io-for-competitive-programming/](https://www.geeksforgeeks.org/fast-io-for-competitive-programming/)

在竞争性编程中，尽可能快地读取输入非常重要，这样我们可以节省宝贵的时间。

你一定看到过各种问题语句说:“ ***”警告:**大 I/O 数据，对某些语言要小心(虽然如果算法设计得好，大部分应该还可以)“*。解决这些问题的关键是使用更快的输入/输出技术。

为了快速输入和输出，通常建议使用 scanf/printf 而不是 cin/cout。但是，通过在 main()函数中包含以下两行，您仍然可以使用 cin/cout 并获得与 scanf/printf 相同的速度:

```cpp
    ios_base::sync_with_stdio(false);
```

如果在程序执行其第一个输入或输出操作之前调用它，它将打开或关闭所有 C++ 标准流与其对应的标准 C 流的同步。添加 IOs _ base::sync _ with _ stdio(false)；(默认情况下为真)在任何 I/O 操作之前，避免这种同步。它是 std::ios_base 函数的静态成员。

```cpp
    cin.tie(NULL);
```

tie()是一种方法，它简单地保证在 std::cin 接受输入之前刷新 std::cout。这对于交互式控制台程序很有用，它要求控制台不断更新，但也会因为大的输入/输出而减慢程序的速度。

此外，您可以通过单个包含来包含标准模板库(STL):

```cpp
    #include <bits/stdc++.h>
```

因此，您的竞争性编程模板可能如下所示:

```cpp
#include <bits/stdc++.h>
using namespace std;

int main()
{
    ios_base::sync_with_stdio(false);
    cin.tie(NULL);
    return 0;
}
```

建议使用 cout << “\n”; instead of cout << endl;. endl is slower because it forces a flushing stream, which is usually unnecessary (See [这个](https://www.geeksforgeeks.org/endl-vs-n/)进行详细说明)。(如果你在写交互式进度条，你需要刷新，但写一百万行数据时就不需要了。)写“\n”而不是 endl。

我们可以在问题[上测试我们的输入和输出方法。](http://www.spoj.com/problems/INTEST/)在进一步阅读之前，我建议你先解决问题。
c++ 4 . 9 . 2 中的解决方案

**正常输入输出:**下面的代码使用 cin 和 cout。该解决方案以 2.17 秒的运行时间被接受。

## C++

```cpp
// A normal IO example code
#include <bits/stdc++.h>
using namespace std;
int main()
{
    int n, k, t;
    int cnt = 0;
    cin >> n >> k;
    for (int i=0; i<n; i++)
    {
        cin >> t;
        if (t % k == 0)
            cnt++ ;
    }
    cout << cnt << "\n";
    return 0;
}
```

**快速 I/O** 但是，我们可以做得更好，通过增加两行来大大减少运行时间。下面的程序以 0.41 秒的运行时间被接受。

## C++

```cpp
// A fast IO program
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // added the two lines below
    ios_base::sync_with_stdio(false);
    cin.tie(NULL);  

    int n, k, t;
    int cnt = 0;
    cin >> n >> k;
    for (int i=0; i<n; i++)
    {
        cin >> t;
        if (t % k == 0)
            cnt++ ;
    }
    cout << cnt << "\n";
    return 0;
}
```

现在，谈论像 ACM ICPC、谷歌代码堵塞、TopCoder Open 这样的竞赛，这里有一个以最快的方式读取整数的独家代码。

## C++

```cpp
void fastscan(int &number)
{
    //variable to indicate sign of input number
    bool negative = false;
    register int c;

    number = 0;

    // extract current character from buffer
    c = getchar();
    if (c=='-')
    {
        // number is negative
        negative = true;

        // extract the next character from the buffer
        c = getchar();
    }

    // Keep on extracting characters if they are integers
    // i.e ASCII Value lies from '0'(48) to '9' (57)
    for (; (c>47 && c<58); c=getchar())
        number = number *10 + c - 48;

    // if scanned input has a negative sign, negate the
    // value of the input number
    if (negative)
        number *= -1;
}

// Function Call
int main()
{
    int number;
    fastscan(number);
    cout << number << "\n";
    return 0;
}
```

[getchar _ unlock()在 C 中进行更快的输入进行竞争性编程](https://www.geeksforgeeks.org/getchar_unlocked-faster-input-cc-competitive-programming/)

本文由**维奈·加尔格供稿。**如果你喜欢 GeeksforGeeks 并想投稿，你也可以写一篇文章，把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如发现任何不正确的地方，请写评论，或者您想分享更多关于上述话题的信息