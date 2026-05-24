# 基础数据类型和派生数据类型的区别

> 原文:[https://www . geesforgeks . org/基本数据类型和派生数据类型之间的区别/](https://www.geeksforgeeks.org/difference-between-fundamental-data-types-and-derived-data-types/)

在计算机编程中，[数据类型](https://www.geeksforgeeks.org/c-data-types/)是一个分类，它向编译器或解释器指定用户打算使用哪种类型的数据。

有两种数据类型–

*   [原语/基础数据类型](https://www.geeksforgeeks.org/c-data-types/):C/c++ 中的每个变量都有一个关联的数据类型。每种数据类型需要不同的内存量，并且有一些特定的操作可以在其上执行。
    **基础数据类型示例–**

## C++

```cpp
// C++ program to illustrate array
// derived data type
#include <bits/stdc++.h>
using namespace std;

// main method starts from here
int main()
{
    // array of size 5
    int a[5] = { 1, 2, 3, 4, 5 };

    // indexing variable
    int i;
    for (i = 0; i < 5; i++)
        cout << ("%d ", a[i]);
    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
// Java program to illustrate
// primitive data types

class GFG {

    public static void main(String[] args)
    {
        // Integer value
        int a = 2;

        // Float value
        float b = 2.0f;

        // Double value
        double c = 2.0003;

        // Character
        char d = 'D';

        System.out.printf("Integer value is = %d", a);
        System.out.printf("\nFloat value is = %f", b);
        System.out.printf("\nDouble value is = %f", c);
        System.out.printf("\nChar value is = %c", d);
    }
}

// This code has been contributed by 29AjayKumar
```

## 计算机编程语言

```cpp
# Python program to illustrate
# primitive data types

# Integer value
a = 2

# Float value
b = 2.0

# Double value
c = 2.0003

# Character
d ='D'
print("Integer value is = ", a);
print("\nFloat value is = ", b);
print("\nDouble value is = ", c);
print("\nChar value is = ", d);

# This code has been contributed by Code_Mech
```

## C#

```cpp
// C# program to illustrate
// primitive data types
using System;

class GFG {

    public static void Main()
    {
        // Integer value
        int a = 2;

        // Float value
        float b = 2.0f;

        // Double value
        double c = 2.0003;

        // Character
        char d = 'D';

        Console.WriteLine("Integer value is = " + a);
        Console.WriteLine("\nFloat value is = " + b);
        Console.WriteLine("\nDouble value is = " + c);
        Console.WriteLine("\nChar value is = " + d);
    }
}

// This code has been contributed by Code_Mech.
```

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```cpp
<?php
// PHP program to illustrate
// primitive data types
{
    // Integer value
    $a = 2;

    // Float value
    $b = 2.0;

    // Double value
    $c = 2.0003;

    // Character
    $d = 'D';

    echo("Integer value is = ". $a);
    echo("\nFloat value is = ". $b);
    echo("\nDouble value is = ". $c);
    echo("\nChar value is = ". $d);
}

// This code has been contributed by Code_Mech.
```

## java 描述语言

```cpp
<script>

// JavaScript program to illustrate
// primitive data types

   // Integer value
        var a = 2;

        // Float value
        var b = 2.0;

        // Double value
        var c = 2.0003;

        // Character
        var d = 'D';

        document.write("Integer value is = ", a + "<br>");
        document.write("\nFloat value is = ", b + "<br>");
        document.write("\nDouble value is = ", c + "<br>");
        document.write("\nChar value is = ", d + "<br>");

// This code has been contributed by shivanisinghss2110

</script>
```

**Output:** 

```cpp
Integer value is = 2
Float value is = 2.000000
Double value is = 2.000300
Char value is = D
```

*   **派生数据类型:**这些数据类型由用户自己定义。比如，用 C++ 定义一个类或者一个结构。这些包括[数组](https://www.geeksforgeeks.org/arrays-in-c-language-set-1-introduction/)、[结构](https://www.geeksforgeeks.org/difference-c-structures-c-structures/)、[类](https://www.geeksforgeeks.org/c-classes-and-objects/)、[联合](https://www.geeksforgeeks.org/union-c/)、[枚举](https://www.geeksforgeeks.org/enumeration-enum-c/)、[指针](https://www.geeksforgeeks.org/pointers-in-c-and-c-set-1-introduction-arithmetic-and-array/)等。
    **派生数据类型示例:**
    *   **指针:**

## C++

```cpp
// C++ program to illustrate pointer
// as derived data type
#include <iostream>
using namespace std;

// main method
int main()
{
    // integer variable
    int variable = 10;

    // Pointer for storing address
    int* pointr;

    // Assigning address of variable to pointer
    pointr = &variable;
    cout << "Value of variable = " <<  variable;

    // cout << "\nValue at pointer = "<<  pointr;
    cout << "\nValue at *pointer = "<< *pointr;
    return 0;
}

// This code is contributed by shubhamsingh10
```

## C

```cpp
// C program to illustrate pointer
// as derived data type
#include <stdio.h>
// main method starts from here
int main()
{
    // integer variable
    int variable = 10;

    // Pointer for storing address
    int* pointr;

    // Assigning address of variable to pointer
    pointr = &variable;
    printf("Value of variable = %d", variable);

    // printf("\nValue at pointer = %d", pointr);
    printf("\nValue at *pointer = %d", *pointr);
    return 0;
}
```

**Output:** 

```cpp
Value of variable = 10
Value at *pointer = 10
```

*   **阵列:**

## C++

```cpp
// C++ program to illustrate array
// derived data type
#include <bits/stdc++.h>
using namespace std;
// main method starts from here
int main()
{
    // array of size 5
    int a[5] = { 1, 2, 3, 4, 5 };

    // indexing variable
    int i;
    for (i = 0; i < 5; i++)
        cout << ("%d ", a[i]);
    return 0;
}

// This code is contributed by Code_Mech.
```

## C

```cpp
// C program to illustrate array
// derived data type
#include <stdio.h>
// main method starts from here
int main()
{
    // array of size 5
    int a[5] = { 1, 2, 3, 4, 5 };

    // indexing variable
    int i;
    for (i = 0; i < 5; i++)
        printf("%d  ", a[i]);
    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
// Java program to illustrate array
// derived data type
import java.util.*;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // array of size 5
        int a[] = { 1, 2, 3, 4, 5 };

        // indexing variable
        int i;
        for (i = 0; i < 5; i++)
            System.out.printf("%d ", a[i]);
    }
}

/* This code contributed by PrinciRaj1992 */
```

## 蟒蛇 3

```cpp
# Python3 program to illustrate array
# derived data type

# Driver code

# array of size 5
a = [1, 2, 3, 4, 5];

# indexing variable
for i in range(5):
    print(a[i], end = " ");

# This code contributed by mits
```

## C#

```cpp
// C# program to illustrate array
// derived data type
using System;

class GFG {
    // Driver code
    public static void Main(String[] args)
    {
        // array of size 5
        int[] a = { 1, 2, 3, 4, 5 };

        // indexing variable
        int i;
        for (i = 0; i < 5; i++)
            Console.Write("{0} ", a[i]);
    }
}

// This code contributed by Rajput-Ji
```

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```cpp
<?php
// PHP program to illustrate array
// derived data type

// Driver code

// array of size 5
$a = array(1, 2, 3, 4, 5);

// indexing variable
for ($i = 0; $i < 5; $i++)
    print($a[$i] . " ");

// This code contributed by mits
?>
```

## java 描述语言

```cpp
<script>

// Javascript program to illustrate
// array derived data type

// Array of size 5
let a = [ 1, 2, 3, 4, 5 ];

// Indexing variable
let i;
for(i = 0; i < 5; i++)
    document.write(a[i] + " ");

// This code is contributed by decode2207

</script>
```

**Output:** 

```cpp
1  2  3  4  5
```

*   **结构**–

## C++

```cpp
// C++ program to illustrate structure
// derived data type
#include <bits/stdc++.h>
using namespace std;

// structure
struct structure_example
{
    int integer;
    float decimal;
    char character[20];
};

// Main Method
int main()
{
    struct structure_example s = { 15, 98.9, "geeksforgeeks" };
    cout << "Structure data -"<< endl;
    cout << "integer = " << s.integer << endl;
    cout << fixed<<setprecision(6)<< "decimal = " << s.decimal << endl;
    cout << "name = " << s.character << endl;
    return 0;
}

// This code is contributed by shubhamsingh10
```

## C

```cpp
// C program to illustrate structure
// derived data type
#include <stdio.h>
// structure
struct structure_example {
    int integer;
    float decimal;
    char character[20];
};
// main method starts from here
void main()
{
    struct structure_example s = { 15, 98.9, "geeksforgeeks" };
    printf("Structure data - \n integer = %d \n decimal =
    %f \n name = %s", s.integer, s.decimal, s.character);
}
```

**Output:** 

```cpp
Structure data - 
 integer = 15 
 decimal = 98.900002 
 name = geeksforgeeks
```

<figure class="table">

| 基本数据类型 | 派生数据类型 |
| --- | --- |
| 基本数据类型也称为原始数据类型。这些是基本的数据类型。 | 派生数据类型是基本数据类型的集合。 |
| 字符、整数、浮点和 void 是基本的数据类型。 | 指针、数组、结构和联合都是派生数据类型。 |
| 字符用于字符。可以分为
字符、有符号字符、无符号字符。 | 指针用于存储变量的地址。 |
| 整数用于整数(没有十进制数字)。它可以分为有符号和无符号。进一步分为 int、short int 和 long int。 | 数组用于包含类似类型的数据。
 |
| 浮点数用于十进制数。这些分为浮点型、双精度型和长双精度型。 | 结构用于将可能不同类型的项组合成一个类型。 |
| void 用在不需要返回值的地方。 | 它类似于结构，但是联合中的所有成员共享相同的内存位置 |

</figure>