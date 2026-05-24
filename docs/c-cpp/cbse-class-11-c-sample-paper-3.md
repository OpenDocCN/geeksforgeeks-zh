# CBSE 11 级 C++ 样纸-3

> 原文:[https://www . geesforgeks . org/cbse-class-11-c-sample-paper-3/](https://www.geeksforgeeks.org/cbse-class-11-c-sample-paper-3/)

**班- XI【计算机科学】
时长:3 小时
M. M. 70
一般说明:
(一)所有问题为必修
(二)编程语言:C++** 

**A 节**

**1。解释操作系统的任何两个重要特性。2**
操作系统有各种各样的特性。这些是:

*   内存管理
*   文件管理
*   硬件相互依赖
*   进程管理
*   图形用户界面
*   网络能力。

**[内存管理](https://www.geeksforgeeks.org/memory-management-mapping-virtual-address-physical-addresses/) :** 内存管理是操作系统的功能，它处理或管理主内存，并在执行过程中在主内存和磁盘之间来回移动进程。

[文件管理:](https://www.geeksforgeeks.org/file-system-operating-systems/)操作系统帮助在计算机系统中创建新文件，并将其放置在特定位置。它有助于在计算机系统中轻松快速地定位这些文件。它使得不同用户之间共享文件的过程非常容易和用户友好。

**2。GUI 和 CUI 有什么区别？2**
图形用户界面是一种图形表示，用户可以通过图形图标与软件或设备进行交互。
命令行界面(命令行界面)是一种基于控制台或文本的表示，用户在其中键入命令来操作软件或设备。

**3。复制和移动文件有什么区别？2**
Copy 是将选中的文件或文件夹复制一份，放在另一个驱动器或文件夹中，而 move 是将原始文件从一个位置移动到另一个位置。move 命令删除原始文件，而 copy 命令保留它们。

**B 节**

**1。用一个例子解释下列术语。(各 2 分)**
**a. [注释](https://www.geeksforgeeks.org/comments-in-c-c/) :** 在计算机编程中，注释是程序员可读的对计算机程序源代码的解释或注释。注释是不被编译器和解释器执行的语句。
在 C/C++ 中有两种类型的注释:
单行注释
多行注释
**参考:**[c++ 中的注释](https://www.geeksforgeeks.org/comments-in-c-c/)

**b .标识符**
标识符用作变量、函数和数组命名的通用术语。这些是用户定义的名称，由任意长的字母和数字序列组成，以字母或下划线(_)作为第一个字符。标识符名称的拼写和大小写必须不同于任何关键字。您不能将关键字用作标识符；它们是为特殊用途保留的。声明后，您可以在以后的程序语句中使用标识符来引用关联的值。goto 语句中可以使用一种特殊的标识符，称为语句标签。
**参考:** [C++ 令牌](https://www.geeksforgeeks.org/cc-tokens/)

**2。你说的编程错误是什么意思？解释所有类型的错误。3**
错误是用户执行的导致程序工作异常的非法操作。
**错误类型:**

*   **语法错误:**违反 C/C++ 语法编写规则时出现的错误称为语法错误。此编译器错误表明在编译代码之前必须修复一些问题。所有这些错误都被编译器检测到，因此被称为编译时错误。
*   **运行时错误:**成功编译后程序执行(运行时)过程中出现的错误称为运行时错误。示例:除以零误差。
*   **逻辑错误:**在编译和执行程序时，当给定某些输入值时，无法获得所需的输出。这些类型的错误提供不正确的输出，但看起来没有错误，被称为逻辑错误。

参考:[c++ 中的错误](https://www.geeksforgeeks.org/errors-in-cc/)

**3。解释术语 LIVEWARE。1**
在计算机系统或与计算环境相关的组织中工作的程序员、系统分析师、操作人员和其他人员被称为 Liveware。

**C 节**

**1。编写一个程序从用户那里读取一个数字，并检查给定的数字是否是质数。5**
你可以参考:[检查一个数字是否是质数](https://www.geeksforgeeks.org/primality-test-set-1-introduction-and-school-method/)

```cpp
// C++ program to check if a
// number is prime

#include <iostream>
using namespace std;

int checkprime(int n)
{
    ;
    int i, flag = 1;
    // Iterate from 2 to n/2
    for (i = 2; i <= n / 2; i++) {
        // If n is divisible by any number between
        // 2 and n/2, it is not prime

        if (n % i == 0) {
            flag = 0;
            break;
        }
    }

    if (flag == 1)
        cout << "prime number";

    else
        cout << "not a prime number";

    return 0;
}

int main()
{
    int n;
    // Ask user for input

    cout << "Enter a number: \n";

    // Store input number in a variable
    cin >> n;
    checkprime(n);
    return 0;
}
```

**2。编写一个函数来计算以下级数:1+X/X<sup>2</sup>+2X/X<sup>3</sup>+3X/X<sup>4</sup>+………..+ NX / X <sup>N+1</sup>**

```cpp
// C++ program to find sum of series
// 1 + X / X<sup>2</sup>
//+ 2X / X<sup>3</sup>+ …… + NX / X<sup>N+1
#include <iostream>
#include <math.h>
using namespace std;

double sum(int x, int n)
{
    double i, total = 1.0;
    for (i = 1; i <= n; i++)
        total = total + (i * x / pow(x, i + 1));
    return total;
}

// Driver code
int main()
{
    int x, n;
    cout << "enter the value of x \n";
    cin >> x;
    cout << "enter the number of terms \n";
    cin >> n;
    cout << "sum of series is:" << sum(x, n);
    return 0;
}
```

**3。计算以下 C++ 表达式，其中 a、b、C 是整数，d、f 是浮点数。a = 6，b = 2，d = 1.5(各 2 分)**
**a) f = a + b/a**
输出:6
**b)c =(a++)×d+b**
输出:8.5
**c)c = a –( b++)*(–a)**
输出:-5

**4。找出错误，画线并改正 4**

```cpp
Void main()
{
    int a, b = 2;
    cout >> “Enter a Value
                    cin
                << “a”;
    floating f = a / b;
    if (a = < b)
        cout << a <<” Greatest “;
    else
        cout << b << “ Greatest”;
    cout <<”Values of f is : “<< f;
    f + = 13;
    cout << Now Value of f is << f;
}
```

**正确代码:**

```cpp
#include <iostream.h>
void main()
{
    int a, b = 2;
    cout << “Enter a Value”;
    cin >> a;
    float f = a / b;
    if (a <= b)
        cout << a <<” Greatest “;
    else
        cout << b << “ Greatest”;
    cout <<”Values of f is : “<< f;
    f + = 13;
    cout << “Now Value of f is” << f;
}
```

**5。写一个程序来[求给定数的阶乘](https://www.geeksforgeeks.org/program-for-factorial-of-a-number/)。4**

```cpp
// C++ program to illustrate the
// before_begin() function
#include <bits/stdc++.h>
using namespace std;

int factorial(int n)
{
    if (n == 0 || n == 1)
        return 1;
    else
        return n * factorial(n - 1);
}

int main()
{
    int n;
    cout << "enter the number";
    cin >> n;
    cout << "the factorial is: " << factorial(n);
    return 0;
}
```

**6。编写一个函数来接受一个字符串、一个字符和一个整数。现在，字符串中“位置”处的“字符串”字符应替换为字符“Ch”4**

```cpp
// C++ program for above implementation
#include <iostream>
using namespace std;

// Function to print the string
void printString(string str, char ch, int pos)
{

    // If given count is 0
    // print the given string and return
    if (pos == 0) {
        cout << str;
        return;
    }

    str[pos - 1] = ch;
    cout << str;
}

// Drivers code
int main()
{
    string str = "geeks for geeks";
    char ch = 'x';
    int pos = 5;
    printString(str, ch, pos);
    return 0;
}
```

**7。写一个程序来读取一个矩阵，然后打印这个矩阵的转置。4**

```cpp
#include <iostream>
#define N 4

// This function stores transpose of A[][] in B[][]
void transpose(int A[][N], int B[][N])
{
    int i, j;
    for (i = 0; i < N; i++)
        for (j = 0; j < N; j++)
            B[i][j] = A[j][i];
}

int main()
{
    int A[N][N] = { { 1, 1, 1, 1 },
                    { 2, 2, 2, 2 },
                    { 3, 3, 3, 3 },
                    { 4, 4, 4, 4 } };
    int B[N][N], i, j;
    transpose(A, B);
    printf("Result matrix is \n");
    for (i = 0; i < N; i++) {
        for (j = 0; j < N; j++)
            printf("%d ", B[i][j]);
        printf("\n");
    }
    return 0;
}
```

**8。a . c++ 中有哪些类型的选择语句？给出每种类型的例子。2**
编程语言中的选择语句决定了程序执行的流向。C++ 中可用的决策语句有:

*   如果语句
*   如果..else 语句
*   嵌套 if 语句
*   如果-否则-如果梯子
*   switch 语句

**参考:**[C/c++ ](https://www.geeksforgeeks.org/decision-making-c-c-else-nested-else/)中的决策

**b 区分系统软件和应用软件。2**

*   **系统软件:**这些是直接允许用户与计算机系统的硬件组件交互的软件。系统软件可以称为计算机系统的主要软件，因为它处理运行硬件的主要部分。
    示例:操作系统
*   **应用软件:**这些是用来运行以完成特定动作和任务的基本软件。这些是专用软件，专门用于执行简单而单一的任务。
    示例:微软 Excel–用于准备 Excel 表格。

参考:[软件概念](https://www.geeksforgeeks.org/software-concepts/)

**c .区分编译器和解释器。2**

*   一个**编译器**获取整个程序，并将其转换成目标代码，通常存储在一个文件中。目标代码也称为二进制代码，可以在链接后由机器直接执行。
    例子:C 和 C++。
*   **解释器**直接执行用编程或脚本语言编写的指令，而无需事先将其转换为目标代码或机器代码。
    例子:Perl、Python 和 Matlab。

参考:[编译器 vs 解释器](https://www.geeksforgeeks.org/compiler-vs-interpreter-2/)

**d .解释一元、二元、三元算子？给出每种类型的例子。3**

*   **一元运算符**:对单个操作数进行运算或工作的运算符是一元运算符。
    示例:(++，–)
*   **二进制运算符**:运算或处理两个操作数的运算符是二进制运算符。
    例:+，–，*，/。
*   **三元运算符**:这些运算符需要 3 个表达式或操作数才能起作用。
    示例:条件运算符-表达式 1？表达 2:表达 3。
    这里，表达式 1 是要评估的条件。如果条件(表达式 1)为真，那么我们将执行并返回表达式 2 的结果，否则返回表达式 3 的结果。

参考:[c++ 中的运算符](https://www.geeksforgeeks.org/operators-c-c/)

**e .中断和继续有什么区别？举个例子。3**

*   Break statement:

    break 语句终止最小的封闭循环(即 while、do-while、for 或 switch 语句)

*   Continue statement:

    continue 语句跳过循环语句的其余部分，并导致循环的下一次迭代发生。

参考:[中断并继续语句](https://www.geeksforgeeks.org/difference-between-continue-and-break-statements-in-c/)

**D 节**

**1。什么是存储设备？详细讨论内存和只读存储器 4**

*   **随机存取存储器(RAM) :** 又称读写存储器或主存储器或主存储器。中央处理器在执行程序时需要的程序和数据都存储在这个存储器中。
    它是一个易失性存储器，因为断电时数据会丢失。
*   **只读存储器(ROM) :** 存储操作系统必不可少的关键信息，就像启动计算机必不可少的程序一样。
    它不反复无常，总是保留自己的数据。只读存储器用于嵌入式系统或编程不需要改变的地方。

参考:[内存和只读存储器](https://www.geeksforgeeks.org/types-computer-memory-ram-rom/)

**2。解释以下术语(各 1 个标记)**

**a. REGISTER** :这些是专用的快速存储设备，用来直接在 CPU 中存储数据。一个中央处理器包含一个寄存器文件，其中包含几个寄存器来存储当前在中央处理器中执行的数据。

**b. ALU** :算术逻辑单元是中央处理器的一部分，处理中央处理器可能需要的所有计算，例如加法、减法、比较。它执行逻辑运算、移位运算和算术运算

**c .非冲击式打印机**:这些打印机使用非冲击技术，如喷墨或激光技术。这些打印机以更高的速度提供更好的输出/输出质量。
示例:喷墨打印机

**3。线上和线下 UPS 有什么区别？2**
**在线不间断电源**系统在正常运行期间通过电源调节和充电组件获取电力。
**离线不间断电源**是一种系统，在正常运行期间，负载直接由原始电源供电，而不是逆变器输出，就负载而言，充电器、逆变器和电池等储能组件离线。