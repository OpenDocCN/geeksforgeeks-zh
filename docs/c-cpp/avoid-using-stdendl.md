# 为什么要避免使用 std::endl

> 原文:[https://www.geeksforgeeks.org/avoid-using-stdendl/](https://www.geeksforgeeks.org/avoid-using-stdendl/)

使用 cout 时，通常使用 **std::endl** 打印换行符。对于输入/输出操作非常少的小程序，这种做法是可以接受的，但是如果大部分输入/输出操作增加，那么程序的效率就会受到影响。

**std::endl** 不仅向流中添加换行符，还会在每次使用缓冲区时刷新缓冲区。因此当我们写作时

```cpp
 cout << std::endl 
```

我们实际上正在做这样的事情

```cpp
 cout << '\n' << std::flush; 
```

刷新缓冲区是操作系统的任务。每次刷新缓冲区时，都必须向操作系统发出请求，而这些请求的成本相对较高。此外，我们并不需要每次向流中写入内容时都刷新缓冲区，因为当缓冲区变满时会自动刷新。在极少数情况下，我们确实需要执行冲洗，我们可以使用 **cout.flush()** 或者通过将 **std::flush** 插入到流中来明确指定操作。

直接向流中写入“\n”字符更有效，因为它不会像 std::endl 那样强制刷新。

**性能影响演示**
下面的 C++ 程序演示了 std::endl 的性能影响。我们使用 std::endl 将 100000 个字符串写入两个文件，然后再次使用' \n '。在每种情况下，我们都会测量执行时间并打印这些时间

```cpp
#include <iostream>
#include <chrono>
#include <fstream>
using namespace std;
using namespace std::chrono;

int main()
{
  ofstream file1("file1.txt");
  ofstream file2("file2.txt");

  // Write to file1 using endl 
  // To measure execution time in C++ 
  // refer to this article 
  // https://www.geeksforgeeks.org/measure-execution-time-function-cpp/  

  auto start = high_resolution_clock::now();
  for ( int i = 0; i < 100000; i++) {
    file1 << "Hello World " << std::endl ;
  }
  auto stop = high_resolution_clock::now();
  auto duration = duration_cast<microseconds>(stop-start);

  cout << "Writing to file using endl took "  
    << duration.count() << " microseconds" << std::endl;

  // Write to file2 using \n 

  start = high_resolution_clock::now();
  for ( int i = 0; i < 100000; i++) {
    file2 << "Hello World \n" ;
  }
  stop = high_resolution_clock::now();
  duration = duration_cast<microseconds>(stop-start);

  cout << "Writing to file using \\n took " 
    << duration.count() << " microseconds"<< std::endl;

  file1.close();
  file2.close();

  return 0;
}
```

输出:(取决于机器)

```cpp
Writing to file using endl took 3272 microseconds
Writing to file using \n took 1533 microseconds

```

从输出中可以看出，std::endl 花费了将近两倍的时间。在某些系统上，性能影响可能会更糟。请注意，可以保证 std::endl 将比直接向流中打印“\n”花费更多的时间。

参考资料:
[C++ 周刊–第 7 集](https://www.youtube.com/watch?v=GMqQOEZYVJQ)