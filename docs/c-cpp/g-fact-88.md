# 【free()如何知道要解除分配的内存大小？

> 原文:[https://www.geeksforgeeks.org/g-fact-88/](https://www.geeksforgeeks.org/g-fact-88/)

考虑以下 *[free()](http://www.cplusplus.com/reference/clibrary/cstdlib/free/)* 函数的原型，该函数用于释放使用 *malloc()* 或 *calloc()* 或 *realloc()* 分配的内存。

```cpp
void free(void *ptr);
```

请注意，自由函数不接受大小作为参数。free()函数如何知道给定一个指针需要释放多少内存？

下面是存储内存大小的最常见方法，以便 free()知道要释放的内存大小。
*内存分配完成后，实际分配的堆空间比请求的内存大一个字。多余的字用于存储分配的大小，稍后由 free( )* 使用

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。

参考文献:
[http://www . cs . CMU . edu/AFS/cs/academic/class/15213-F10/www/讲课/17-分配-basic . pptx](http://www.cs.cmu.edu/afs/cs/academic/class/15213-f10/www/lectures/17-allocation-basic.pptx)