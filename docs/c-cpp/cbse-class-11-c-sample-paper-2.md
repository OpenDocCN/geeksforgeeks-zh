# CBSE 11 级 C++ |样纸-2

> 原文:[https://www . geesforgeks . org/cbse-class-11-c-sample-paper-2/](https://www.geeksforgeeks.org/cbse-class-11-c-sample-paper-2/)

**模拟题试卷
课- XI
计算机科学
上午 10:70 时间:3 小时。
说明:
1。所有问题都是必修的。
2。编程语言:C++**

**问题 1【答】一个[编译器和解释器](https://www.geeksforgeeks.org/compiler-vs-interpreter-2/)有什么不同？2**
编译器和解释器是执行用编程或脚本语言编写的程序的两种不同方式。

*   **编译器**获取整个程序，并将其转换为目标代码，目标代码通常存储在一个文件中。目标代码也被称为二进制代码，可以在链接后由机器直接执行。编译编程语言的例子有 C 和 C++。
*   **解释器**直接执行用编程或脚本语言编写的指令，而无需事先将其转换为目标代码或机器代码。解释语言的例子有 Perl、Python 和 Matlab。

参考:[编译器 vs 解释器](https://www.geeksforgeeks.org/compiler-vs-interpreter-2/)

**【B】你对应用软件的理解是什么？2**
这些是用来运行完成特定动作和任务的基本软件。这些是专用软件，专门用于执行简单而单一的任务。分为两种:
**a)通用应用软件:**
微软 Excel–用于准备 Excel 表格。
VLC 媒体播放器–用于播放音频/视频文件。
Adobe Photoshop–用于设计和动画等。
**b)特定用途应用软件:**
购票系统
健康管理系统
参考:[软件概念](https://www.geeksforgeeks.org/software-concepts/)

**【C】谁发明了穿孔卡片？1**
赫尔曼·何乐礼发明了打卡。

**【D】说出印度研发的超级计算机？1**
印度开发的超级计算机有:PARAM，ANURAG

**问题 2【答】优雅的退化是什么意思？2**
优雅降级是指计算机、机器、电子系统或网络即使在很大一部分被破坏或失效的情况下仍能保持有限功能的能力。

**【B】为什么逻辑错误更难定位？2**
提供不正确输出但看起来没有错误的错误类型称为逻辑错误。这些是编程初学者最常见的错误之一。
逻辑错误很难发现，因为隔离这些错误完全取决于程序员的逻辑思维，只有当我们沿着执行的路线，确定程序为什么走特定的执行路径时，才能发现这些错误。
参考:[逻辑错误](https://www.geeksforgeeks.org/errors-in-cc/)

**【C】写出开发程序所需的步骤，并简要说明步骤。3**
程序开发需要 6 个阶段，如下:
问题定义。
问题分析。
算法开发。
编码&文档。
测试&调试。
维护。

**Q3【A】命名以下所属的头文件:-2**
**(I)exit()**:process . h
**(ii)get()**:stdio . h
**(iii)to lower()**:ctype . h
**(iv)malloc()**:stdlib . h。

**【B】以下语句的输出会是什么:2**
**(I)a = sqrt(16)**:16
**(ii)B = strlen(“COMPUTER”)**:8
**(iii)c = ceil(13.45)**:14
**(iv)d = ABS(-6)**:6

**【C】sizeof 运算符的目的是什么？2**
Sizeof 是一个编译时一元运算符，可以用来计算其操作数的大小。sizeof 的结果是一个无符号整型。Sizeof 可以应用于任何数据类型，包括整型和浮点型等基本类型、指针类型或结构、联合等复合数据类型。
参考:[操作员尺寸](https://www.geeksforgeeks.org/g-fact-9/)

**【D】写出一元运算符和二元运算符 2**
**一元运算符:**作用于单个操作数以产生新值的运算符。
一元运算符的类型:一元减(-)、递增(++)、递减(–)、非(！)、运算符的地址(&)和 sizeof()运算符
**二进制运算符:**运算或处理两个操作数的运算符是二进制运算符。例如:二进制运算符的类型:加法(+)、减法(–)、乘法(*)、除法(/)等。
参考:[C/c++ ](https://www.geeksforgeeks.org/unary-operators-cc/)中的一元运算符，[c++ ](https://www.geeksforgeeks.org/operators-c-c/)中的运算符

**问题 4【答】写入口控制回路和出口控制回路 2** 之间的差异

*   **进入受控回路:**在这种类型的回路中，测试条件在进入回路主体之前进行测试。示例:For 循环和 While 循环是入口控制循环。
*   **退出受控循环:**在这类循环中，测试条件在循环体的末端进行测试或评估。因此，不管测试条件是真还是假，循环体都将至少执行一次。示例:在循环退出受控循环时执行。

参考:[c++ 中的循环](https://www.geeksforgeeks.org/loops-in-c/)

**【B】编写一个程序来输入一个字符，并打印给定的字符是字母、数字还是任何其他字符。**
逻辑:所有字符无论是字母、数字还是特殊字符都有 ASCII 值。用户输入的字符将决定是字母、数字还是特殊字符。
ASCII 值范围-
大写字母 65–90
小写字母 97–122
数字 48–57
所有其他情况都是特殊字符。

```cpp
// CPP program to find type of input character
#include <iostream>
using namespace std;

void charCheck(char input_char)
{
    // CHECKING FOR ALPHABET
    if ((input_char >= 65 && input_char <= 122))
        cout << " Alphabet ";

    // CHECKING FOR DIGITS
    else if (input_char >= 48 && input_char <= 57)
        cout << " Digit ";

    // OTHERWISE SPECIAL CHARACTER
    else
        cout << " Special Character ";
}

// Driver Code
int main()
{
    char input_char = '{content}apos;;
    charCheck(input_char);
    return 0;
}
```

**【C】给出以下程序段的输出:2**

```cpp
i.for (int i = 10; i > 6; i = i - 2)
        cout
    << i << endl;

Output : 10, 8

                 (ii) for (int i = -5; i > -7; i--)
                     cout
                 << i + 1 << endl;
>

    Output : -4,
    -5
```

**q . 5【A】以下两种说法有什么区别:-1**
**(I)int sum[10]；**
**(二)int sum[10]= 20；**
这两个语句的区别是:
在第一个语句中，已经声明了一个由 10 个元素组成的整数数组，并且没有为数组的元素赋值。
在第二个语句中，已经声明了一个由 10 个元素组成的整数数组，并且该数组的所有元素都被赋予了值= 20

**【B】删除语法错误后，重新编写以下程序，在每个
更正处加下划线。3**

```cpp
#include <iostream.h>
main()
{
 int x[5], y, z[5]
 for( i=0;i<5;i++
 {
        x[i] = i;
        z = i + 3;
        y = z;
        x = y;
 }
}

// Correct code:

void main()
{
    int x[5], y, z[5];
    for (int i = 0; i < 5; i++) {
        x[i] = i;
        z = i + 3;
        y = z;
        x[i] = y;
    }
}
```

**【C】找到以下程序的输出:2**

```cpp
#include <iostream.h>
main()
{
    int a[4], i;
    for (i = 0; i < 4; i++)
        a[i] = 5 * i;
    for (i = 0; i < 4; i++)
        cout << a[i];
}
```

输出:0、5、10、15

**【D】编写程序读取一个字符串，打印字符串中存储了多少字。3**

```cpp
// C++ program to count no of words
// from given input string.
#include <iostream>
using namespace std;
#define OUT 0
#define IN 1

// returns number of words in str
unsigned countWords(char* str)
{
    int state = OUT;
    unsigned wc = 0; // word count

    // Scan all characters one by one
    while (*str) {
        // If next character is a separator, set the
        // state as OUT
        if (*str == ' ')
            state = OUT;

        // If next character is not a word separator and
        // state is OUT, then set the state as IN and
        // increment word count
        else if (state == OUT) {
            state = IN;
            ++ wc;
        }

        // Move to next character
        ++ str;
    }
    return wc;
}

// Driver program to test above functions
int main(void)
{
    char str[] = "One two three  four five  ";
    cout<<"No of words : %u"<<countWords(str));
    return 0;
}
```

**【E】写程序求数组元素的和。3**

```cpp
#include <iostream>
using namespace std;

int arraysum(int arr[], int n)
{
    int i, sum = 0;
    for (i = 0; i < n; i++)
        sum = sum + arr[i];
    cout << sum;
    return 0;
}

int main()
{
    int arr[10];
    int i;
    cout << "enter array elements";
    for (i = 0; i < 10; i++)
        cin >> arr[i];
    arraysum(arr, 10);
    return 0;
}
```

**问题 6【A】功能原型是什么意思？1**
函数原型告诉编译器函数的参数个数、参数的数据类型和函数的返回类型。通过使用这些信息，编译器用函数定义和函数调用交叉检查函数参数及其数据类型。
参考:[功能原型](https://www.geeksforgeeks.org/what-is-the-purpose-of-a-function-prototype/)

**【B】范围是什么意思？C++ 支持各种范围的命名。3**
在编程中，变量的范围被定义为程序代码中我们可以访问、声明或使用的变量的范围。主要有两种类型的变量范围，如下所述:
**局部变量**
在函数或块中定义的变量被称为这些函数的局部变量。
**全局变量**
顾名思义，可以从程序的任何部分访问全局变量。它们在程序的整个生命周期中都是可用的。它们在所有函数或块之外的程序顶部声明。
参考:[c++ 中变量的作用域](https://www.geeksforgeeks.org/scope-of-variables-in-c/)

**【C】找到以下的输出:3**

```cpp
#include <iostream.h>
int max(int& x, int& y, int& z)
{
    if (x > y && y > z) {
        y++ ;
        z++ ;
        return x;
    }
    else {
        if (y > x)
            return y;
        else
            return z;
    }
    void main()
    {
        int a = 10, b = 13, c = 8;
        a = max(a, b, c);
        cout << a << b << c;
        b = max(a, b, c);
        cout << ++ a << ++ b << ++ c << endl;
    }
```

第一次调用 max(a，b，c)时 a=10，b=13，c=8，输出为:
13 13 8
第二次调用函数时，b 被赋值为 8，输出为:
14 9 9

**【D】写一个完整的 C++ 程序，读取一个有 15 个元素的浮点数组。程序使用函数 reverse()来[反转该数组。](https://www.geeksforgeeks.org/write-a-program-to-reverse-an-array-or-string/) 4**

```cpp
#include <iostream>
using namespace std;

// function to swap elements
int swap(float* a, float* b)
{
    float temp;
    temp = *a;
    *a = *b;
    *b = temp;
}
// function to reverse the elements by
// swapping each element from the start
// and the end

int reverse(float arr[])
{
    int i = 0, j = 14;
    while (i < j) {
        swap(&arr[i], &arr[j]);
        i++ ;
        j--;
    }
    for (i = 0; i < 15; i++)
        cout << arr[i] << endl;
    return 0;
}

// driver function
int main()
{
    float arr[5] = { 0 };
    int i;
    cout << "enter the elements";
    for (int i = 0; i < 15; i++)
        cin >> arr[i];
    reverse(arr);
}
```

**【E】用结果类型 float 写一个有两个参数 x 类型 float 和 n 类型 integer 的 C++ 函数，求以下级数的和:-**
1 + x/2！+ x <sup>2</sup> /4！+ x <sup>3</sup> /6！+……………+ x<sup>n</sup>/2n！

```cpp
#include <iostream>
#include <math.h>
using namespace std;

int fact(int z)
{
    if (z == 1)
        return 1;
    return x * fact(x - 1);
}

double sum(int x, int n)
{
    double i, total = 1.0;
    for (i = 1; i <= n; i++)
        total = total + (pow(x, i) / fact(2 * i));
    return total;
}

// Driver code
int main()
{
    int x;
    int n;
    cout << "" enter x and n ";
                               cin
                               >> x >> n printf("%.2f", sum(x, n));
    return 0;
}
```

**问题 7【答】在线 UPS 和离线 UPS 的区别。2**
在线不间断电源系统在正常运行期间通过电源调节和充电组件获取电能。
离线不间断电源是一种系统，在正常运行期间，负载直接由原始电源供电，而不是逆变器输出，就负载而言，充电器、逆变器和电池等储能组件处于离线状态。

**【B】说明打印机有哪两类？2**
打印机是用于在纸上准备永久输出设备的输出设备。打印机可以分为两大类:
**冲击打印机:**在这种情况下，锤子或大头针敲击色带和纸张来打印文本。这种机构被称为机电机构。它们有两种类型。
示例:
字符打印机:一次只打印一个字符。它的速度相对较慢。其中有点阵打印机。
点阵打印机:打印字符为点的组合。点阵打印机是串行打印机中最受欢迎的。
**无冲击打印机**:这些打印机使用喷墨或激光技术等无冲击技术。这些打印机以更高的速度提供更好的输出/输出质量。
示例:喷墨打印机

**【C】什么是访问时间。1**
访问时间是从一个存储设备访问开始到下一个访问可以开始的时间。访问时间包括延迟(到达设备上正确位置并准备访问它的开销)和传输时间。
该术语既适用于随机存取存储器(RAM)访问，也适用于硬盘和光盘访问

**【E】将以下内容转换为其二进制等价数系:-3**
**(I)(EB4A)<sub>16</sub>=(60234)<sub>10</sub>**
**(ii)(84)<sub>10</sub>=(1010100)<sub>2</sub>**
**(iii)(B2F)<sub>16</sub>=(53)**

详情请参考:[基础换算](https://www.geeksforgeeks.org/number-system-and-base-conversions/)

**【F】求下列 8 位一的补码形式:2**
**(I)-14****(ii)-49**
解:负数的 1 的补码是通过翻转其二进制表示的位来计算的。
-14 =-(00001110)<sub>2</sub>=(11110001)<sub>1 的</sub>T13】-49 =-(00110001)<sub>2</sub>=(11001110)<sub>1 的</sub>