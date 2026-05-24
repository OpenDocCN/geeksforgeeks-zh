# C++ | asm 声明

> 原文:[https://www.geeksforgeeks.org/c-asm-declaration/](https://www.geeksforgeeks.org/c-asm-declaration/)

正如我们所知，C++ 是一种全面而强大的编程语言，但是很少有它无法处理的高度专门化的情况。对于这些情况，C++ 提供了一个可以随时删除汇编代码的选项。这个选项是使用' asm '语句。使用 asm 语句，汇编语言可以直接嵌入到 C++ 程序中。asm 关键字接受一个必须是字符串的字段。
ASM 关键字的一般形式是:

```cpp
asm("op-code");
```

**操作码**:这是将被包含在程序中的汇编语言指令。

一些编译器使用以下形式的 asm 语句:

```cpp
asm instruction;
asm instruction newline
asm {instruction sequence }

```

一些 GCC 内联程序集语法如下:

1.  **寄存器命名:**寄存器名称以%为前缀。
    例如-寄存器是%eax、%cl 等，而不仅仅是 eax、cl。

    ```cpp
    #include<bits/stdc++.h>
    using namespace std;

    int main() {
    int res;
    // move value to register %eax
    // move value to register %ebx
    // subtracting and storing result in res
    __asm__ ( "movl $20, %%eax;"
                    "movl $10, %%ebx;"
                    "subl %%ebx, %%eax ":"=a"(res));
        cout<<res;
       return 0;

    }
    ```

    **输出:**

    ```cpp
    10

    ```

2.  **操作数的顺序:**与英特尔惯例(第一个操作数是目标)不同，操作数的顺序是源在前，目标在后。
    例如，英特尔语法“mov eax，edx”在 AT & T 汇编中将看起来像“mov %edx，%eax”。

    ```cpp
    #include<bits/stdc++.h>
    using namespace std;

    int main() {
    int res;
    // source 5 is written first
    // then destination register is written
    // this will move 5 to register
    __asm__ ( "movl $5, %%eax;": "=a"(res));
        cout<<res;
       return 0;

    }
    ```

    **输出:**

    ```cpp
    5

    ```

3.  **立即操作数:**立即操作数用$前缀标记。例如，就像在“addl $5，%eax”中一样，这意味着向注册%eax 添加立即长值 5。

    ```cpp
    #include<bits/stdc++.h>
    using namespace std;

    int main() {
    int res;
    // move immediate value 50 to register eax
    // move immediate value 20 to register ebx
    // the added value is stored in res for output
    __asm__ ( "movl $50, %%eax;"
                    "movl $20, %%ebx;"
                    "addl %%ebx, %%eax ":"=a"(res));
        cout<<res;
       return 0;

    }
    ```

    **输出:**

    ```cpp
    70

    ```

这基本上显示了内联程序集在 c++ 中的使用。术语内联用于指示编译器在进行实际调用的地方将函数的代码插入其调用方的代码中。这种函数称为“内联函数”。它减少了函数调用开销。使用 asm 关键字，汇编代码被写成内联函数。
ASM 关键字使用的简单示例:

```cpp
#include<bits/stdc++.h>
using namespace std;
int main()
{
  // generates interrupt 5
  asm int 5;  

  return 0;
} 
```

当在 DOS 下运行时，这个程序产生一个 INT 5 指令，调用打印屏幕功能。

内联程序集可以以以下两种格式使用:

```cpp
asm("assembly code") or __asm__("assembly code")
```

说明 asm 关键字使用的程序:

```cpp
#include<bits/stdc++.h>
using namespace std;
int main()
{
  int val1,val2, add, sub, mul;

   val1=100;val2=20;
    asm( "addl %%ebx, %%eax;" : "=a" (add) : "a" (val1) , "b" (val2) );
    asm( "subl %%ebx, %%eax;" : "=a" (sub) : "a" (val1) , "b" (val2) );
    asm( "imull %%ebx, %%eax;" : "=a" (mul) : "a" (val1) , "b" (val2) );
 printf( "%d + %d = %d\n ", val1, val2, add );
    printf( "%d - %d = %d ", val1,val2, sub );
    printf( "%d * %d = %d ", val1, val2, mul );

  return 0;
} 
```

**Output:**

```cpp
100 + 20 = 120
 100 - 20 = 80 100 * 20 = 2000

```

**示例:**

```cpp
Input : 10 20 
Output :10+20=30 10-20=-10 10*20=200 

Input : 30 20
Output :30+20=50 30-20=10 30*20=600

```

上述程序在 asm 关键字的帮助下，使用内联程序集执行加法、减法和乘法运算。