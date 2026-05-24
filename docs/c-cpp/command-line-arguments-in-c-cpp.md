# C/c++ 中的命令行参数

> 原文:[https://www . geesforgeks . org/命令行-参数-in-c-cpp/](https://www.geeksforgeeks.org/command-line-arguments-in-c-cpp/)

C/C++ 最重要的功能是 main()函数。它主要是用 int 的返回类型定义的，没有参数:

```cpp
int main() { /* ... */ } 

```

我们也可以用 C 和 C++ 给出命令行参数。在操作系统的命令行外壳中，命令行参数位于程序名称之后。
为了传递命令行参数，我们通常用两个参数定义 main():第一个参数是命令行参数的数量，第二个参数是命令行参数的列表。

```cpp
int main(int argc, char *argv[]) { /* ... */ }

```

或者

```cpp
int main(int argc, char **argv) { /* ... */ }

```

*   **argc (ARGument Count)** 是 int，存储用户传递的命令行参数的数量，包括程序的名称。因此，如果我们向程序传递一个值，argc 的值将是 2(一个用于参数，一个用于程序名)
*   argc 的值应该是非负的。
*   **argv(ARgum Vector)**是列出所有参数的字符指针数组。
*   如果 argc 大于零，从 argv[0]到 argv[argc-1]的数组元素将包含指向字符串的指针。
*   Argv[0]是程序的名称，之后直到 argv[argc-1]每个元素都是命令行参数。

为了更好的理解，在你的 linux 机器上运行这段代码。

```cpp
// Name of program mainreturn.cpp
#include <iostream>
using namespace std;

int main(int argc, char** argv)
{
    cout << "You have entered " << argc
         << " arguments:" << "\n";

    for (int i = 0; i < argc; ++ i)
        cout << argv[i] << "\n";

    return 0;
}
```

输入:

```cpp
$ g++ mainreturn.cpp -o main 
$ ./main geeks for geeks

```

输出:

```cpp
You have entered 4 arguments:
./main
geeks
for
geeks

```

**注意:**C 和 C++ 标准也允许其他平台相关的格式；例如，Unix(虽然不是 POSIX.1)和微软 Visual C++ 有第三个参数给出了程序的环境，否则可以通过 stdlib.h 中的 getenv 访问:有关详细信息，请参考 [C 程序打印环境变量](https://www.geeksforgeeks.org/c-program-print-environment-variables/)。

**命令行参数的属性:**

1.  它们被传递给 main()函数。
2.  它们是调用程序时提供给程序的参数/自变量。
3.  它们用于从外部控制程序，而不是对代码内部的那些值进行硬编码。
4.  argv[argc]是一个空指针。
5.  argv[0]保存程序的名称。
6.  argv[1]指向第一个命令行参数，argv[n]指向最后一个参数。

**注意:**您可以传递所有由空格分隔的命令行参数，但是如果参数本身有空格，那么您可以通过将它们放在双引号“”或单引号中来传递这些参数。

```cpp
// C program to illustrate
// command line arguments
#include<stdio.h>

int main(int argc,char* argv[])
{
    int counter;
    printf("Program Name Is: %s",argv[0]);
    if(argc==1)
        printf("\nNo Extra Command Line Argument Passed Other Than Program Name");
    if(argc>=2)
    {
        printf("\nNumber Of Arguments Passed: %d",argc);
        printf("\n----Following Are The Command Line Arguments Passed----");
        for(counter=0;counter<argc;counter++)
            printf("\nargv[%d]: %s",counter,argv[counter]);
    }
    return 0;
}
```

**不同场景下的输出:**

1.  **无参数:**当编译和执行上述代码时，不传递任何参数，它会产生以下输出。

    ```cpp
    $ ./a.out
    Program Name Is: ./a.out
    No Extra Command Line Argument Passed Other Than Program Name

    ```

2.  **三个参数:**当用三个参数编译并执行上述代码时，它会产生以下输出。

    ```cpp
    $ ./a.out First Second Third
    Program Name Is: ./a.out
    Number Of Arguments Passed: 4
    ----Following Are The Command Line Arguments Passed----
    argv[0]: ./a.out
    argv[1]: First
    argv[2]: Second
    argv[3]: Third

    ```

3.  **单参数:**当编译和执行上面的代码时，使用一个由空格分隔但在双引号内的单参数，它会产生以下输出。

    ```cpp
    $ ./a.out "First Second Third"
    Program Name Is: ./a.out
    Number Of Arguments Passed: 2
    ----Following Are The Command Line Arguments Passed----
    argv[0]: ./a.out
    argv[1]: First Second Third

    ```

4.  **用空格分隔的单引号中的单个参数:**当编译和执行上面的代码时，使用一个用空格分隔但在单引号中的单个参数，它会产生以下输出。

    ```cpp
    $ ./a.out 'First Second Third'
    Program Name Is: ./a.out
    Number Of Arguments Passed: 2
    ----Following Are The Command Line Arguments Passed----
    argv[0]: ./a.out
    argv[1]: First Second Third

    ```

**参考文献:**T2[http://www.cprogramming.com/tutorial/lesson14.html](http://www.cprogramming.com/tutorial/lesson14.html)T5[http://c0x.coding-guidelines.com/5.1.2.2.1.html](http://c0x.coding-guidelines.com/5.1.2.2.1.html)

This article is contributed by **Kartik Ahuja** and **[Avadhut Patade](https://in.linkedin.com/in/avadhut-patade-4b5a5069)**. If you like GeeksforGeeks and would like to contribute, you can also write an article using [write.geeksforgeeks.org](https://write.geeksforgeeks.org) or mail your article to review-team@geeksforgeeks.org. See your article appearing on the GeeksforGeeks main page and help other Geeks.Please write comments if you find anything incorrect, or you want to share more information about the topic discussed above.