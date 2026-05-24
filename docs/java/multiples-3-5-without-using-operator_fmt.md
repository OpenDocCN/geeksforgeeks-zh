# 不使用%运算符的3和5的倍数

> 原文：[https://www.geeksforgeeks.org/multiples-3-5-without-using-operator/](https://www.geeksforgeeks.org/multiples-3-5-without-using-operator/)

写一个短程序，在新的一行上打印从1到n的每个数字。

1.  对于3的每个倍数，打印“Multiple of 3”而不是数字。
2.  对于每个5的倍数，打印“Multiple of 5”而不是数字。
3.  对于3和5的倍数的数字，打印“Multiple of 3. Multiple of 5.”而不是数字。

**例：**

```
Input  : 15 
Output : 1

         Multiple of 3.

         Multiple of 5.
         Multiple of 3.

         Multiple of 3.
         Multiple of 5.

         Multiple of 3.

         Multiple of 3. Multiple of 5.
```

这个想法是从1迭代到n，并通过将3和5加到当前倍数来跟踪3和5的倍数。如果当前数字与倍数匹配，我们会相应地更新输出。

## C++

```cpp
// C++ program to print multiples
// of 3 and 5 without using % operator.
#include <iostream>
using namespace std;

void findMultiples(int n)
{
    int a = 3; // To keep track of multiples of 3
    int b = 5; // To keep track of multiples of 5
    for (int i = 1; i <= n; i++)
    {
        string s = "";

        // Found multiple of 3
        if (i == a)
        {
            a = a + 3; // Update next multiple of 3
            s = s + "Multiple of 3. ";
        }

        // Found multiple of 5
        if (i == b)
        {
            b = b + 5; // Update next multiple of 5
            s = s + "Multiple of 5.";
        }

        if (s == "")
            cout << (i) << endl;
        else
        cout << (s) << endl;
    }
}

// Driver Code
int main()
{
    findMultiples(20);

    return 0;
}

// This code is contributed
// by Sach_Code
```

## Java

```java
// Java program to print multiples of 3 and
// 5 without using % operator.
import java.io.*;

class GFG
{
    static void findMultiples(int n)
    {
        int a = 3;  // To keep track of multiples of 3
        int b = 5;  // To keep track of multiples of 5
        for (int i=1; i<=n; i++)
        {
            String s = "";

            // Found multiple of 3
            if (i==a)
            {
                a = a + 3;  // Update next multiple of 3
                s = s + "Multiple of 3. ";
            }

            // Found multiple of 5
            if (i==b)
            {
                b = b+5;  // Update next multiple of 5
                s = s + "Multiple of 5.";
            }

            if (s == "")
                System.out.println(i);
            else  System.out.println(s);
        }
    }

    public static void main (String[] args)
    {
        findMultiples(20);
    }
}
```

## C\#

```csharp
// C# program to print multiples of 3 and
// 5 without using % operator.
using System;

public class GFG {

    static void findMultiples(int n)
    {

        // To keep track of multiples of 3
        int a = 3;

        // To keep track of multiples of 5
        int b = 5;
        for (int i = 1; i <= n; i++)
        {
            String s = "";

            // Found multiple of 3
            if (i == a)
            {

                // Update next multiple of 3
                a = a + 3;
                s = s + "Multiple of 3. ";
            }

            // Found multiple of 5
            if (i == b)
            {

                // Update next multiple of 5
                b = b + 5;
                s = s + "Multiple of 5.";
            }

            if (s == "")
                Console.WriteLine(i);
            else
                Console.WriteLine(s);
        }
    }

    // Driver code
    public static void Main ()
    {
        findMultiples(20);
    }
}

// This code is contributed by Sam007.
```

## PHP

```php
<?php
// PHP program to print multiples
// of 3 and 5 without using % operator.

function findMultiples($n)
{
    $a = 3; // To keep track of multiples of 3
    $b = 5; // To keep track of multiples of 5
    for ($i = 1; $i <= $n; $i++)
    {
        $s = "";

        // Found multiple of 3
        if ($i == $a)
        {
            $a = $a + 3; // Update next multiple of 3
            $s = $s . "Multiple of 3. ";
        }

        // Found multiple of 5
        if ($i == $b)
        {
            $b = $b + 5; // Update next multiple of 5
            $s = $s . "Multiple of 5.";
        }

        if ($s == "")
            echo ($i). "\n";
        else
            echo ($s). "\n";
    }
}

// Driver Code
findMultiples(20);

// This code is contributed
// by Akanksha Rai(Abby_akku)
```

## JavaScript

```javascript
<script>

// JavaScript program for the above approach

    function findMultiples(n)
    {
        let a = 3;  // To keep track of multiples of 3
        let b = 5;  // To keep track of multiples of 5
        for (let i=1; i<=n; i++)
        {
            let s = "";

            // Found multiple of 3
            if (i==a)
            {
                a = a + 3;  // Update next multiple of 3
                s = s + "Multiple of 3. ";
            }

            // Found multiple of 5
            if (i==b)
            {
                b = b+5;  // Update next multiple of 5
                s = s + "Multiple of 5.";
            }

            if (s == "") {
                document.write(i);
                document.write("<br />");
             }
            else {
                document.write(s);
                document.write("<br />");
            }
        }
    }

// Driver Code
    findMultiples(20);

   // This code is contributed by susmitakundugoaldanga.
</script>
```

## Python 3

```python
# Python 3 program to print multiples
# of 3 and 5 without using % operator.

def findMultiples(n):
    a = 3 # To keep track of multiples of 3
    b = 5 # To keep track of multiples of 5
    for i in range(1,n+1):
        s = ""

        # Found multiple of 3
        if (i == a):
            a = a + 3 # Update next multiple of 3
            s = s + "Multiple of 3. "

        # Found multiple of 5
        if (i == b):
            b = b + 5 # Update next multiple of 5
            s = s + "Multiple of 5."
        if (s == ""):
            print(i)
        else:
            print(s) 

# Driver Code
if __name__ == '__main__':
    findMultiples(20)
```

**输出：**

```
Multiple of 3. 

Multiple of 5.
Multiple of 3. 

Multiple of 3. 
Multiple of 5.

Multiple of 3. 

Multiple of 3. Multiple of 5.

Multiple of 3. 

Multiple of 5.
```

**时间复杂度：**`O(N)`
**辅助空间：**`O(1)`

本文由**Nimesh Jain**供稿。如果你喜欢GeeksforGeeks并想投稿，你也可以用[write.geeksforgeeks.org](http://www.write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到`review-team@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。