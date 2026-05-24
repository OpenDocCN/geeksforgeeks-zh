# C 语言中实用程序指令的类型

> 原文:[https://www . geesforgeks . org/type-of-pragma-instructions-in-c/](https://www.geeksforgeeks.org/types-of-pragma-directives-in-c/)

**Pragma 指令:**[Pragma 指令](https://www.geeksforgeeks.org/pragma-directive-in-c-c/)用于控制程序特定部分的编译器动作，而不影响整个程序。

*   Pragma 指令包含在 [C 程序](https://www.geeksforgeeks.org/c-programming-language/)中才能生效。
*   pragma 的效果将从它被包含的地方应用到编译单元的末尾，或者直到另一个 pragma 改变它的状态。
*   一个 **#pragma** 指令是对编译器的指令，在预处理过程中通常被忽略。

**语法:**

> #pragma 字符串

这里[字符串](https://www.geeksforgeeks.org/string-data-structure/)可以是给编译器的指令之一，带有任何需要的参数。

<figure class="table">

| **指令** | **描述** |
| --- | --- |
| **着作权** | 指定版权字符串 |
| **着作权 _DATE** | 为版权字符串指定版权日期 |
| **优化** | 要打开或关闭优化功能 |
| **location** | 命名一个编码子空间 |
| **OPT_LEVEL** | 设置优化级别 |
| **HP_SHLIB_VERSION** | 创建共享库例程的版本 |
| **版本号** | 要指定版本字符串 |
| **一次** | 指定文件只打开一次 |

</figure>

**<u>实用程序指令类型</u> :**

### **pragma COPYRIGHT:**

pragma 版权的**语法**为:

> #pragma 版权“字符串”

*   这里，字符串指定了包含在目标文件的版权消息中的字符集。
*   如果在 pragma 版权期间未指定任何数据，则在版权消息中使用当前年份:

**示例:**如果以以下方式写入拷贝:

> #pragma 版权所有“GFG 私人有限公司”

*   然后将以下字符串放入目标代码中(假设当前年份是 2020 年):

> 版权所有 GFG 私人有限公司，2020。
> 保留所有权利。未经 GFG 私人有限公司事先书面同意，不得复制、复制或传播本程序的任何部分。

**注意:**要查看版权字符串以及对象文件中的任何其他字符串，请使用 strings(1)命令和-a 选项。

**示例:**

> strings -and ObjectFileName.o

### **害虫版权 _DATE:**

pragma 的**语法**版权所有:

> # pragma COMPORITY _ DATE“string”

在这里，字符串是一个将被 COMPORITY pragma 使用的日期。
考虑下面给出的例子:

> # pragma COPYRIGHT _ DATE“2011-2020”
> # pragma COPYRIGHT“GFG 私人有限公司”

上面的 pragma 将在目标代码中放置以下字符串:

> 版权所有 GFG 私人有限公司，2011-2020。
> 保留所有权利未经 GFG 私人有限公司事先书面同意，不得影印、复制或传播本节目的任何部分。

**注意:**要查看对象文件中的 **COPYRIGHT_DATE** 字符串以及任何其他字符串，请使用带有 **-a** 选项的 strings(1)命令。
**例:**

> strings -and ObjectFileName.o

### **pragma OPT_LEVEL:**

用于将优化级别设置为 1、2、3 或 4 的 pragma OPT_LEVEL 的**语法**为:

> # pragma OPT _ LEVEL 1
> # pragma OPT _ LEVEL 2
> # pragma OPT _ LEVEL 3
> # pragma OPT _ LEVEL 4

像优化 pragma 一样，即使是 pragma 也不能在函数中使用。最后，OPT_LEVEL 3 和 4 只允许出现在文件的开头。

下面是 C 语言中的一个示例代码片段，演示了 pragma opt 级别的使用:

## C

```cpp
aCC - O prog.C

#pragma OPT_LEVEL 1

      // Optimise func1() at level 1
      void
      Func1()
{
}

#pragma OPT_LEVEL 2

// Optimize Func2() to at level 2
void Func2()
{
}
```

### **pragma OPTIMIZE:**

使用 pragma OPTIMIZE 的**语法**是:

> #pragma 优化开启
> #pragma 优化关闭

*   pragma 优化基本上是用来打开/关闭源程序部分的优化。
*   但是，当使用 pragma 时，请在 ACC 命令上指定一个优化选项(同时给出编译程序的命令)，否则，该 pragma 将被忽略。
*   另外，请记住，pragma 优化不能在函数中使用。

下面是 C 语言中的一个示例代码片段，演示了优化实用程序的使用:

## C++

```cpp
// Set optimization to level 2
// for Prog.C
aCC + O2 Prog.C

#pragma OPTIMISE OFF
      void Func1
{
    // Turn off optimization for
    // this function
}

#pragma OPTIMISE ON
Void Func2()
{
    // Restore optimization to level 2
}
```

### **<u>HP _ shlib _ version</u>害虫:T3]**

用于创建不同版本共享库例程的惠普 _SHLIB_VERSION 的语法是:

> # pragma HP _ SHLIB _ VERSION["]日期["]

**示例:**

> # pragma _ shlib _ version["]12/20["]

*   这里，数据参数的形式是月/年，可选地用引号括起来。
*   必须使用 1 到 12 之间的任何数字来指定月份。
*   年份可以指定为年份的最后两位数字(2011 年为 11)或整年规格(2011 年)。
*   下面是 11 到 20 的两位实数，分别代表 2011 年到 2020 年。
*   只有在对源文件进行不兼容的更改时，才应该使用 pragma。

### **pragma location:**

用于指定与写入可重定位对象模块的代码相关联的名称的 pragma 局部性的**语法**是:

> # pragma location“string”

**示例:**

> # pragma LOCALITY“极客为极客”

*   在上面的例子中，字符串(“极客的极客”)指定了一个用于编码子空间的名称。
*   在此指令之后，该指令后面的所有代码都与字符串中指定的名称相关联。
*   唯一 LOCALITY pragma 的最小范围是一个函数。

### **pragma VERSION ID:**

pragma VERSION ID 的**语法**可以给出如下:

> #pragma VERSIONID "string "

这里的字符串是放在目标文件中的字符串。

**示例:**

> # pragma VERSIOND“GFG 私人有限公司，版本 1234 5.8.0 1.10”

在上例中，pragma 将 **GFG 私人有限公司版本 1234 5.8.0 1.10** 的角色极客放入对象文件中。

### **pragma 一次:**

pragma 一旦指定了包含该 pragma 目录的文件将只被编译器在特定文件的构建中打开一次，其**语法**可以给出为:

> #pragma 一次

**结论:**

*   pragma 预处理器指令主要用于 C 的每个实现都支持其主机或[操作系统](https://www.geeksforgeeks.org/operating-systems/)独有的一些特性的情况。
*   例如，一些程序可能需要对放置数据的[内存](https://www.geeksforgeeks.org/introduction-to-memory-and-memory-units/)区域进行精确控制，或者控制某些函数接收参数的方式。在这种情况下， **#pragma** 指令为每个编译器提供特定于操作系统的特性，同时保持与 C 语言的整体兼容性。