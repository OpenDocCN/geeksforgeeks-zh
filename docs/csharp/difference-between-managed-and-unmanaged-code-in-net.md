# 中托管和非托管代码的区别。NET

> 原文:[https://www . geesforgeks . org/托管和非托管代码在网络中的区别/](https://www.geeksforgeeks.org/difference-between-managed-and-unmanaged-code-in-net/)

**托管代码**是由*的 CLR(公共语言运行时)管理的代码。NET 框架*。而非托管代码是由操作系统直接执行的代码。下面是托管代码和非托管代码之间的一些重要区别:

<figure class="table">

| 

托管代码

 | 

【非托管代码

 |
| --- | --- |
| It is executed by the managed runtime environment or managed by CLR. | Directly executed by the operating system. |
| It provides security for written applications. NET framework. | No security guarantee is provided for the application. |
| The memory buffer has not overflowed. | There may be a memory buffer overflow. |
| Provide runtime services such as garbage collection and exception handling. | Do not provide runtime services such as garbage collection and exception handling. |
| The source code is compiled in the intermediate language *IL or MSIL or CIL* . | Compile the source code directly into the native language. |
| It does not provide low-level access to programmers. | It provides programmers with low-level access rights. |

</figure>