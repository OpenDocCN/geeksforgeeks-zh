# 去除 TLE 的方法

> 原文:[https://www.geeksforgeeks.org/ways-to-remove-tle/](https://www.geeksforgeeks.org/ways-to-remove-tle/)

在任何在线裁判上解决问题时，有时可能会超过[时限](https://www.geeksforgeeks.org/overcome-time-limit-exceedtle/)。下面是优化代码的一些方法:

## 最小化使用循环内部的循环，即嵌套循环

例如：

```cpp
for(i = 0 ; i < n ; i++)
{
    for(j = 0 ; j < n ; j++)
    {
        // *Your Code*
    }
}
```

上面的代码将执行 `N*N` 迭代，并且将花费更多的时间。为了避免这种情况，我们的想法是想出一种方法，最大限度地减少循环内循环的使用。

## 我不喜欢冗长的 if-else 列表，而更倾向于使用 switch 语句

例如：

```cpp
if(condition 1)
{

}
else
{
   if(condition 2)
   {

   }
   else
   {

   }
}
```

假设还有另一个条件 3，那么代码的流程是先检查条件 1，然后条件 2，然后会到达条件 3。因此，它需要 3 次操作。想法是使用下面的代码：

```cpp
switch (c)
{
    // Condition 1
    case 1:
       break;

    // Condition 2
    case 2 :
       break;

    // And so on
}
```

在开关的情况下，编译器将直接转到条件并执行它们，而不执行其他条件。

## 使用 `++i` 代替 `i = i+1`，使用 `i+= 3` 代替 `i = i+3`

## 除非必要，最好选择前置递增或递减，而不是后置递增或递减

例如：

```cpp
int i = 3;

// It will increment in the same step
++ i;

// It will increment in the next step
// so it will take more time
i++ ;
```

## 同样，应避免使用指针，并且可以在任何地方避免

指针指向变量的地址，这将进一步用于访问变量。因此，尝试直接访问变量，因为它们可以直接使用，所以可以减少时间。

## 对于字符串连接，使用 `StringBuilder` 或 `StringBuffer` 类，而不是 `+` 运算符

```cpp
// 1.Using "+" operator
String x="";
char c='a';
for(int i=0;i<10000;i++)
    x+=c;

// 2.Using StringBulider/StringBuffer Class
StringBuilder sb=new StringBuilder("");
char c='a';
for(int i=0;i<10000;i++)
    sb.append(c);
String x=sb.toString();
```

他们两个做同样的工作（制作一个 10000 个“a”字符的字符串）。但是第二个选项比第一个选项花费的时间少 10 倍。

因此，总是建议使用 `StringBuilder`（在 java 中）而不是 `+` 运算符进行连接。