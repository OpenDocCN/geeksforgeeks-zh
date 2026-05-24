# 求数列的前 N 项之和 2×3 + 4×4 + 6×5 + 8×6 + …

> 原文: [https://www.geeksforgeeks.org/find-the-sum-of-first-n-terms-of-the-series-2x3-4x4-6x5-8x6/](https://www.geeksforgeeks.org/find-the-sum-of-first-n-terms-of-the-series-2x3-4x4-6x5-8x6/)

给定一个整数 `N`。任务是找到给定系列的`总和`到 `N` 项:
> 2×3 + 4×4 + 6×5 + 8×6 + …

**例:**
```
Input : N = 5
Output : Sum = 170

Input : N = 10
Output : Sum = 990
```

让该系列的第 N 个`术语`为 `t_N`。
`t_1 = 2×3 = (2×1)(1+2)`
`t_2 = 4×4 = (2×2)(2+2)`
`t_3 = 6×5 = (2×3)(3+2)`
`t_4 = 8×6 = (2×4)(4+2)`
。
。
。
`t_N = (2×N)(N+2)`
级数 N 项之和，

```
Sn = t1 + t2 +... + tn
=
=
=
=
=
=
=
```

以下是上述方法的实现:

## C++

```cpp
// C++ program to find sum upto
// N term of the series:
// 2 × 3 + 4 × 4 + 6 × 5 + 8 × 6 + ...
#include<iostream>
using namespace std;

// calculate sum upto N term of series
void Sum_upto_nth_Term(int n)
{
    int r = n * (n + 1) *
                (2 * n + 7) / 3;
    cout << r;
}

// Driver code
int main()
{
    int N = 5;
    Sum_upto_nth_Term(N) ;
    return 0;
}
```

## Java

```java
// Java program to find sum upto
// N term of the series:

import java.io.*;

class GFG {
// calculate sum upto N term of series
static void Sum_upto_nth_Term(int n)
{
    int r = n * (n + 1) *
                (2 * n + 7) / 3;
    System.out.println(r);
}

// Driver code
    public static void main (String[] args) {
    int N = 5;
    Sum_upto_nth_Term(N);
    }
}
```

## Python 3

```python
# Python program to find sum upto N term of the series:
# 2 × 3 + 4 × 4 + 6 × 5 + 8 × 6 + ...

# calculate sum upto N term of series
def Sum_upto_nth_Term(n):
    return n * (n + 1) * (2 * n + 7) // 3

# Driver code
N = 5
print(Sum_upto_nth_Term(N))
```

## C#

```csharp
// C# program to find sum upto
// N term of the series:
// 2 × 3 + 4 × 4 + 6 × 5 + 8 × 6 + ...

using System;

class GFG
{
// calculate sum upto N term of series
static void Sum_upto_nth_Term(int n)
{
    int r = n * (n + 1) *
                (2 * n + 7) / 3;
    Console.Write(r);
}

// Driver code
public static void Main()
{
    int N = 5;
    Sum_upto_nth_Term(N);
}
}

// This code is contributed
// by Akanksha Rai(Abby_akku)
```

## PHP

```php
<?php
// PHP program to find sum upto
// N term of the series:
// 2 × 3 + 4 × 4 + 6 × 5 + 8 × 6 + ...
function Sum_upto_nth_Term($n)
{
    $r = $n * ($n + 1) *
              (2 * $n + 7) / 3;
    echo $r;
}

// Driver code
$N = 5;
Sum_upto_nth_Term($N);

// This code is contributed
// by Shashank_Sharma
?>
```

## JavaScript

```javascript
<script>

// Javascript program to find sum upto
// N term of the series:
// 2 × 3 + 4 × 4 + 6 × 5 + 8 × 6 + ...

// calculate sum upto N term of series
function Sum_upto_nth_Term(n)
{
    let r = n * (n + 1) *
                (2 * n + 7) / 3;
    document.write(r);
}

// Driver code

    let N = 5;
    Sum_upto_nth_Term(N) ;

// This code is contributed by Mayank Tyagi

</script>
```

**Output:**

```