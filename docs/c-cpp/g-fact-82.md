# C

中的偏移()与倒带()

> 原文:[https://www.geeksforgeeks.org/g-fact-82/](https://www.geeksforgeeks.org/g-fact-82/)

在 C 语言中，应该优先使用 fseek()而不是 rewind()。

注意下面的文本 C99 标准:
*倒带功能将流指向的流的文件位置指示器设置到文件的开头。相当于*

```cpp
(void)fseek(stream, 0L, SEEK_SET)
```

*除了流的错误指示器也被清除。*

下面的代码示例使用 rewind()将输入流的文件位置指示器设置回开头。但是没有办法检查倒带()是否成功。

```cpp
int main()
{
  FILE *fp = fopen("test.txt", "r");

  if ( fp == NULL ) {
    /* Handle open error */
  }

  /* Do some processing with file*/

  rewind(fp);  /* no way to check if rewind is successful */

  /* Do some more precessing with file */

  return 0;
}
```

**在上面的代码中，可以用 fseek()代替 rewind()来查看操作是否成功。下面几行代码可以用来代替倒带(FP)；**

```cpp
if ( fseek(fp, 0L, SEEK_SET) != 0 ) {
  /* Handle repositioning error */
}
```

**来源:** [https://www . securecoding . cert . org/convergence/display/seccode/FIO07-c .+prefere+fseek % 28% 29+to+rewind % 28% 29](https://www.securecoding.cert.org/confluence/display/seccode/FIO07-C.+Prefer+fseek%28%29+to+rewind%28%29)

本文由**拉胡尔·古普塔**供稿。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。