# 时间复杂度的其他问题

> 原文：[https://www.geeksforgeeks.org/miscellaneous-problems-of-time-complexity/](https://www.geeksforgeeks.org/miscellaneous-problems-of-time-complexity/)

**先决条件：** [渐近符号](https://www.geeksforgeeks.org/analysis-of-algorithms-set-3asymptotic-notations/)

**时间复杂度：**
时间复杂度是算法所需的时间，表示为问题大小的函数。也可以定义为运行一个程序到完成所需的计算机时间。当我们解决一个时间复杂度的问题时，这个定义帮助最大——
“它是算法相对于输入大小完成任务的操作数。”

以下是一些时间复杂性的杂七杂八的问题，在不同类型的测验中经常被问到。

## 1. 以下代码的时间复杂度是多少

```c
void function(int n)
{
    int i = 1, s = 1;
    while (s < n) {
        s = s + i;
        i++;
    }
}
```

**解：**
时间复杂度 = `O(√n)`。

**解释：**
我们可以根据关系 `S_i = S_{i-1} + i` 来定义‘S’术语，让 `k` 为程序的迭代总次数。

| **i** | **S** |
| :--- | :--- |
| 1 | 1 |
| 2 | 2 |
| 3 | 2 + 2 |
| 4 | 2 + 2 + 3 |
| … | … |
| k | 2 + 2 + 3 + 4 + ……+ k |

当 `S >= n` 时，则循环将停止在第 `k` 次迭代，
`S >= n`
`S = n`
`2 + 2 + 3 + 4 + ……+ k = n`
`1 + (k * (k + 1)) / 2 = n`
`k^2 = n`
`k = √n`
因此，时间复杂度为 `O(√n)`。

## 2. 以下代码的时间复杂度是多少

```cpp
void fun(int n)
{
    if (n < 5)
        cout << "GeeksforGeeks";
    else {
        for (int i = 0; i < n; i++) {
            cout << i << " ";
        }
    }
}
```

**解：**
时间复杂度 = 最佳情况下为 `O(1)`，最差情况下为 `O(n)`。

**解释：**
这个程序包含 `if` 和 `else` 条件。因此，时间复杂性有两种可能性。如果 `n` 的值小于 5，那么我们只得到 `GeeksforGeeks` 作为输出，其时间复杂度为 `O(1)`。
但是，如果 `n >= 5`，则 `for` 循环将执行，时间复杂度变为 `O(n)`，这被认为是最坏的情况，因为它需要更多的时间。

## 3. 以下代码的时间复杂度是多少

```cpp
void fun(int a, int b)
{
    while (a != b) {
        if (a > b)
            a = a - b;
        else
            b = b - a;
    }
}
```

**解：**
时间复杂度 = 最佳情况下 `O(1)`，最差情况下 `O(max(a, b))`。

**解释：**
如果 `a` 和 `b` 的值相同，则不会执行 `while` 循环。因此，时间复杂度将为 `O(1)`。
但是如果 `a != b`，则将执行 `while` 循环。设 `a=16`，`b = 5`；

| **迭代次数** | **a** | **b** |
| :--- | :--- | :--- |
| 1 | 16 | 5 |
| 2 | 16-5=11 | 5 |
| 3 | 11-5=6 | 5 |
| 4 | 6-5=1 | 5 |
| 5 | 1 | 5-1=4 |
| 6 | 1 | 4-1=3 |
| 7 | 1 | 3-1=2 |
| 8 | 1 | 2-1=1 |

对于这种情况，`while` 循环执行了 8 次 (`a/2 = 16/2 = 8`)。
如果 `a=5`，`b=16`，那么循环也将执行 8 次。所以我们可以说时间复杂度是 `O(max(a/2, b/2)) = O(max(a, b))`，因为耗时比较多，所以被认为是最坏的情况。

## 4. 以下代码的时间复杂度是多少

```cpp
void fun(int n)
{
  for(int i=0; i*i<n; i++)
    cout<<"GeeksforGeeks";
}
```

**解：**
时间复杂度 = `O(√n)`。

**解释：**
让 `k` 成为循环的迭代次数。

| **i** | **i*i** |
| :--- | :--- |
| 1 | 1 |
| 2 | 2^2 |
| 3 | 3^2 |
| 4 | 4^2 |
| … | … |
| k | k^2 |

当 `i * i >= n` 即 `i * i = n`
`i * i = n`
`k^2 = n`
`k = √n`
时循环停止，因此时间复杂度为 `O(√n)`。

## 5. 以下代码的时间复杂度是多少

```cpp
void fun(int n, int x)
{
    for (int i = 1; i < n; i = i * x) //or for(int i = n; i >=1; i = i / x)
        cout << "GeeksforGeeks";
}
```

**解：**
时间复杂度 = `O(log_x n)`。

**解释：**
让 `k` 成为循环的迭代次数。

| **itr 数量** | **i=i*x** |
| :--- | :--- |
| 1 | 1*x=x |
| 2 | x*x=x^2 |
| 3 | x^2 *x=x^3 |
| … | … |
| k | x^{k-1} *x= x^k |

当 `i >= n`
`x^k = n`
`x^k = n` (两边取对数)
`k = log_x n`
时循环将停止。因此，时间复杂度为 `O(log_x n)`。

## 6. 以下代码的时间复杂度是多少

```cpp
void fun(int n)
{
    for (int i = 0; i < n / 2; i++)
        for (int j = 1; j + n / 2 <= n; j++)
            for (int k = 1; k <= n; k = k * 2)
                cout << "GeeksforGeeks";
}
```

**解：**
时间复杂度 = `O(n^2 log_2 n)`。

**解释：**
第 1 个循环的时间复杂度为 `O(n/2) = O(n)`。
第 2 个循环的时间复杂度 = `O(n/2) = O(n)`。
第 3 个循环的时间复杂度 = `O(log_2 n)`。（参考问题 5）
因此，函数的时间复杂度将变为 `O(n^2 log_2 n)`。

## 7. 以下代码的时间复杂度是多少

```cpp
void fun(int n)
{
    for (int i = 1; i <= n; i++)
        for (int j = 1; j <= n; j = j + i)
            cout << "GeeksforGeeks";
}
```

**解：** 时间复杂度 = `O(n log n)`。

**解释：**
循环 1 的时间复杂度 = `O(n)`。
第 2 个循环对 `i` 的每个值执行 `n/i` 次，其时间复杂度为 `O(∑_{i=1}^{n} n/i) = O(log n)`。
因此，函数的时间复杂度 = `O(n log n)`。

## 8. 以下代码的时间复杂度是多少

```cpp
void fun(int n)
{
    for (int i = 0; i <= n / 3; i++)
        for (int j = 1; j <= n; j = j + 4)
            cout << "GeeksforGeeks";
}
```

**解：** 时间复杂度 = `O(n^2)`。

**解释：**
第一个 `for` 循环的时间复杂度 = `O(n/3) = O(n)`。
第二个 `for` 循环的时间复杂度 = `O(n/4) = O(n)`。
因此，函数的时间复杂度将变为 `O(n^2)`。

## 9. 以下代码的时间复杂度是多少

```cpp
void fun(int n)
{
    int i = 1;
    while (i < n) {
        int j = n;
        while (j > 0) {
            j = j / 2;
        }
        i = i * 2;
    }
}
```

**解：** 时间复杂度 = `O(log^2 n)`。

**解释：**
在每次迭代中，`i` 变成两倍 (T.C=`O(log n)`)，`j` 变成一半 (T.C=`O(log n)`)。所以，时间复杂度会变成 `O(log^2 n)`。
我们可以把这个 `while` 循环转换成 `for` 循环。
`for(int i = 1; i<n; i = i * 2)`
`for(int j = n; j>0; j = j / 2)`。
以上 `for` 循环的时间复杂度也是 `O(log^2 n)`。

## 10. 考虑下面的 C 代码，在循环的执行中进行了多少次比较？

```cpp
void fun(int n)
{
    int j = 1;
    while (j <= n) {
        j = j * 2;
    }
}
```

**解：** `ceil(log_2 n) + 1`。

**解释：**
让 `k` 成为循环的迭代次数。第 `k` 步后，`j` 的值为 `2^k`。因此，`k = log_2 n`，这里我们用 `log_2 n` 的 `ceil`，因为 `log_2 n` 可能是小数。因为我们要为退出循环再做一次比较。
那么，答案是 `ceil(log_2 n) + 1`。