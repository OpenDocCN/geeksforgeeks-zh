# Cin-Cout vs Scanf-Printf

> 原文:[https://www.geeksforgeeks.org/cincout-vs-scanfprintf/](https://www.geeksforgeeks.org/cincout-vs-scanfprintf/)

当输入很大时，普通的有竞争力的程序员面临着共同的挑战，从 stdin 读取这样的输入可能会成为一个瓶颈。这样的问题伴随着“警告:大的输入输出数据”。

让我们创建一个虚拟输入文件，其中包含一行 16 个字节，后跟一个换行符，并且有 1000000 个这样的行，这样一个 17MB 的文件应该足够好了。

```cpp
// Creating a dummy file of size 17 MB to compare 
// performance of scanf() and cin()
$ yes 1111111111111111 | head -1000000 > tmp/dummy
```

让我们通过使用 scanf()和 cin 来比较从 stdin 读取文件(使用重定向将文件从磁盘获取到 stdin)所花费的时间。

```cpp
// Filename : cin_test.cc to test the 
// We redirect above created temp file 
// of 17 MB to stdin when this program 
// is run.
#include<iostream>
using namespace std;

int main()
{
    char buffer[256];
    while (cin >> buffer)
    {
    }
    return 0;
}
```

当虚拟文件被重定向到标准输入时，上述程序的输出。

```cpp
$ g++ cin_test.cc –o cin_test
$ time ./cin_test < /tmp/dummy
real	 0m2.162s
user	 0m1.696s
sys	 0m0.332s
```

```cpp
// Filename : scanf_test.c to see
// performance of scanf()
// We redirect above created temp file
// of 17 MB to stdin when this program
// is run.
#include<cstdlib>
#include<cstdio>
int main()
{
    char buffer[256];
    while (scanf("%s", buffer) != EOF)
    {
    }
    return 0;
}
```

当虚拟文件被重定向到标准输入时，上述程序的输出。

```cpp
$ g++ scanf_test.cc –o scanf_test
$ time ./scanf_test < /tmp/dummy
real	 0m0.426s
user	 0m0.248s
sys	 0m0.084s
```

嗯，上述结果与我们的观察一致。

为什么斯堪夫比 cin 快？
在高层次上两者都是 *read()* 系统调用的包装器，只是句法糖。唯一可见的区别是 *scanf()* 必须显式声明输入类型，而 *cin* 使用模板重载了重定向操作。这似乎不是性能提升 5 倍的充分理由。

原来 *iostream* 利用了 *stdio* 的缓冲系统。因此， *cin* 浪费时间与底层 C 库的 *stdio* 缓冲区同步，以便对 *scanf()* 和 *cin* 的调用可以交错。

好消息是 libstdc++ 提供了一个选项，可以使用关闭所有 *iostream* 标准流与其对应的标准 C 流的同步

```cpp
std::ios::sync_with_stdio(false);
```

而 *cin* 变得比*斯堪夫()*还要快，这本来是应该的。

竞技编程[快速输入输出](https://www.geeksforgeeks.org/fast-io-for-competitive-programming/)详解

```cpp
// Filename : cin_test_2.cc to see
// performance of cin() with stdio syc
// disabled using sync_with_stdio(false).
#include<iostream>
using namespace std;

int main()
{
    char buffer[256];
    ios_base::sync_with_stdio(false);

    while (cin >> buffer)
    {

    }
    return 0;
}
```

运行程序:

```cpp
$ g++ cin_test_2.cc –o cin_test_2
$ time./cin_test_2 </tmp/dummy
real    0m0.380s
user   0m0.240s
sys    0m0.028s 
```

*   和所有事情一样，这里有一个警告。在同步关闭的情况下，同时使用 *cin* 和 *scanf()* 将导致不确定的混乱。
*   关闭同步后，上述结果表明 *cin* 比*斯堪夫()*快 8-10%。这可能是因为 *scanf()* 在运行时解释格式参数，并使用可变数量的参数，而 *cin* 在编译时这样做。

现在想知道，它能多快完成？

```cpp
// Redirecting contents of dummy file to null
// device (a special device that discards the
// information written to it) using command line.
$time cat /tmp/dummy > /dev/null
real   0m0.185s
user   0m0.000s
sys    0m0.092s
```

哇哦！这太快了！！！

本文由 **Ayush Govil** 供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上述话题的信息，请写评论