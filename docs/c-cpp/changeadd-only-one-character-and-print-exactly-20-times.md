# 仅更改/添加一个字符，精确打印“*”20 次

> 原文:[https://www . geesforgeks . org/change add-仅一个字符并精确打印 20 次/](https://www.geeksforgeeks.org/changeadd-only-one-character-and-print-exactly-20-times/)

在下面的代码中，只更改/添加一个字符，并精确地打印 20 次' * '。

```cpp
int main()
{
    int i, n = 20;
    for (i = 0; i < n; i--)
        printf("*");             
    getchar();
    return 0;
}
```

**解决方案:**
**1。在循环的第三个表达式中用 n 替换 I**

## C++

```cpp
#include <iostream>
using namespace std;
int main()
{
    int i, n = 20;
    for (i = 0; i < n; n--)
        cout << "*";
    getchar();
    return 0;
}
```

## C

```cpp
#include <stdio.h>
int main()
{
    int i, n = 20;
    for (i = 0; i < n; n--)
        printf("*");
    getchar();   
    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
// Java code
class GfG {
public static void main(String[] args)
{
    int i, n = 20;
    for (i = 0; i < n; n--)
        System.out.print("*");
}
}
```

## 蟒蛇 3

```cpp
# Python3 program to implement 
# the above approach
if __name__ == '__main__':
  n = 20;
  for i in range(0, n):
    print("*"); n -= 1;

# This code is contributed by gauravrajput1
```

## C#

```cpp
// C# code
using System;
class GfG
{
    public static void Main()
    {
        int i, n = 20;
        for (i = 0; i < n; n--)
            Console.Write("*");
    }
}

// This code is contributed by SoumikMondal
```

## java 描述语言

```cpp
<script>

// Javascript code
var i, n = 20;
for(i = 0; i < n; n--)
    document.write("*");

// This code is contributed by Ankita Saini

</script>
```

**2。在我输入 loop 的第二个表达式**T2 之前输入'-'

## C++

```cpp
#include<bits/stdc++.h>
using namespace std;

int main()
{
    int i, n = 20;
    for (i = 0; -i < n; i--)
        cout<<"*";          

    return 0;
}

// This code is contributed by rutvik_56.
```

## C

```cpp
#include <stdio.h>
int main()
{
    int i, n = 20;
    for (i = 0; -i < n; i--)
        printf("*");          
    getchar();   
    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
// Java code
import java.util.*;
public class GFG
{
  public static void main(String[] args)
  {
    int i, n = 20;
    for (i = 0; -i < n; i--)
      System.out.print("*");
  }
}

// This code is contributed by divyesh072019.
```

## 蟒蛇 3

```cpp
# Python3 program to implement 
# the above approach
if __name__ == '__main__':
  n = 20
  for i in range(0,n):
    print("*", end="")

# This code is contributed by shivanisinghss2110
```

## C#

```cpp
// C# code
using System;
class GfG
{
    public static void Main()
    {
        int i, n = 20;
        for (i = 0; -i < n; i--)
            Console.Write("*");
    }
}

// This code is contributed by divyeshrabadiya07.
```

## java 描述语言

```cpp
<script>

let i, n = 20;
for (i = 0; -i < n; i--)
      document.write("*");

// This code is contributed by patel2127
</script>
```

**3。将循环的第二个表达式**中的<替换为+ in

## C++

```cpp
#include <iostream>
using namespace std;

int main()
{
    int i, n = 20;
    for(i = 0; i + n; i--)
        cout << "*";

    return 0;
}

// This code is contributed by shivani
```

## C

```cpp
#include <stdio.h>
int main()
{
    int i, n = 20;
    for (i = 0; i + n; i--)
       printf("*");
    getchar();
    return 0;
}
```

## java 描述语言

```cpp
<script>

let i, n = 20;

for(i = 0; i + n; i--)
        document.write("*");

// This code is contributed by unknown2108
</script>
```

**我们把问题稍微延伸一下。**
仅更改/添加一个字符，并精确打印 21 次“*”。
解决方法:将否定运算符放在 I 之前，用于循环的第二个表达式。
解释:否定运算符将数字转换为其补码。

```cpp
       No.              One's complement
 0 (00000..00)            -1 (1111..11)                         
-1 (11..1111)             0 (00..0000)                        
-2 (11..1110)             1 (00..0001)                            
-3 (11..1101)             2 (00..0010)
...............................................
-20 (11..01100)           19 (00..10011)
```

## C++

```cpp
// C++ program for the above approach
#include <iostream>
using namespace std;

int main()
{
    int i, n = 20;
    for (i = 0; ~i < n; i--)
        printf("*");
    getchar();
    return 0;
}

// This code is contributed by shivanisinghss2110
```

## C

```cpp
#include <stdio.h>
int main()
{
    int i, n = 20;
    for (i = 0; ~i < n; i--)
        printf("*");
    getchar();
    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
// Java program for the above approach
import java.util.*;

class GFG{

public static void main(String[] args)
{
    int i, n = 20;
    for(i = 0; ~i < n; i--)
        System.out.print( "*" );
}
}

// This code is contributed by shivani
```

## C#

```cpp
// C# program for the above approach
using System;

class GFG{

public static void Main(String[] args)
{
    int i, n = 20;
    for(i = 0; ~i < n; i--)
        Console.Write( "*" );
}
}

// This code is contributed by shivanisinghss2110
```

## java 描述语言

```cpp
<script>

// JavaScript program for the above approach
{
    var i, n = 20;
    for(i = 0; ~i < n; i--)
        document.write("*");
}

// This code is contributed by shivanisinghss2110

</script>
```

如果你发现以上问题有更多的解决方法，请评论。