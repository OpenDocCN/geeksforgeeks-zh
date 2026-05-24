# 标准::快速 _ 退出和标准::中止的区别

> 原文:[https://www . geesforgeks . org/difference-stdquick _ exit-and-stdabort/](https://www.geeksforgeeks.org/difference-between-stdquick_exit-and-stdabort/)

**std::quick_exit()**

它会导致正常程序终止，而不会完全清理资源。
**语法:**

```cpp
 void quick_exit(int exit_code) no except; 
```

在执行线程的情况下，代码变得复杂，知道线程的执行是困难的。一个线程可能在等待一个进程结束，而另一个线程在等待前一个线程。在这种情况下，真正的程序通常会死锁和退出，这是不愉快的。管理员必须强制启动系统或关闭用户界面等才能解除锁定。为此，制定了**标准::快速退出()**。它终止程序，将我们从执行真实程序时摆脱死锁的困难中解救出来。它清除输入输出，但不刷新静态析构函数。另一个功能 **at_quick_exit()**

```cpp
 int at_quick_exit( void (*func)(void) ); 
```

将函数作为参数，在调用 quick_exit()函数时执行该参数。注册到这个的函数是按照相反的执行顺序调用的。

```cpp
#include <cstdlib>
void atEXIT()
{
  cout << "Quick exit function.";
}
int main ()
{
  at_quick_exit(atEXIT);
  cout << "Main Function";
  quick_exit(0);
  cout << "End of Main"; 
  return 0;
}
 Output: Main Function
          Quick exit function.    

```

**std::abort()**

导致程序异常终止，除非 SIGABRT 被传递给 std::signal 的信号处理程序捕获，并且该处理程序没有返回。
**语法:**

```cpp
 void abort() no except; 
```

POSIX 指定中止函数覆盖阻塞或忽略 SIGABRT 信号。

```cpp
#include <cstdlib>

int main ()
{
  FILE * fp;
  fp= fopen("myfile.txt", "r");
  if (fp== NULL)
  {
    fputs("Error opening file \n", stderr);
    abort();
  }
  fclose(fp);
  return 0;
}
 Output: The file named myfile.txt, if not found or fails opens due to any reason the error 
            message is printed and abort function terminates the program.

```

**相似之处:**STD::quick _ exit()和 std::abort()函数都在 cstdlib 头中定义。这两个函数都没有参数，也没有异常。它们都没有回报价值。它们用于终止程序，但它们仍然彼此不同。
**区别:**引入 **quick_exit()** 功能的原因是在清除 IO 的同时结束正在运行的程序，并且仍然获得程序的某些部分，即在 **at_quick_exit()** 中注册的要执行的功能，而 **std::abort()** 功能终止程序，而不执行程序的其他部分并且不清除 IO。