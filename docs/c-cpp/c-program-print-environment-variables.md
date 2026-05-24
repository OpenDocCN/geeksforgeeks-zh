# C 程序打印环境变量

> 原文:[https://www . geesforgeks . org/c-程序-打印-环境-变量/](https://www.geeksforgeeks.org/c-program-print-environment-variables/)

C 标准对 C 中的主要功能描述如下

```cpp
The function called at program startup is named main. The 
implementation declares no prototype for this function. It shall 
be defined with a return type of int and with no parameters:
       int main(void) { /* ... */ }
or with two parameters (referred to here as argc and argv, though 
any names may be used, as they are local to the function in which
they are declared):
       int main(int argc, char *argv[]) { /* ... */ }
or equivalent;10) or in some other implementation-defined manner.
```

但是 ***大多数编译器也支持接受第三个参数的第三个 main 声明。第三个参数存储所有环境变量*** 。

```cpp
#include <stdio.h>

// Most of the C compilers support a third parameter to main which
// store all envorinment variables
int main(int argc, char *argv[], char * envp[])
{
    int i;
    for (i = 0; envp[i] != NULL; i++)
        printf("\n%s", envp[i]);
    getchar();
    return 0;
}
```

输出:

```cpp
ALLUSERSPROFILE=C:\ProgramData
CommonProgramFiles=C:\Program Files\Common Files
HOMEDRIVE=C:
NUMBER_OF_PROCESSORS=2
OS=Windows_NT
PATHEXT=.COM;.EXE;.BAT;.CMD;.VBS;.VBE;.JS;.JSE;.WSF;.WSH;.MSC
PROCESSOR_ARCHITECTURE=x86
PROCESSOR_IDENTIFIER=x86 Family 6 Model 42 Stepping 7, GenuineIntel
PROCESSOR_LEVEL=6
PROCESSOR_REVISION=2a07
ProgramData=C:\ProgramData
ProgramFiles=C:\Program Files
PUBLIC=C:\Users\Public
SESSIONNAME=Console
SystemDrive=C:
SystemRoot=C:\Windows
WATCOM=C:\watcom
windir=C:\Windows
```

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论