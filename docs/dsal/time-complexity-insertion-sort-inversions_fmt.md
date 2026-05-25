# 有 `O(n)` 个反转时插入排序的时间复杂度？

> 原文：[https://www.geeksforgeeks.org/time-complexity-insertion-sort-inversions/](https://www.geeksforgeeks.org/time-complexity-insertion-sort-inversions/)

## 什么是倒置？

给定一个数组 `arr[]`，如果 `arr[i] < arr[j]` 和 `i > j`，一对 `arr[i]` 和 `arr[j]` 形成一个反转。例如，数组 `{1, 3, 2, 5}` 有一个反转 `(3, 2)`，数组 `{5, 4, 3}` 有反转 `(5, 4)`，`(5, 3)` 和 `(4, 3)`。我们已经讨论了一种基于[合并排序的算法来计数倒排](https://www.geeksforgeeks.org/counting-inversions/)。

## 有 `O(n)` 个反转时[插入排序](http://geeksquiz.com/insertion-sort/)的时间复杂度是多少？

考虑以下插入排序功能。

```c
/* Function to sort an array using insertion sort*/
void insertionSort(int arr[], int n)
{
   int i, key, j;
   for (i = 1; i < n; i++)
   {
       key = arr[i];
       j = i-1;

/* Move elements of arr[0..i-1], that are
          greater than key, to one position ahead
          of their current position */
       while (j >= 0 && arr[j] > key)
       {
           arr[j+1] = arr[j];
           j = j-1;
       }
       arr[j+1] = key;
   }
}
```

如果我们仔细看看插入排序代码，我们可以注意到 `while` 循环的每次迭代都会减少一次反转。`while` 循环仅在 `i > j` 且 `arr[i] < arr[j]` 时执行。因此，`while` 循环的总迭代次数（对于所有 `i` 值）与反转数量相同。因此，插入排序的总体时间复杂度为 `O(n + f(n))`，其中 `f(n)` 是反转计数。如果反转计数是 `O(n)`，那么插入排序的时间复杂度就是 `O(n)`。在最坏的情况下，可能会有 `n*(n-1)/2` 次反转。最坏情况发生在数组按相反顺序排序时。因此，插入排序的最坏情况时间复杂度是 `O(n^2)`。

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论。