# 带幂循环的时间复杂度

> 原文：[https://www.geeksforgeeks.org/time-complexity-of-loop-with-powers/](https://www.geeksforgeeks.org/time-complexity-of-loop-with-powers/)

下面这个函数的时间复杂度是多少？

## C++

```cpp
void fun(int n, int k)
{
    for (int i = 1; i <= n; i++)
    {
        int p = pow(i, k);
        for (int j = 1; j <= p; j++)
        {
            // Some O(1) work
        }
    }
}

// This code is contributed by Shubham Singh
```

## C

```c
void fun(int n, int k)
{
    for (int i = 1; i <= n; i++)
    {
        int p = pow(i, k);
        for (int j = 1; j <= p; j++)
        {
            // Some O(1) work
        }
    }
}
```

## Java

```java
static void fun(int n, int k)
{
    for (int i = 1; i <= n; i++)
    {
        int p = Math.pow(i, k);
        for (int j = 1; j <= p; j++)
        {
            // Some O(1) work
        }
    }
}

// This code is contributed by umadevi9616
```

## Python 3

```python
def fun(n, k):

    for i in range(1, n + 1):
        p = pow(i, k)
        for j in range(1, p + 1):
            # Some O(1) work

# This code is contributed by Shubham Singh
```

## C#

```csharp
static void fun(int n, int k)
{
    for (int i = 1; i <= n; i++)
    {
        int p = Math.Pow(i, k);
        for (int j = 1; j <= p; j++)
        {
            // Some O(1) work
        }
    }
}

// This code is contributed by umadevi9616
```

## JavaScript

```javascript
// JavaScript program for the above approach
function fun(n, k)
{
    for(let i = 1; i <= n; i++)
    {
        int p = Math.pow(i, k);
        for (let j = 1; j <= p; j++)
        {
            // Some O(1) work
        }
    }
}

// This code is contributed by Shubham Singh
```

上述功能的时间复杂度可以写成 `1^k + 2^k + 3^k + ... n^k`。

让我们尝试几个例子：

```
k=1
Sum = 1 + 2 + 3 ... n 
    = n(n+1)/2 
    = n^2/2 + n/2

k=2
Sum = 1^2 + 2^2 + 3^2 + ... n^2.
    = n(n+1)(2n+1)/6
    = n^3/3 + n^2/2 + n/6

k=3
Sum = 1^3 + 2^3 + 3^3 + ... n^3.
    = n^2(n+1)^2/4
    = n^4/4 + n^3/2 + n^2/4     
```

一般来说，渐近值可以写成 `(n^(k+1))/(k+1) + θ(n^k)`。
如果 `n >= k` 那么时间复杂度将在 `O((n^(k+1))/(k+1))` 中考虑，如果 `n < k` 那么时间复杂度将在 `O(n^k)` 中考虑。

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论。