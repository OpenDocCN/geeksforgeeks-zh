# 从不同的三个数组中找出三个元素，使得 a + b + c = 总和

> 原文: [https://www.geeksforgeeks.org/find-three-element-from-different-three-arrays-such-that-that-a-b-c-k/](https://www.geeksforgeeks.org/find-three-element-from-different-three-arrays-such-that-that-a-b-c-k/)

给定三个整数数组和一个“和”，任务是检查是否有三个元素 `a`、`b`、`c`，使得 `a + b + c = 和`，`a`、`b` 和 `c` 属于三个不同的数组。

**示例:**

```
Input : a1[] = { 1 , 2 , 3 , 4 , 5 };
    a2[] = { 2 , 3 , 6 , 1 , 2 };
    a3[] = { 3 , 2 , 4 , 5 , 6 };  
        sum = 9
Output : Yes
1  + 2  + 6 = 9  here 1 from a1[] and 2 from
a2[] and 6 from a3[]   

Input : a1[] = { 1 , 2 , 3 , 4 , 5 };
    a2[] = { 2 , 3 , 6 , 1 , 2 };
    a3[] = { 3 , 2 , 4 , 5 , 6 };   
         sum = 20 
Output : No 
```

## 简单的方法

一种简单的方法是运行三个循环，如果找到则打印存在，否则打印不存在，则检查三个元素的总和形成等于给定数量的不同数组。

### C++

```
// C++ program to find three element
// from different three arrays such
// that a + b + c is equal to
// given sum
#include<bits/stdc++.h>
using namespace std;

// Function to check if there is
// an element from each array such
// that sum of the three elements
// is equal to given sum.
bool findTriplet(int a1[], int a2[],
                 int a3[], int n1,
                 int n2, int n3, int sum)
{
    for (int i = 0; i < n1; i++)
    for (int j = 0; j < n2; j++)
        for (int k = 0; k < n3; k++)
            if (a1[i] + a2[j] + a3[k] == sum)
            return true;

    return false;
}

// Driver Code
int main()
{
    int a1[] = { 1 , 2 , 3 , 4 , 5 };
    int a2[] = { 2 , 3 , 6 , 1 , 2 };
    int a3[] = { 3 , 2 , 4 , 5 , 6 };
    int sum = 9;
    int n1 = sizeof(a1) / sizeof(a1[0]);
    int n2 = sizeof(a2) / sizeof(a2[0]);
    int n3 = sizeof(a3) / sizeof(a3[0]);
    findTriplet(a1, a2, a3, n1, n2, n3, sum)?
                cout << "Yes" : cout << "No";
    return 0;
}
```

### Java

```
// Java program to find three element
// from different three arrays such
// that a + b + c is equal to
// given sum
class GFG
{

    // Function to check if there is
    // an element from each array such
    // that sum of the three elements
    // is equal to given sum.
    static boolean findTriplet(int a1[], int a2[],
                               int a3[], int n1,
                               int n2, int n3, int sum)
    {
        for (int i = 0; i < n1; i++)
            for (int j = 0; j < n2; j++)
                for (int k = 0; k < n3; k++)
                    if (a1[i] + a2[j] + a3[k] == sum)
                    return true;

        return false;
    }

    // Driver code
    public static void main (String[] args)
    {
        int a1[] = { 1 , 2 , 3 , 4 , 5 };
        int a2[] = { 2 , 3 , 6 , 1 , 2 };
        int a3[] = { 3 , 2 , 4 , 5 , 6 };
        int sum = 9;

        int n1 = a1.length;
        int n2 = a2.length;
        int n3 = a3.length;

        if(findTriplet(a1, a2, a3, n1, n2, n3, sum))
            System.out.print("Yes");
        else
            System.out.print("No");
    }
}

// This code is contributed by Anant Agarwal.
```

### Python 3

```
# Python3 program to find
# three element from different
# three arrays such that
# a + b + c is equal to
# given sum

# Function to check if there
# is an element from each
# array such that sum of the
# three elements is equal to
# given sum.
def findTriplet(a1, a2, a3,
                n1, n2, n3, sum):

    for i in range(0 , n1):
        for j in range(0 , n2):
            for k in range(0 , n3):
                if (a1[i] + a2[j] +
                    a3[k] == sum):
                    return True

    return False

# Driver Code
a1 = [ 1 , 2 , 3 , 4 , 5 ]
a2 = [ 2 , 3 , 6 , 1 , 2 ]
a3 = [ 3 , 2 , 4 , 5 , 6 ]
sum = 9
n1 = len(a1)
n2 = len(a2)
n3 = len(a3)
print("Yes") if findTriplet(a1, a2, a3,
                            n1, n2, n3,
                            sum) else print("No")

# This code is contributed
# by Smitha
```

### C#

```
// C# program to find three element
// from different three arrays such
// that a + b + c is equal to
// given sum
using System;

public class GFG
{

// Function to check if there is an
// element from each array such that
// sum of the three elements is
// equal to given sum.
static bool findTriplet(int []a1, int []a2,
                        int []a3, int n1,
                        int n2, int n3,
                        int sum)
{

    for (int i = 0; i < n1; i++)

        for (int j = 0; j < n2; j++)

            for (int k = 0; k < n3; k++)
            if (a1[i] + a2[j] + a3[k] == sum)
            return true;

    return false;
}

    // Driver Code
    static public void Main ()
    {
        int []a1 = {1 , 2 , 3 , 4 , 5};
        int []a2 = {2 , 3 , 6 , 1 , 2};
        int []a3 = {3 , 2 , 4 , 5 , 6};
        int sum = 9;
        int n1 = a1.Length;
        int n2 = a2.Length;
        int n3 = a3.Length;
        if(findTriplet(a1, a2, a3, n1,
                       n2, n3, sum))
        Console.WriteLine("Yes");
        else
        Console.WriteLine("No");
    }
}

// This code is contributed by vt_m.
```

### PHP

```
<?php
// PHP program to find three element
// from different three arrays such
// that a + b + c is equal to
// given sum

// Function to check if there is an
// element from each array such that
// sum of the three elements is equal
// to given sum.
function findTriplet($a1, $a2, $a3,
                     $n1, $n2, $n3,
                     $sum)
{
    for ( $i = 0; $i < $n1; $i++)
    for ( $j = 0; $j < $n2; $j++)
        for ( $k = 0; $k < $n3; $k++)
            if ($a1[$i] + $a2[$j] + $a3[$k] == $sum)
            return true;

    return false;
}

// Driver Code
$a1 = array( 1 , 2 , 3 , 4 , 5 );
$a2 = array( 2 , 3 , 6 , 1 , 2 );
$a3 = array( 3 , 2 , 4 , 5 , 6 );
$sum = 9;
$n1 = count($a1);
$n2 = count($a2);
$n3 = count($a3);
if(findTriplet($a1, $a2, $a3, $n1,
               $n2, $n3, $sum)==true)
echo "Yes" ;
else
echo "No";

// This code is contributed by anuj_67.
?>
```

### JavaScript

```
<script>

// JavaScript program to find three element
// from different three arrays such
// that a + b + c is equal to
// given sum

// Function to check if there is
// an element from each array such
// that sum of the three elements
// is equal to given sum.
function findTriplet(a1, a2, a3, n1,
                      n2, n3, sum)
{
    for (var i = 0; i < n1; i++)
    for (var j = 0; j < n2; j++)
        for (var k = 0; k < n3; k++)
            if (a1[i] + a2[j] + a3[k] == sum)
            return true;

    return false;
}

// Driver Code
var a1 = [ 1 , 2 , 3 , 4 , 5 ];
var a2 = [ 2 , 3 , 6 , 1 , 2 ];
var a3 = [ 3 , 2 , 4 , 5 , 6 ];
var sum = 9;
var n1 = a1.length;
var n2 = a2.length;
var n3 = a3.length;
findTriplet(a1, a2, a3, n1, n2, n3, sum)?
            document.write("Yes") : document.write("No");

</script>
```

**输出:**

```
Yes
```

**时间复杂度:** O(n<sup>3</sup>)
**空间复杂度:** O(1)

## 高效的解决方案

一个高效的解决方案是将第一个数组的所有元素存储在哈希表中（C++中的 `unordered_set`），然后逐个计算最后两个数组元素的两个元素之和，从给定的数字 `k` 中减去，并在哈希表中检查它是否存在于哈希表中，然后打印存在，否则不存在。

```
1. Store all elements of first array in hash table
2. Generate all pairs of elements from two arrays using
   nested loop. For every pair (a1[i], a2[j]), check if
   sum - (a1[i] + a2[j]) exists in hash table. If yes
   return true.      
```

以下是上述想法的实现。

## C++

```cpp
// C++ program to find three element
// from different three arrays such
// that a + b + c is equal to
// given sum
#include<bits/stdc++.h>
using namespace std;

// Function to check if there is
// an element from each array such
// that sum of the three elements is
// equal to given sum.
bool findTriplet(int a1[], int a2[],
                 int a3[], int n1,
                 int n2, int n3,
                 int sum)
{
    // Store elements of
    // first array in hash
    unordered_set <int> s;
    for (int i = 0; i < n1; i++)
        s.insert(a1[i]);

    // sum last two arrays
    // element one by one
    for (int i = 0; i < n2; i++)
    {
        for (int j = 0; j < n3; j++)
        {
            // Consider current pair and
            // find if there is an element
            // in a1[] such that these three
            // form a required triplet
            if (s.find(sum - a2[i] - a3[j]) !=
                                       s.end())
                return true;
        }
    }

    return false;
}

// Driver Code
int main()
{
    int a1[] = { 1 , 2 , 3 , 4 , 5 };
    int a2[] = { 2 , 3 , 6 , 1 , 2 };
    int a3[] = { 3 , 2 , 4 , 5 , 6 };
    int sum = 9;
    int n1 = sizeof(a1) / sizeof(a1[0]);
    int n2 = sizeof(a2) / sizeof(a2[0]);
    int n3 = sizeof(a3) / sizeof(a3[0]);
    findTriplet(a1, a2, a3, n1, n2, n3, sum)?
    cout << "Yes" : cout << "No";

    return 0;
}
```

## Java

```java
// Java program to find three element
// from different three arrays such
// that a + b + c is equal to
// given sum
import java.util.*;

class GFG
{

    // Function to check if there is
    // an element from each array such
    // that sum of the three elements is
    // equal to given sum.
    static boolean findTriplet(int a1[], int a2[], int a3[],
                                int n1, int n2, int n3,
                                int sum)
    {
        // Store elements of
        // first array in hash
        HashSet<Integer> s = new HashSet<Integer>();
        for (int i = 0; i < n1; i++)
        {
            s.add(a1[i]);
        }

        // sum last two arrays
        // element one by one
        ArrayList<Integer> al = new ArrayList<>(s);
        for (int i = 0; i < n2; i++)
        {
            for (int j = 0; j < n3; j++)
            {

                // Consider current pair and
                // find if there is an element
                // in a1[] such that these three
                // form a required triplet
                if (al.contains(sum - a2[i] - a3[j]) &
                            al.indexOf(sum - a2[i] - a3[j])
                            != al.get(al.size() - 1))
                {
                    return true;
                }
            }
        }
        return false;
    }

    // Driver Code
    public static void main(String[] args)
    {
        int a1[] = {1, 2, 3, 4, 5};
        int a2[] = {2, 3, 6, 1, 2};
        int a3[] = {3, 2, 4, 5, 6};
        int sum = 9;
        int n1 = a1.length;
        int n2 = a2.length;
        int n3 = a3.length;
        if (findTriplet(a1, a2, a3, n1, n2, n3, sum))
        {
            System.out.println("Yes");
        }
        else
        {
            System.out.println("No");
        }
    }
}

// This code is contributed by 29AjayKumar
```

## Python 3

```python
# Python3 program to find three element
# from different three arrays such
# that a + b + c is equal to
# given sum

# Function to check if there is
# an element from each array such
# that sum of the three elements is
# equal to given sum.
def findTriplet(a1, a2, a3,
                n1, n2, n3, sum):

    # Store elements of first
    # array in hash
    s = set()

    # sum last two arrays element
    # one by one
    for i in range(n1):
        s.add(a1[i])

    for i in range(n2):
        for j in range(n3):

            # Consider current pair and
            # find if there is an element
            # in a1[] such that these three
            # form a required triplet
            if sum - a2[i] - a3[j] in s:
                return True
    return False

# Driver code
a1 = [1, 2, 3, 4, 5]
a2 = [2, 3, 6, 1, 2]
a3 = [3, 24, 5, 6]
n1 = len(a1)
n2 = len(a2)
n3 = len(a3)
sum = 9
if findTriplet(a1, a2, a3,
               n1, n2, n3, sum) == True:
    print("Yes")
else:
    print("No")

# This code is contributed by Shrikant13
```

## C\#

```csharp
// C# program to find three element
// from different three arrays such
// that a + b + c is equal to
// given sum
using System;
using System.Collections.Generic;

class GFG
{

    // Function to check if there is
    // an element from each array such
    // that sum of the three elements is
    // equal to given sum.
    static bool findTriplet(int []a1, int []a2, int []a3,
                                int n1, int n2, int n3,
                                int sum)
    {
        // Store elements of
        // first array in hash
        HashSet<int> s = new HashSet<int>();
        for (int i = 0; i < n1; i++)
        {
            s.Add(a1[i]);
        }

        // sum last two arrays
        // element one by one
        List<int> al = new List<int>(s);
        for (int i = 0; i < n2; i++)
        {
            for (int j = 0; j < n3; j++)
            {

                // Consider current pair and
                // find if there is an element
                // in a1[] such that these three
                // form a required triplet
                if (al.Contains(sum - a2[i] - a3[j]) &
                            al.IndexOf(sum - a2[i] - a3[j])
                            != al[al.Count - 1])
                {
                    return true;
                }
            }
        }
        return false;
    }

    // Driver Code
    public static void Main(String[] args)
    {
        int []a1 = {1, 2, 3, 4, 5};
        int []a2 = {2, 3, 6, 1, 2};
        int []a3 = {3, 2, 4, 5, 6};
        int sum = 9;
        int n1 = a1.Length;
        int n2 = a2.Length;
        int n3 = a3.Length;
        if (findTriplet(a1, a2, a3, n1, n2, n3, sum))
        {
            Console.WriteLine("Yes");
        }
        else
        {
            Console.WriteLine("No");
        }
    }
}

// This code is contributed by PrinciRaj1992
```

## JavaScript

```javascript
<script>

// Javascript program to find three element
// from different three arrays such
// that a + b + c is equal to
// given sum

// Function to check if there is
// an element from each array such
// that sum of the three elements is
// equal to given sum.
function findTriplet(a1, a2, a3, n1, n2, n3, sum)
{

    // Store elements of
    // first array in hash
    var s = new Set();
    for (var i = 0; i < n1; i++)
        s.add(a1[i]);

    // sum last two arrays
    // element one by one
    for (var i = 0; i < n2; i++)
    {
        for (var j = 0; j < n3; j++)
        {
            // Consider current pair and
            // find if there is an element
            // in a1[] such that these three
            // form a required triplet
            if (s.has(sum - a2[i] - a3[j]))
                return true;
        }
    }

    return false;
}

// Driver Code
var a1 = [1 , 2 , 3 , 4 , 5];
var a2 = [2 , 3 , 6 , 1 , 2];
var a3 = [3 , 2 , 4 , 5 , 6];
var sum = 9;
var n1 = a1.length;
var n2 = a2.length;
var n3 = a3.length;
findTriplet(a1, a2, a3, n1, n2, n3, sum)?
document.write( "Yes" ): document.write( "No");

// This code is contributed by famously.
</script>
```

**输出:**

```
Yes
```

**时间复杂度:** O(n<sup>2</sup>)
**辅助空间:** O(n)

**参考文献:**
[http://stackoverflow.com/questions/2070359/finding-three-elements-in-an-array-whose-sum-is-closest-to-a-given-number](http://stackoverflow.com/questions/2070359/finding-three-elements-in-an-array-whose-sum-is-closest-to-a-given-number)

本文由**丹麦语 _RAZA 供稿🙂**。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。