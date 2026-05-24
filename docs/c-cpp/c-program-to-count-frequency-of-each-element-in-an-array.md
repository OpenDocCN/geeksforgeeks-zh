# C 程序对数组中每个元素的频率进行计数

> 原文:[https://www . geesforgeks . org/c-程序对数组中每个元素的计数频率/](https://www.geeksforgeeks.org/c-program-to-count-frequency-of-each-element-in-an-array/)

给定一个大小为 **N** 的[数组](https://www.geeksforgeeks.org/array-data-structure/) **arr[]** ，任务是找出给定数组中每个不同元素的出现频率。

**示例:**

> **输入:** arr[] = { 1，100000000，3，10000000，3 }
> **输出:** { 1 : 1，3 : 2，100000000 : 2 }
> **解释:**
> 给定数组的不同元素是{ 1，100000000，3 }
> 给定数组中 1 的频率是 1。
> 给定数组中 100000000 的频率为 2。
> 给定数组中 3 的频率为 2。
> 因此，需要的输出为{ 1 : 1，100000000 : 2，3 : 2 }
> 
> **输入:**arr[]= { 1000000000，100000000，80000000，10000000 }
> T3】输出: { 100000000 : 3，800000000 : 1}

**方法:**使用[二分搜索法手法](https://www.geeksforgeeks.org/binary-search/)可以解决问题。按照以下步骤解决问题:

*   [按升序排列数组](https://www.geeksforgeeks.org/comparator-function-of-qsort-in-c/)。
*   [遍历数组](https://www.geeksforgeeks.org/comparator-function-of-qsort-in-c/)，对于每个不同的数组元素，[使用二分搜索法](https://www.geeksforgeeks.org/implementing-upper_bound-and-lower_bound-in-c/)找到其下限索引和上限索引，并存储在变量中，例如分别为 **LB** 和 **UB** 。将**(UB–LB)**的值打印为该元素的频率。

下面是上述方法的实现:

## C

```cpp
// C program to implement
// the above approach

#include <stdio.h>
#include <stdlib.h>

// Comparator function to sort
// the array in ascending order
int cmp(const void* a,
        const void* b)
{
    return (*(int*)a - *(int*)b);
}

// Function to find the lower_bound of X
int lower_bound(int arr[], int N, int X)
{
    // Stores minimum possible
    // value of the lower_bound
    int low = 0;

    // Stores maximum possible
    // value of the lower_bound
    int high = N;

    // Calculate the upper_bound
    // of X using binary search
    while (low < high) {

        // Stores mid element
        // of low and high
        int mid = low + (high - low) / 2;

        // If X is less than
        // or equal to arr[mid]
        if (X <= arr[mid]) {

            // Find lower_bound in
            // the left subarray
            high = mid;
        }

        else {

            // Find lower_bound in
            // the right subarray
            low = mid + 1;
        }
    }

    // Return the lower_bound index
    return low;
}

// Function to find the upper_bound of X
int upper_bound(int arr[], int N, int X)
{
    // Stores minimum possible
    // value of the upper_bound
    int low = 0;

    // Stores maximum possible
    // value of the upper_bound
    int high = N;

    // Calculate the upper_bound
    // of X using binary search
    while (low < high) {

        // Stores mid element
        // of low and high
        int mid = low + (high - low) / 2;

        // If X is greater than
        // or equal  to arr[mid]
        if (X >= arr[mid]) {

            // Find upper_bound in
            // right subarray
            low = mid + 1;
        }

        // If X is less than arr[mid]
        else {

            // Find upper_bound in
            // left subarray
            high = mid;
        }
    }

    // Return the upper_bound index
    return low;
}

// Function to find the frequency
// of an element in the array
int findFreq(int arr[], int N,
             int X)
{
    // Stores upper_bound index of X
    int UB = upper_bound(arr, N, X);

    // Stores lower_bound index of X
    int LB = lower_bound(arr, N, X);

    return (UB - LB);
}

// Utility function to print the frequency
// of each distinct element of the array
void UtilFindFreqArr(int arr[], int N)
{
    // Sort the array in
    // ascending order
    qsort(arr, N,
          sizeof(int), cmp);

    // Print start bracket
    printf("{ ");

    // Traverse the array
    for (int i = 0; i < N;) {

        // Stores frequency
        // of arr[i];
        int fr = findFreq(arr, N,
                          arr[i]);

        // Print frequency of arr[i]
        printf("%d : %d",
               arr[i], fr);

        // Update i
        i++ ;

        // Remove duplicate elements
        // from the array
        while (i < N && arr[i] == arr[i - 1]) {

            // Update i
            i++ ;
        }

        // If arr[i] is not
        // the last array element
        if (i <= N - 1) {

            printf(", ");
        }
    }

    // Print end bracket
    printf(" }");
}

// Driver Code
int main()
{
    int arr[] = { 1, 100000000, 3,
                  100000000, 3 };

    int N = sizeof(arr) / sizeof(arr[0]);

    UtilFindFreqArr(arr, N);
}
```

**Output:** 

```cpp
{ 1 : 1, 3 : 2, 100000000 : 2 }
```

***时间复杂度:** O(N * log(N))*
***辅助空间:** O(1)*