# For vs While

> 原文:[https://www.geeksforgeeks.org/for-versus-while/](https://www.geeksforgeeks.org/for-versus-while/)

**问题:**有没有以下两个循环不会以相同方式工作的例子？

```cpp
/*Program 1 --> For loop*/
for (<init-stmnt>; <boolean-expr>; <incr-stmnt>) 
{
   <body-statements>
}

/*Program 2 --> While loop*/
<init-stmnt>;
while (<boolean-expr>) 
{
   <body-statements>
   <incr-stmnt>
}
```

**解决方案:**
如果 body-语句包含 continue，那么这两个程序将以不同的方式工作

见下面的例子:程序 1 将打印“循环”3 次，但程序 2 将进入无限循环。

**程序 1 示例**

```cpp
int main()
{
  int i = 0;
  for(i = 0; i < 3; i++)
  {
    printf("loop ");
    continue;
  } 
  getchar();
  return 0;
}
```

**程序示例 2**

```cpp
int main()
{
  int i = 0;
  while(i < 3)
  {
    printf("loop"); /* printed infinite times */
    continue;
    i++ ; /*This statement is never executed*/
  } 
  getchar();
  return 0;
}
```

以上问题如需补充更多解答，请写评论。