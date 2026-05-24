# 计算日志 n 的程序

> 原文:[https://www.geeksforgeeks.org/program-to-compute-log-n/](https://www.geeksforgeeks.org/program-to-compute-log-n/)

写一个计算并返回![\log_2 n                   ](img/690e35656494d8bb3d5cdf4c249a33c4.png "Rendered by QuickLaTeX.com")的单行 C 函数。例如，如果 n = 64，那么你的函数应该返回 6，如果 n = 128，那么你的函数应该返回 7。

**使用递归**

## C++

```cpp
// C++ program to find log(n) using Recursion
#include <iostream>
using namespace std;

unsigned int Log2n(unsigned int n)
{
    return (n > 1) ? 1 + Log2n(n / 2) : 0;
}

// Driver code
int main()
{
    unsigned int n = 32;
    cout << Log2n(n);
    getchar();
    return 0;
}

// This code is contributed by kirti
```

## C

```cpp
// program to find log(n) using Recursion
#include <stdio.h>

unsigned int Log2n(unsigned int n)
{
    return (n > 1) ? 1 + Log2n(n / 2) : 0;
}

int main()
{
    unsigned int n = 32;
    printf("%u", Log2n(n));
    getchar();
    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
// Java program to find log(n)
// using Recursion
class Gfg1
{

    static int Log2n(int n)
    {
        return (n > 1) ? 1 + Log2n(n / 2) : 0;
    }

    // Driver Code
    public static void main(String args[])
    {
        int n = 32;
        System.out.println(Log2n(n));
    }
}

// This code is contributed by Niraj_Pandey
```

## 蟒蛇 3

```cpp
# Python 3 program to
# find log(n) using Recursion

def Log2n(n):

    return 1 + Log2n(n / 2) if (n > 1) else 0

# Driver code
n = 32
print(Log2n(n))

# This code is contributed by
# Smitha Dinesh Semwal
```

## C#

```cpp
// C# program to find log(n)
// using Recursion
using System;

class GFG {

    static int Log2n(int n)
    {
        return (n > 1) ? 1 +
            Log2n(n / 2) : 0;
    }

    // Driver Code
    public static void Main()
    {
        int n = 32;

        Console.Write(Log2n(n));
    }
}

// This code is contributed by
// nitin mittal.
```

## java 描述语言

```cpp
<script>
// program to find log(n) using Recursion

 function  Log2n( n)
{
    return (n > 1) ? 1 + Log2n(n / 2) : 0;
}

     n = 32;
    document.write( Log2n(n));
   //This code is contributed by simranarora5sos
</script>
```

**输出:**

```cpp
5
```

**时间复杂度:**O(log n)
T3】辅助空间: O(log n)如果在递归过程中考虑了堆栈大小，否则为 O(1)

**使用内置日志功能**

我们可以使用标准库中可用的内置功能。

## C++

```cpp
// C++ program to find log(n) using Inbuilt
#include <bits/stdc++.h>
using namespace std;

int main()
{
    unsigned int n = 32;
    cout << (log(32) / log(2));
    return 0;
}

// This code is contributed by UJJWAL BHARDWAJ
```

## C

```cpp
// C program to find log(n) using Inbuilt
// function of <math.h> library
#include <math.h>
#include <stdio.h>
int main()
{
    unsigned int n = 32;
    printf("%d", (int)log2(n));
    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
// Java program to find log(n) using Inbuilt
// function of java.util.Math library
import java.util.*;

class Gfg2
{
    public static void main(String args[])
    {
        int n = 32;
        System.out.println((int)(Math.log(n) / Math.log(2)));
    }
}

// This code is contributed by Niraj_Pandey
```

## 蟒蛇 3

```cpp
# Python3 program to find log(n) using Inbuilt

# Function of math library
import math

if __name__ == "__main__":
    n = 32

    print(int(math.log(n, 2)))

# This code is contributed by ukasp
```

## C#

```cpp
// C# program to find log(n) using Inbuilt
// function
using System;

class GFG{

static public void Main()
{
    int n = 32;
    Console.WriteLine((int)(Math.Log(n) / Math.Log(2)));
}
}

// This code is contributed by Ankita Saini
```

## java 描述语言

```cpp
<script>
//program to find log(n) using Inbuilt
// function of <math.h> library

     n = 32;
     document.write(  Math.log2(n));
//This code is contributed by simranarora5sos
</script>
```

**输出:**

```cpp
5
```

**时间复杂度:**O(1)
T3】辅助空间: O(1)

**让我们来试试这个问题的扩展版本。**

写一个返回![\lfloor\log_r n\rfloor                       ](img/caa15d3816f11c80a857cd3e16baa900.png "Rendered by QuickLaTeX.com")的单行函数 Logn(n，r)。

**使用递归**

## C++

```cpp
// C++ program to find log(n) on arbitrary
// base using Recursion
#include <bits/stdc++.h>
using namespace std;

unsigned int Logn(unsigned int n,
                  unsigned int r)
{
    return (n > r - 1) ? 1 +
       Logn(n / r, r) : 0;
}

// Driver code
int main()
{
    unsigned int n = 256;
    unsigned int r = 3;

    cout << Logn(n, r);

    return 0;
}

// This code is contributed by UJJWAL BHARDWAJ
```

## C

```cpp
// C program to find log(n) on arbitrary base using Recursion
#include <stdio.h>

unsigned int Logn(unsigned int n, unsigned int r)
{
    return (n > r - 1) ? 1 + Logn(n / r, r) : 0;
}

int main()
{
    unsigned int n = 256;
    unsigned int r = 3;
    printf("%u", Logn(n, r));
    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
// Java program to find log(n) on
// arbitrary base using Recursion
class Gfg3
{
    static int Logn(int n, int r)
    {
        return (n > r - 1) ? 1 + Logn(n / r, r) : 0;
    }

    // Driver Code
    public static void main(String args[])
    {
        int n = 256;
        int r = 3;
        System.out.println(Logn(n, r));
    }
}

// This code is contributed by Niraj_Pandey
```

## 蟒蛇 3

```cpp
# Python program to find log(n) on arbitrary
# base using Recursion
def Logn(n, r):

    return  1 + Logn(n / r, r) if (n > r - 1) else 0

# Driver code
n = 256
r = 3
print(Logn(n, r))

# This code is contributed by shivanisinghss2110
```

## C#

```cpp
// C# program to find log(n) on
// arbitrary base using Recursion
using System;

public class Gfg3
{
    static int Logn(int n, int r)
    {
        return (n > r - 1) ? 1 + Logn(n / r, r) : 0;
    }

    // Driver Code
    public static void Main(String []args)
    {
        int n = 256;
        int r = 3;
        Console.WriteLine(Logn(n, r));
    }
}

// This code is contributed by gauravrajput1
```

## java 描述语言

```cpp
<script>
//program to find log(n) on arbitrary base using Recursion

   function Logn( n,  r)
{
    return (n > r - 1) ? 1 + Logn(n / r, r) : 0;
}

     n = 256;
     r = 3;
    document.write( Logn(n, r));
//This code is contributed by simranarora5sos
</script>
```

**输出:**

```cpp
5
```

**时间复杂度:**O(log n)
T3】辅助空间: O(log n)如果在递归过程中考虑了堆栈大小，否则为 O(1)

**使用内置日志功能**

我们只需要用对数性质来求任意基数 **r** 上 log(n)的值。即![\log_r n = \dfrac{log_k (n)}{\log_k (r)}                    ](img/e53cf48d881751a5abae53f8982e1902.png "Rendered by QuickLaTeX.com")，其中 **k** 可以是任何东西，对于标准日志功能，可以是 **e** 或 **10**

## C++

```cpp
// C++ program to find log(n) on arbitrary base
// using log() library function
#include <bits/stdc++.h>
using namespace std;

unsigned int Logn(unsigned int n,
                  unsigned int r)
{
    return log(n) / log(r);
}

// Driver code
int main()
{
    unsigned int n = 256;
    unsigned int r = 3;

    cout << Logn(n, r);

    return 0;
}

// This code is contributed by UJJWAL BHARDWAJ
```

## C

```cpp
// C program to find log(n) on arbitrary base
// using log() function of maths library
#include <math.h>
#include <stdio.h>

unsigned int Logn(unsigned int n, unsigned int r)
{
    return log(n) / log(r);
}

int main()
{
    unsigned int n = 256;
    unsigned int r = 3;
    printf("%u", Logn(n, r));

    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
// Java program to find log(n) on arbitrary base
// using log() function of java.util.Math library
import java.util.*;

class Gfg4 {

    public static void main(String args[])
    {
        int n = 256;
        int r = 3;
        System.out.println((int)(Math.log(n) / Math.log(r)));
    }
}

// This code is contributed by Niraj_Pandey
```

## 蟒蛇 3

```cpp
# Python program to find log(n) on arbitrary base
# using log() library function
import math
def Logn(n, r):

    return math.log(n) // math.log(r)

n = 256
r = 3
print(int(Logn(n, r)))

# This code is contributed by shivanisinghss2110
```

## C#

```cpp
// C# program to find log(n) on arbitrary base
// using log() function of java.util.Math library
using System;

class Gfg4 {

    public static void Main(String []args)
    {
        int n = 256;
        int r = 3;
        Console.Write((int)(Math.Log(n) / Math.Log(r)));
    }
}

// This code is contributed by shivanisinghss2110
```

## java 描述语言

```cpp
<script>
// program to find log(n) on arbitrary base
// using log() function of maths library

   function  Logn( n, r)
{
    return Math.floor(Math.log(n) / Math.log(r));
}

    n = 256;
    r = 3;
    document.write( Logn(n, r));
//This code is contributed by simranarora5sos
</script>
```

**输出:**

```cpp
5
```

**时间复杂度:**O(1)
T3】辅助空间: O(1)

本文由 [Shubham Bansal](https://www.quora.com/profile/Shubham-Bansal-209) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。