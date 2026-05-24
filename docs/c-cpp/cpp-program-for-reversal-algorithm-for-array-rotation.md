# 数组旋转反转算法的 C++ 程序

> 原文:[https://www . geesforgeks . org/CPP-程序换反转-算法换阵列-旋转/](https://www.geeksforgeeks.org/cpp-program-for-reversal-algorithm-for-array-rotation/)

编写一个函数 rotate(arr[]，d，n)，将大小为 n 的 arr[]旋转 d 个元素。
**例:**

```cpp
Input :  arr[] = [1, 2, 3, 4, 5, 6, 7]
         d = 2
Output : arr[] = [3, 4, 5, 6, 7, 1, 2] 
```

![Array](img/ba17844d7fa31a1b00169a41fc3bc3d3.png)

将上面的数组旋转 2 将会形成数组

![ArrayRotation1](img/a0ca29059e52fd48e525698f91766984.png)

通过 d 元素旋转数组的前 3 种方法已经在[这篇](https://www.geeksforgeeks.org/array-rotation/)文章中讨论过了。
**方法 4(反转算法):**
**算法:**

```cpp
rotate(arr[], d, n)
  reverse(arr[], 1, d) ;
  reverse(arr[], d + 1, n);
  reverse(arr[], 1, n);
```

假设 AB 是输入数组的两部分，其中 A = arr[0..d-1]和 B = arr[d..n-1]。算法的思路是:

*   反向 A 得到 ArB，其中 Ar 是 A 的反向。
*   反向 B 得到 ArBr，其中 Br 是 B 的反向。
*   全部反转得到(ArBr) r = BA。

**例:**
让数组为 arr[] = [1，2，3，4，5，6，7]，d =2 和 n = 7
A = [1，2]和 B = [3，4，5，6，7]

*   反过来，我们得到 ArB = [2，1，3，4，5，6，7]
*   反 B，我们得到 ArBr = [2，1，7，6，5，4，3]
*   反过来，我们得到(ArBr)r = [3，4，5，6，7，1，2]

以下是上述方法的实现:

## C++

```cpp
// C++ program for reversal algorithm
// of array rotation
#include <bits/stdc++.h>
using namespace std;

/*Function to reverse arr[] from index start to end*/
void reverseArray(int arr[], int start, int end)
{
    while (start < end) {
        int temp = arr[start];
        arr[start] = arr[end];
        arr[end] = temp;
        start++ ;
        end--;
    }
}

/* Function to left rotate arr[] of size n by d */
void leftRotate(int arr[], int d, int n)
{
    if (d == 0)
        return;
    // in case the rotating factor is
    // greater than array length
    d = d % n;

    reverseArray(arr, 0, d - 1);
    reverseArray(arr, d, n - 1);
    reverseArray(arr, 0, n - 1);
}

// Function to print an array
void printArray(int arr[], int size)
{
    for (int i = 0; i < size; i++)
        cout << arr[i] << " ";
}

/* Driver program to test above functions */
int main()
{
    int arr[] = { 1, 2, 3, 4, 5, 6, 7 };
    int n = sizeof(arr) / sizeof(arr[0]);
    int d = 2;

    // Function calling
    leftRotate(arr, d, n);
    printArray(arr, n);

    return 0;
}
```

**输出:**

```cpp
3 4 5 6 7 1 2
```

**时间复杂度:** O(n)

更多详情请参考[数组旋转反转算法](https://www.geeksforgeeks.org/program-for-array-rotation-continued-reversal-algorithm/)的完整文章！