# 嵌套循环拼图

> 原文:[https://www.geeksforgeeks.org/a-nested-loop-puzzle/](https://www.geeksforgeeks.org/a-nested-loop-puzzle/)

以下两个代码段哪个更快？假设编译器没有优化。

## C

```cpp
/* FIRST */
for(i=0;i<10;i++)
  for(j=0;j<100;j++)
    //do something
```

## 蟒蛇 3

```cpp
# FIRST
for i in range(10):
    for j in range(100):
        #do something

# This code is contributed by shivani
```

## C

```cpp
/* SECOND */
for(i=0;i<100;i++)
  for(j=0;j<10;j++)
    //do something
```

## 蟒蛇 3

```cpp
# SECOND
for i in range(100):
    for j in range(10):

      # Do something

# This code is contributed by shivani
```

两个代码段提供相同的功能，两个 for 循环中的代码在两个代码段中的执行次数相同。
如果我们仔细观察，那么我们可以看到第二个比第一个做更多的操作。它执行 for 循环的所有三个部分(赋值、比较和增量)的次数多于 FIRST 的相应部分:

1.  第二次执行赋值操作(j = 0 或 i = 0) 101 次，而第一次只执行 11 次。
2.  第二个进行 101 + 1100 次比较(i < 100 或 j < 10)，而第一个进行 11 + 1010 次比较(i < 10 或 j < 100)。
3.  第二个执行 1100 个增量操作(i++ 或 j++)，而第一个执行 1010 个增量操作。

下面的代码计算第一次和第二次执行的增量操作的数量，并打印计数。

## C++

```cpp
// C++ program to count number of increment
// operations in FIRST and SECOND
#include<iostream>

using namespace std;

int main()
{
  int c1 = 0, c2 = 0;

  /* FIRST */
  for(int i=0;i<10;i++,c1++)
    for(int j=0;j<100;j++, c1++);

  /* SECOND */
  for(int i=0; i<100; i++, c2++)
      for(int j=0; j<10; j++, c2++);

  cout << " Count in FIRST = " <<c1 << endl;
  cout << " Count in SECOND  = " <<c2 << endl;

  getchar();
  return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
// Java program to count number of increment
// operations in FIRST and SECOND

import java.io.*;

class GFG {
    public static void main (String[] args) {
       int c1 = 0, c2 = 0;

        for(int i=0; i<10;i++, c1++){
          for(int j=0;j<100;j++, c1++){}
        }

        for(int i=0;i<100;i++, c2++){
              for(int j=0;j<10;j++, c2++){}
        }

        System.out.println( "Count in First = "+c1);       
        System.out.println( "Count in SECOND = "+c2);
    }
}
```

## 蟒蛇 3

```cpp
# Python program to count number of increment
# operations in FIRST and SECOND
c1 = 0
c2 = 0

# FIRST
for i in range (10):
    for j in range (100):
        c1 += 1
    c1 += 1

# SECOND
for i in range (100):
    for j in range (10):
        c2 += 1
    c2 += 1

print("Count in FIRST = " ,c1)
print("Count in SECOND  = " ,c2)

# This code is contributed by shivanisinghss2110
```

## C#

```cpp
// C# program to count number of increment
// operations in FIRST and SECOND
using System;

class GFG{

public static void Main (String[] args)
{
   int c1 = 0, c2 = 0;

    for(int i = 0; i < 10; i++, c1++)
    {
        for(int j = 0; j < 100;j++, c1++){}
    }

    for(int i = 0; i < 100; i++, c2++)
    {
        for(int j = 0; j < 10; j++, c2++){}
    }

    Console.WriteLine("Count in First = " + c1);       
    Console.WriteLine("Count in SECOND = " + c2);
}
}

// This code is contributed by shivanisinghss2110
```

## java 描述语言

```cpp
<script>

// JavaScript program to count number of increment
// operations in FIRST and SECOND
       let c1 = 0, c2 = 0;

        for(let i=0; i<10;i++, c1++){
          for(let j=0;j<100;j++, c1++){}
        }

        for(let i=0;i<100;i++, c2++){
              for(let j=0;j<10;j++, c2++){}
        }

        document.write( "Count in First = "+c1 +"<br>");       
        document.write( "Count in SECOND = "+c2);
  // this code is contributed by shivanisinghss2110 

</script>
```

**Output**

```cpp
 Count in FIRST = 1010
 Count in SECOND  = 1100
```

下面的代码计算第一次和第二次执行的比较操作的数量

## C++

```cpp
//program to count the number of comparison
//operations executed by FIRST and SECOND */
#include<iostream>

using namespace std;

int main()
{
   int c1 = 0, c2 = 0;

   /* FIRST */
   for(int i=0; ++ c1&&i<10; i++)
      for(int j=0; ++ c1&&j<100;j++);

   /* SECOND */
   for(int i=0; ++ c2&&i<100; i++)
      for(int j=0; ++ c2&&j<10; j++);

   cout << " Count for FIRST  " <<c1 << endl;
   cout << " Count for SECOND  " <<c2 << endl;
   getchar();
   return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
/*package whatever //do not write package name here */

import java.io.*;

class GFG {
    public static void main (String[] args) {
         int c1 = 0, c2 = 0;

        for(int i=0; i<++ c1 && i<10;i++) {
              for(int j=0;j<++ c1 &&j<100;j++) {                 
              }
        }

        for(int i=0;i<++ c2 && i<100;i++) {
              for(int j=0;j<++ c2 &&j<10;j++) {        
              }
        }

        System.out.println( "Count in FIRST = "+c1);       
        System.out.println( "Count in SECOND  = "+c2);   

    }
}
```

## 蟒蛇 3

```cpp
#program to count the number of comparison
#operations executed by FIRST and SECOND */

# FIRST
c1 = 1
c2 = 1
i = 0
while (i < c1 and i < 10):
    j = -1
    c1 += 1
    while (j < c1 and j < 100):
        c1 += 1
        j += 1
    i += 1

# SECOND
i = 0
while (i < c2 and i < 100):
    j = -1
    c2 += 1
    while (j < c2 and j < 10):
        c2 += 1
        j += 1
    i += 1

print(" Count fot FIRST  " , c1)
print(" Count fot SECOND  " , c2)

# This code is contributed by shivanisinghss2110

```

## C#

```cpp
/*package whatever //do not write package name here */

using System;

class GFG {
    public static void Main (String[] args) {
         int c1 = 0, c2 = 0;

        for(int i = 0; i < ++ c1 && i < 10; i++)
        {
              for(int j = 0; j < ++ c1 && j < 100; j++)
              {                 
              }
        }

        for(int i = 0; i < ++ c2 && i < 100; i++) {
              for(int j = 0; j < ++ c2 && j < 10; j++) {        
              }
        }

        Console.WriteLine( "Count in FIRST = "+c1);       
        Console.WriteLine( "Count in SECOND  = "+c2);   

    }
}

// This code is contributed by shivanisinghss2110
```

## java 描述语言

```cpp
<script>

/*package whatever //do not write package name here */
//program to count the number of comparison
//operations executed by FIRST and SECOND */

         let c1 = 0, c2 = 0;

        for(let i=0; i<++ c1 && i<10;i++) {
              for(let j=0;j<++ c1 &&j<100;j++) {                 
              }
        }

        for(let i=0;i<++ c2 && i<100;i++) {
              for(let j=0;j<++ c2 &&j<10;j++) {        
              }
        }

        document.write( "Count in FIRST = "+c1 +"<br>");       
        document.write( "Count in SECOND  = "+c2);   

// this code is contributed by shivanisinghss2110  

</script>
```

**Output**

```cpp
 Count for FIRST  1021
 Count for SECOND  1201

```

感谢 [Dheeraj](https://www.geeksforgeeks.org/forums/users/dheeraj) 提出解决方案。
如果您发现任何答案/代码不正确，或者您想分享关于上述主题的更多信息，请写评论。