# 将 C/C++ 程序转换为预处理器代码

> 原文:[https://www . geesforgeks . org/convert-c-c-程序到预处理器-代码/](https://www.geeksforgeeks.org/convert-c-c-program-to-preprocessor-code/)

我们使用 g++ 编译器将提供的 Cpp 代码转换成预处理器代码。要查看 CPP 编译器生成的预处理器代码，我们可以使用命令行上的“-E”选项:
预处理器在代码中包含所有的 **#** 指令。并且还扩展了**宏**功能。

```cpp
Syntax:
g++ -E filename.cpp

```

```cpp
// MACRO named MAX initialism to 10
#define MAX 10

int main()
{

    int a = MAX, b = MAX;

    // Add two values.
    int c = a + b;

    return 0;
}
```

**运行命令:**

```cpp
g++ -E geeks.cc

```

输出:

```cpp
int main()
{

    int a = 10, b = 10;

    // Add two values.
    int c = a + b;

    return 0;
}

```