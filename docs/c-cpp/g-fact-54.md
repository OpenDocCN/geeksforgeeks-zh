# C 和 C++ 中字符文字的类型差异

> 原文:[https://www.geeksforgeeks.org/g-fact-54/](https://www.geeksforgeeks.org/g-fact-54/)

C/C++ 中的每个文字(常量)都将有一个与之关联的类型信息。

在 C 和 C++ 中，数值文字(例如 10)的类型都是 *int* 。这意味着 *sizeof(10)* 和 *sizeof(int)* 将返回相同的值。

但是，字符文字(例如“V”)将有不同的类型，*sizeof(‘V’)*在 C 和 C++ 中返回不同的值。在 C 语言中，字符文字被视为 *int* 类型，而在 C++ 中，字符文字被视为 *char* 类型( *sizeof('V')* 和 *sizeof(char)* 在 C++ 中相同，但在 C 语言中不同)。

```cpp
int main()
{
   printf("sizeof('V') = %d sizeof(char) = %d", sizeof('V'), sizeof(char));
   return 0;
}
```

**上述程序的结果:**

c 结果-*sizeof(' v ')= 4 sizeof(char)= 1*

C++ 结果-*sizeof(' v ')= 1 sizeof(char)= 1*

这种行为在 C++ 中是必需的，以支持函数重载。举个例子会更清楚。预测以下 C++ 程序的输出。

```cpp
void foo(char c)
{
   printf("From foo: char");
}
void foo(int i)
{
   printf("From foo: int");
}

int main()
{
   foo('V');
   return 0;
}
```

编译器必须调用

```cpp
void foo(char);
```

因为“V”型是*充电*。

Venki 和 Geeksforgeeks 团队的文章贡献。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。