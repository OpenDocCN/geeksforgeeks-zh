# 二维路径中从源到目的地的固定大小跳跃

> 原文：[https://www.geeksforgeeks.org/source-to-destination-in-2-d-path-with-fixed-sized-jumps/](https://www.geeksforgeeks.org/source-to-destination-in-2-d-path-with-fixed-sized-jumps/)

给定路径的源点和目的点以及两个整数 `x` 和 `y`。任务是检查是否可以用下面的移动从源移动到目的地，如果当前位置是 `(a, b)`，那么有效的移动是：

1.  `(a + x, b + y)`
2.  `(a - x, b + y)`
3.  `(a + x, b - y)`
4.  `(a - x, b - y)`

**示例：**

> **输入：** `Sx = 0, Sy = 0, Dx = 0, Dy = 6, x = 2, y = 3`
> **输出：** 是
> `(0, 0) -> (2, 3) -> (0, 6)`
>
> **输入：** `Sx = 1, Sy = 1, Dx = 3, Dy = 6, x = 1, y = 5`
> **输出：** 否

**处理方式：** 我们来处理这个问题，就好像步骤是 `(a, b) -> (a + x, 0)` 或 `(a, b) -> (a - x, 0)` 或 `(a, b) -> (0, b + y)` 或 `(a, b) -> (0, b - y)`。那么如果 `|Sx - Dx| mod x = 0` 和 `|Sy - Dy| mod y = 0`，答案就是 `是`。
很容易看出，如果这个问题的答案是否定的，那么原问题的答案也是否定的。
让我们回到原问题，看看一些步骤的顺序。在某一点 `(x_e, y_e)` 结束。将 `cnt_x` 定义为 `|x_e - Sx| / x`，`cnt_y` 定义为 `|y_e - Sy| / y`。`cnt_x` 的奇偶性与 `cnt_y` 的奇偶性相同，因为每种类型的移动都会改变 `cnt_x` 和 `cnt_y` 的奇偶性。
那么答案是 `是` 如果 `|Sx - Dx| mod x = 0`、`|Sy - Dy| mod y = 0` 和 `|Sx - Dx| / x mod 2 = |Sy - Dy| / y mod 2`。

下面是上述方法的实现。

## C++

```cpp
// C++ implementation of the approach
#include <bits/stdc++.h>
using namespace std;

// Function that returns true if
// it is possible to move from source
// to the destination with the given moves
bool isPossible(int Sx, int Sy, int Dx, int Dy, int x, int y)
{
    if (abs(Sx - Dx) % x == 0
        and abs(Sy - Dy) % y == 0
        and (abs(Sx - Dx) / x) % 2 == (abs(Sy - Dy) / y) % 2)
        return true;

    return false;
}

// Driver code
int main()
{
    int Sx = 0, Sy = 0, Dx = 0, Dy = 0;
    int x = 3, y = 4;

    if (isPossible(Sx, Sy, Dx, Dy, x, y))
        cout << "Yes";
    else
        cout << "No";

    return 0;
}
```

## Java

```java
// Java implementation of the approach
import java.io.*;

class GFG
{

// Function that returns true if
// it is possible to move from source
// to the destination with the given moves
static boolean isPossible(int Sx, int Sy, int Dx,
                          int Dy, int x, int y)
{
    if (Math.abs(Sx - Dx) % x == 0 &&
        Math.abs(Sy - Dy) % y == 0 &&
       (Math.abs(Sx - Dx) / x) % 2 ==
       (Math.abs(Sy - Dy) / y) % 2)
        return true;

    return false;
}

// Driver code
public static void main(String[] args)
{
    int Sx = 0, Sy = 0, Dx = 0, Dy = 0;
    int x = 3, y = 4;

    if (isPossible(Sx, Sy, Dx, Dy, x, y))
        System.out.println("Yes");
    else
        System.out.println("No");
}
}

// This code is contributed by inder_verma..
```

## Python 3

```python
# Python3 implementation of the approach

# Function that returns true if it is
# possible to move from source to the
# destination with the given moves
def isPossible(Sx, Sy, Dx, Dy, x, y):
    if (abs(Sx - Dx) % x == 0 and
        abs(Sy - Dy) % y == 0 and
       (abs(Sx - Dx) / x) % 2 ==
       (abs(Sy - Dy) / y) % 2):
        return True;
    return False;

# Driver code
Sx = 0;
Sy = 0;
Dx = 0;
Dy = 0;
x = 3;
y = 4;

if (isPossible(Sx, Sy, Dx, Dy, x, y)):
    print("Yes");
else:
    print("No");

# This code is contributed by mits
```

## C#

```csharp
// C# implementation of the approach
using System;

class GFG
{

// Function that returns true if
// it is possible to move from source
// to the destination with the given moves
static bool isPossible(int Sx, int Sy, int Dx,
                        int Dy, int x, int y)
{
    if (Math.Abs(Sx - Dx) % x == 0 &&
        Math.Abs(Sy - Dy) % y == 0 &&
        (Math.Abs(Sx - Dx) / x) % 2 ==
        (Math.Abs(Sy - Dy) / y) % 2)
        return true;

    return false;
}

// Driver code
static void Main()
{
    int Sx = 0, Sy = 0, Dx = 0, Dy = 0;
    int x = 3, y = 4;

    if (isPossible(Sx, Sy, Dx, Dy, x, y))
        Console.WriteLine("Yes");
    else
        Console.WriteLine("No");
}
}

// This code is contributed by chandan_jnu
```

## PHP

```php
<?php
// PHP implementation of the approach

// Function that returns true if
// it is possible to move from source
// to the destination with the given moves
function isPossible($Sx, $Sy, $Dx,
                    $Dy, $x, $y)
{
    if (abs($Sx - $Dx) % $x == 0 &&
        abs($Sy - $Dy) % $y == 0 &&
       (abs($Sx - $Dx) / $x) % 2 ==
       (abs($Sy - $Dy) / $y) % 2)
        return true;

    return false;
}

// Driver code
$Sx = 0; $Sy = 0; $Dx = 0;
$Dy = 0; $x = 3; $y = 4;

if (isPossible($Sx, $Sy, $Dx,
               $Dy, $x, $y))
    echo("Yes");
else
    echo("No");

// This code is contributed
// by Code_Mech
?>
```

## JavaScript

```javascript
<script>

// Javascript implementation of the approach

// Function that returns true if
// it is possible to move from source
// to the destination with the given moves
function isPossible(Sx, Sy, Dx, Dy, x, y)
{
    if (Math.abs(Sx - Dx) % x == 0 &&
        Math.abs(Sy - Dy) % y == 0 &&
        (Math.abs(Sx - Dx) / x) % 2 ==
        (Math.abs(Sy - Dy) / y) % 2)
        return true;

    return false;
}

// Driver code
let Sx = 0, Sy = 0, Dx = 0, Dy = 0;
let x = 3, y = 4;

if (isPossible(Sx, Sy, Dx, Dy, x, y))
    document.write("Yes");
else
    document.write("No");

// This code is contributed by mukesh07

</script>
```

**输出：**

```
Yes
```