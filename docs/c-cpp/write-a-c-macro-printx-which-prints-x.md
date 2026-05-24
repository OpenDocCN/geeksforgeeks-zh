# 写一个打印 x 的 C 宏 PRINT(x)

> 原文:[https://www . geesforgeks . org/write-a-c-macro-printx-what-print-x/](https://www.geeksforgeeks.org/write-a-c-macro-printx-which-prints-x/)

乍一看，写一个打印论点的 C 宏似乎是儿戏。以下程序应该工作，即它应该打印 *x*

```cpp
#define PRINT(x) (x)
int main()
{ 
  printf("%s",PRINT(x));
  return 0;
}
```

但是它会发出编译错误，因为被编译器作为变量的 *x* 的数据类型是未知的。现在看起来没那么明显了。不是吗？你猜怎么着，下面这些也行不通

```cpp
#define PRINT(x) ('x')
#define PRINT(x) ("x")
```

但是如果我们知道 C 语言一个不太为人所知的特点，写这样一个宏真的是儿戏。🙂在 C 语言中，有一个#指令，也叫做‘Stringizing Operator’，它具有这种魔力。基本上#指令将其参数转换为字符串。瞧啊。剩下的就这么简单了。所以上面的程序可以修改如下。

```cpp
#define PRINT(x) (#x)
int main()
{ 
  printf("%s",PRINT(x));
  return 0;
}
```

现在如果输入是 *PRINT(x)* ，就会打印 *x* 。事实上，如果输入的是 *PRINT(极客)*，它会打印*极客*。

你可以从微软门户 [**这里**](http://msdn.microsoft.com/en-us/library/7e3a913x(VS.80).aspx) 找到这个指令的细节。