# 如何在 C 语言中不使用循环的情况下连接两个整数数组？

> 原文:[https://www . geesforgeks . org/如何在不使用 c 循环的情况下连接两个整数数组/](https://www.geeksforgeeks.org/how-to-concatenate-two-integer-arrays-without-using-loop-in-c/)

给定两个数组，使得第一个数组有足够的额外空间来容纳第二个数组的元素。C 语言中如何在不使用任何循环的情况下将第二个数组连接到第一个数组？

示例:

```cpp
Input: arr1[5] = {1, 2, 3}
       arr2[]  = {4, 5}
Output: arr1[] = {1, 2, 3, 4, 5}

```

**我们强烈建议你尽量减少浏览器，先自己试试这个。**

提示:我们可以在 c 语言中使用库函数。

想法是在 C.

```cpp
// arr1[] is of size m+n and arr2[] is of size n. This function
// appends contents of arr2[] at the end of arr1[]
void concatenate(int arr1[], int arr2[], int m, int n)
{
   memcpy(arr1 + m, arr2, sizeof(arr2)); 
}
```

中使用 [memcpy()](http://geeksquiz.com/memcpy-in-cc/) 或 [memmove()](http://geeksquiz.com/memmove-in-cc/)

完整的运行代码见[本](https://ide.geeksforgeeks.org/Kmuk8T)。

感谢[乌卡什·特里维迪](http://qa.geeksforgeeks.org/user/utkarsh111)提出上述解决方案。

如果您发现任何不正确的地方，或者您想分享关于上面讨论的主题的更多信息，请写评论