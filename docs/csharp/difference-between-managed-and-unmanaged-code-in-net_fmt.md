# 托管和非托管代码在 .NET 中的区别

> 原文: [https://www.geeksforgeeks.org/difference-between-managed-and-unmanaged-code-in-net/](https://www.geeksforgeeks.org/difference-between-managed-and-unmanaged-code-in-net/)

**托管代码**是由 .NET 框架的 `CLR`（公共语言运行时）管理的代码。而非托管代码是由操作系统直接执行的代码。下面是托管代码和非托管代码之间的一些重要区别：

<figure class="table">

| 托管代码 | 非托管代码 |
| --- | --- |
| 由托管运行时环境或 `CLR` 执行。 | 由操作系统直接执行。 |
| 为 .NET 框架编写的应用程序提供安全性。 | 不为应用程序提供安全性保证。 |
| 内存缓冲区不会溢出。 | 可能存在内存缓冲区溢出。 |
| 提供运行时服务，如垃圾回收和异常处理。 | 不提供运行时服务，如垃圾回收和异常处理。 |
| 源代码被编译为中间语言 `IL` 或 `MSIL` 或 `CIL`。 | 将源代码直接编译为本机语言。 |
| 不向程序员提供低级访问权限。 | 向程序员提供低级访问权限。 |

</figure>