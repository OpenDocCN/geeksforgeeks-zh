# 数组元素的不常见表示

> 原文:[https://www . geeksforgeeks . org/一种不常见的数组元素表示法/](https://www.geeksforgeeks.org/an-uncommon-representation-of-array-elements/)

考虑下面的程序。

```cpp
int main( )
{
  int arr[2] = {0,1};
  printf("First Element = %d\n",arr[0]);
  getchar();
  return 0;
}
```

非常简单的程序..嗯…输出会是 0。

现在，如果您将 *arr[0]* 替换为 *0[arr]* ，输出将是相同的。因为编译器在访问数组元素之前会将数组操作转换为指针。

例如 *arr[0]* 将是 **(arr + 0)* ，因此 0[arr]将是 **(0 + arr)* ，您知道 **(arr + 0)* 和 **(0 + arr)* 是相同的。

如果你在上面的文章中发现任何不正确的地方，请写评论。