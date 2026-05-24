# C 文件编译后的类型

> 原文：[https://www.geeksforgeeks.org/types-of-c-files-after-its-compilation/](https://www.geeksforgeeks.org/types-of-c-files-after-its-compilation/)

写完 [C 程序后](https://www.geeksforgeeks.org/c-programming-language/)，当我们编译和执行程序时，会创建各种类型的文件。你可以参考[编译一个 C 程序：幕后](https://www.geeksforgeeks.org/compiling-a-c-program-behind-the-scenes/)和[一个 C 程序是如何执行的？](https://www.geeksforgeeks.org/how-does-a-c-program-executes/)以获得更好的理解。

## 编译过程要点

以下是编译每个 C 文件时遵循的要点：

1.  每个 `.h` 头文件与其对应的 `.c` 文件一起编译，并创建一个头文件对象（`.o` 文件）。
2.  在编译 `main.c` 文件之前，它首先经过预处理器，然后编译器将其编译成汇编程序并创建目标文件（`main.o`）。
3.  然后链接器将 `main.o` 链接到所需的头文件和库，并创建一个可执行文件（程序 `.exe`）。

## 文件类型详解

1.  **源文件（`.c`）**：这些文件包含函数定义以及整个程序逻辑。这些文件是人类可读的，按照惯例，它们的名字以 `.c` 结尾。
2.  **头文件（`.h`）**：这些文件包含功能原型和各种[预处理器语句](https://www.geeksforgeeks.org/cc-preprocessors/)。它们用于允许源代码文件访问外部定义的函数。按照惯例，它们的名称以 `.h` 结尾。
3.  **目标文件（`.o`）**：这些文件作为编译器的输出产生。它们由二进制形式的函数定义组成，但它们本身是不可执行的。按照惯例，它们的名称以 `.o` 结尾。
4.  **二进制可执行文件（`.exe`）**：这些文件是作为一个名为[链接器](https://www.geeksforgeeks.org/linker/)的程序的输出产生的。链接器将许多目标文件链接在一起，生成一个可以直接执行的二进制文件。它包含链接器可以从归档文件中提取并在构建可执行文件时插入其中的符号。按照惯例，在 Windows 中它们的名字以 `.exe` 结尾。
5.  [**动态库**](https://www.geeksforgeeks.org/static-vs-dynamic-libraries/) **文件（`.so`、`.dylib`、`.dll`）**：一个动态库（`.so` 文件对于大多数 POSIX 系统，`.dylib` 适用于 macOS，`.dll` 文件适用于 Windows）在运行时由程序动态链接。这些有时也被称为共享库，因为一个库映像可以被许多程序共享。如果有多个应用程序正在使用动态库，则动态库具有占用较少磁盘空间的优势。此外，它们允许库更新（错误修复），而不必重建可执行文件。按照惯例，`.dll` 用于 Windows 中的命名，`.so` 用在 Linux 上，`.dylib` 在 macOS 上使用。