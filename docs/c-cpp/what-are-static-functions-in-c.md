# C

中的静态功能

> 原文:[https://www . geesforgeks . org/什么是静态函数 in-c/](https://www.geeksforgeeks.org/what-are-static-functions-in-c/)

先决条件:[C 中的静态变量](https://www.geeksforgeeks.org/static-variables-in-c/)

在 C 语言中，函数默认是全局的。函数名前的“ *static* 关键字使其成为静态的。比如下面的功能 *fun()* 就是静态的。

```cpp
static int fun(void)
{
  printf("I am a static function ");
}
```

与 C 语言中的全局函数不同，对静态函数的访问仅限于声明它们的文件。因此，当我们想要限制对函数的访问时，我们将它们设为静态。使函数成为静态的另一个原因是可以在其他文件中重用相同的函数名。

例如，如果我们将以下程序存储在一个文件*文件 1.c* 中

```cpp
/* Inside file1.c */ 
static void fun1(void)
{
  puts("fun1 called");
}
```

并将以下程序存储在另一个文件*文件 2.c*

```cpp
/* Inside file2.c  */ 
int main(void)
{
  fun1(); 
  getchar();
  return 0;  
}
```

中

现在，如果我们用命令“ *gcc file2.c file1.c* ”编译上述代码，我们会得到错误*“未定义引用‘fun 1’”*。这是因为 *fun1()* 在*文件 1.c* 中声明为*静态*，不能在*文件 2.c* 中使用。

如果你在上面的文章中发现任何不正确的地方，或者想分享更多关于 c 语言中静态函数的信息，请写评论。