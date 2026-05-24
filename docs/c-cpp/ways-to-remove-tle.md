# 去除 TLE 的方法

> 原文:[https://www.geeksforgeeks.org/ways-to-remove-tle/](https://www.geeksforgeeks.org/ways-to-remove-tle/)

在任何在线裁判上解决问题时，有时可能会超过[时限](https://www.geeksforgeeks.org/overcome-time-limit-exceedtle/)。下面是优化代码的一些方法:

*   **Minimize the use of** [**loop**](https://www.geeksforgeeks.org/loops-in-c-and-cpp/) **internal loop, namely** [**nested loop**](https://www.geeksforgeeks.org/nested-loops-in-c-with-examples/) **:** For example:

```cpp
     for(i = 0 ; i < n ; i++)
     {
           for(j = 0 ; j < n ; j++)
           {
                // *Your Code*
           }
      }
```

上面的代码将执行 **N*N** 迭代，并且将花费更多的时间，为了避免这种情况，我们的想法是想出一种方法，最大限度地减少循环内循环的使用。

*   **I don't like a long list of** [**if-else**](https://www.geeksforgeeks.org/decision-making-javaif-else-switch-break-continue-jump/) **, but I prefer to use** [**switch statement**](https://www.geeksforgeeks.org/switch-statement-cc/) **:** For example:

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

假设还有另一个条件 3，那么代码的流程是先检查**条件 1** ，然后**条件 2** ，然后会到达**条件 3** 。因此，它需要 3 次操作。想法是使用下面的代码:

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

*   Instead of **"I = I+1"** , I prefer **"++ I"** , instead of **"I = I+3"** , use **"I+= 3"**
*   It is better to choose [**to pre-increase or pre-decrease**](https://www.geeksforgeeks.org/g-fact-40/) **instead of** [**to increase and then decrease**](https://www.geeksforgeeks.org/pre-increment-and-post-increment-in-c/) until and unless necessary. For example:

```cpp
int i = 3;

// It will increment in the same step
++ i;

// It will increment in the next step
// so it will take more time
i++ ;
```

*   Similarly, the use of [pointer](https://www.geeksforgeeks.org/pointers-in-c-and-c-set-1-introduction-arithmetic-and-array/) should be avoided, and it can be avoided everywhere. Pointer to the address of a variable, which will be further used to access the variable. Therefore, try to access variables directly, because they can be used directly, so time can be reduced.
*   Use StringBuilder or StringBuffer class for concatenation instead of "+"operator.

```cpp
        1.Using "+" operator
        String x="";
        char c='a';
        for(int i=0;i<10000;i++)
          x+=c;

        2.Using StringBulider/StringBuffer Class
        StringBuilder sb=new StringBuilder("");
        char c='a';
        for(int i=0;i<10000;i++)
         sb.append(c);
        String x=sb.toString();
```

他们两个做同样的工作(制作一个 10000 个“a”字符的字符串)。但是第二个选项比第一个选项花费的时间少 10 倍。

因此，总是建议使用 StringBuilder(在 java 中)而不是“+”运算符进行连接。