# 缓冲区刷新在 C++ 中是什么意思？

> 原文:[https://www.geeksforgeeks.org/buffer-flush-means-c/](https://www.geeksforgeeks.org/buffer-flush-means-c/)

缓冲区刷新是将计算机数据从临时存储区传输到计算机的永久内存。例如，如果我们对一个文件进行任何更改，我们在一个计算机屏幕上看到的更改会暂时存储在一个缓冲区中。
通常，当我们打开任何 word 文档时，都会有一个临时文件，当我们关闭主文件时，它会自动销毁。因此，当我们保存工作时，自上次保存以来对文档所做的更改会从缓冲区刷新到硬盘上的永久存储中。

在 C++ 中，我们可以显式刷新来强制写入缓冲区。一般来说， **std::endl** 函数通过插入一个新行字符并刷新流来实现同样的功能。 **stdout/cout 是行缓冲的**也就是说，直到你写了一个换行符或显式刷新缓冲区，输出才被发送到操作系统。例如，

## C++

```cpp
// Causes only one write to underlying file
// instead of 5, which is much better for
// performance.
std::cout << a << " + " << b << " = " << std::endl;
```

但是也有一些缺点，

## C++

```cpp
// Below is C++ program
#include <iostream>
#include <thread>
#include <chrono>

using namespace std;

int main()
{
  for (int i = 1; i <= 5; ++ i)
  {
      cout << i << " ";
      this_thread::sleep_for(chrono::seconds(1));
  }
  cout << endl;
  return 0;
}
```

```cpp
The above program will output 1 2 3 4 5 at once.
```

因此在这种情况下，使用额外的**“刷新”**功能来确保输出按照我们的要求显示。例如，

## C++

```cpp
// C++ program to demonstrate the
// use of flush function
#include <iostream>
#include <thread>
#include <chrono>
using namespace std;
int main()
{
   for (int i = 1; i <= 5; ++ i)
   {
      cout << i << " " << flush;
      this_thread::sleep_for(chrono::seconds(1));
   }
   return 0;
}
```

```cpp
The above program will print the 
numbers(1 2 3 4 5) one by one rather than once. 
The reason is flush function flushed the output 
to the file/terminal instantly.
```

**注:**

1.  你不能在一个在线编译器上运行这个程序来看出区别，因为它们只在程序终止时给出输出。因此，您需要在一个离线编译器中运行所有上述程序，如 GCC 或 clang。
2.  阅读 cin 刷新 cout，所以我们不需要显式刷新来做到这一点。

**参考文献:**

*   [http://searchstorage.techtarget.com/definition/buffer-flush](http://searchstorage.techtarget.com/definition/buffer-flush)
*   [https://stackoverflow . com/questions/15042849/刷新缓冲区是什么意思](https://stackoverflow.com/questions/15042849/what-does-flushing-the-buffer-mean)

**相关文章:**
[在 C](https://www.geeksforgeeks.org/use-fflushstdin-c/) 中使用 fflush(stdin)

本文由 [Shubham Bansal](https://www.quora.com/profile/Shubham-Bansal-209) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。