# C# |运算符

> 原文:[https://www.geeksforgeeks.org/c-sharp-operators/](https://www.geeksforgeeks.org/c-sharp-operators/)

运算符是任何编程语言的基础。因此[**【c#**](https://www.geeksforgeeks.org/introduction-to-c-sharp/)语言的功能性在没有使用运算符的情况下是不完整的。运算符允许我们对**操作数**执行不同类型的运算。在 [C# ](https://www.geeksforgeeks.org/introduction-to-c-sharp/) 中，操作员可以根据其不同的**功能**进行分类**:**

*   [算术运算符](# Arithmetic Operators)
*   [关系运算符](# Relational Operators)
*   [逻辑运算符](# Logical Operators)
*   [按位运算符](# Bitwise Operators)
*   [分配操作员](# Assignment Operators)
*   [条件运算符](# Conditional Operator)

在 C# 中，操作符也可以根据操作数的数量来分类【T0:

*   **一元运算符:**取**一个**操作数进行运算的运算符。
*   **二元运算符:**取**两个**操作数进行运算的运算符。
*   **三元运算符:**取**三个**操作数进行运算的运算符。

**算术运算符**

这些用于对操作数执行算术/数学运算。属于此类别的**二进制运算符**有:

*   **加法:****“+”**运算符将两个操作数相加。例如 **x+y** 。
*   **减法:****“-”**运算符减去两个操作数。例如 **x-y** 。
*   **乘法:****' ***运算符将两个操作数相乘。例如 **x*y** 。
*   **除法:****/**运算符将第一个操作数除以第二个操作数。例如， **x/y** 。
*   **模数:**当第一个操作数除以第二个操作数时，**“%”**运算符返回余数。例如， **x%y** 。

**示例:**

## C#

```cs
// C# program to demonstrate the working
// of Binary Arithmetic Operators
using System;
namespace Arithmetic
{
    class GFG
    {

        // Main Function
        static void Main(string[] args)
        {

            int result;
            int x = 10, y = 5;

            // Addition
            result = (x + y);
            Console.WriteLine("Addition Operator: " + result);

            // Subtraction
            result = (x - y);
            Console.WriteLine("Subtraction Operator: " + result);

            // Multiplication
            result = (x * y);
            Console.WriteLine("Multiplication Operator: "+ result);

            // Division
            result = (x / y);
            Console.WriteLine("Division Operator: " + result);

            // Modulo
            result = (x % y);
            Console.WriteLine("Modulo Operator: " + result);
        }
    }
}
```

**输出:**

```cs
Addition Operator: 15
Subtraction Operator: 5
Multiplication Operator: 50
Division Operator: 2
Modulo Operator: 0
```

属于**一元运算符**的有:

*   **增量:****“++”**运算符用于增加整数值。当放在变量名(也称为**预递增**运算符)之前时，其值会立即递增。例如 **++x** 。
    当它被放在变量名之后(也称为**后递增运算符**)时，它的值会被暂时保留，直到执行该语句，并在执行下一个语句之前得到更新。比如 **x++** 。
*   **递减:****“–”**运算符用于递减整数值。当放在变量名(也称为**预递减运算符**)之前时，其值会立即递减。例如**–x**。
    当它被放在变量名之后(也称为**后递减运算符**)时，它的值会被临时保留，直到执行该语句，并在执行下一个语句之前得到更新。例如，**x–**。

**示例:**

## C#

```cs
// C# program to demonstrate the working
// of Unary Arithmetic Operators
using System;
namespace Arithmetic {

    class GFG {

        // Main Function
        static void Main(string[] args)
        {

            int a = 10, res;

            // post-increment example:
            // res is assigned 10 only,
            // a is not updated yet
            res = a++;

             //a becomes 11 now
            Console.WriteLine("a is {0} and res is {1}", a, res);

            // post-decrement example:
            // res is assigned 11 only, a is not updated yet
            res = a--;

            //a becomes 10 now
            Console.WriteLine("a is {0} and res is {1}", a, res); 

            // pre-increment example:
            // res is assigned 11 now since a
            // is updated here itself
            res = ++a;

            // a and res have same values = 11
            Console.WriteLine("a is {0} and res is {1}", a, res);

            // pre-decrement example:
            // res is assigned 10 only since
            // a is updated here itself
            res = --a;

            // a and res have same values = 10
            Console.WriteLine("a is {0} and res is {1}",a, res);

        }
    }
}
```

**输出:**

```cs
a is 11 and res is 10
a is 10 and res is 11
a is 11 and res is 11
a is 10 and res is 10
```

**关系运算符**

关系运算符用于比较两个值。让我们一个一个来看:

*   **'== '(等于)**运算符检查两个给定的操作数是否相等。如果是，它返回真。否则返回假。例如， **5==5** 将返回真。
*   **’！= '(不等于)**运算符检查两个给定的操作数是否相等。如果不是，它返回真。否则返回假。它是**= =“**运算符的精确布尔补码。比如， **5！=5** 将返回假。
*   **' >'(大于)**运算符检查第一个操作数是否大于第二个操作数。如果是，它返回真。否则返回假。比如 **6 > 5** 会回真。
*   **' <'(小于)**运算符检查第一个操作数是否小于第二个操作数。如果是，它返回真。否则返回假。比如 **6 < 5** 会回假。
*   **' > = '(大于等于)**运算符检查第一个操作数是否大于或等于第二个操作数。如果是，它返回真。否则返回假。比如 **5 > =5** 会回真。
*   **' < = '(小于等于)**运算符检查第一个操作数是否小于或等于第二个操作数。如果是，它返回真。否则返回假。比如 **5 < =5** 也会回真。

**示例:**

## C#

```cs
// C# program to demonstrate the working
// of Relational Operators
using System;
namespace Relational {

class GFG {

    // Main Function
    static void Main(string[] args)
    {
        bool result;
        int x = 5, y = 10;

        // Equal to Operator
        result = (x == y);
        Console.WriteLine("Equal to Operator: " + result);

        // Greater than Operator
        result = (x > y);
        Console.WriteLine("Greater than Operator: " + result);

        // Less than Operator
        result = (x < y);
        Console.WriteLine("Less than Operator: " + result);

        // Greater than Equal to Operator
        result = (x >= y);
        Console.WriteLine("Greater than or Equal to: "+ result);

        // Less than Equal to Operator
        result = (x <= y);
        Console.WriteLine("Lesser than or Equal to: "+ result);

        // Not Equal To Operator
        result = (x != y);
        Console.WriteLine("Not Equal to Operator: " + result);
    }
}
}
```

**输出:**

```cs
Equal to Operator: False
Greater than Operator: False
Less than Operator: True
Greater than or Equal to: False
Lesser than or Equal to: True
Not Equal to Operator: True
```

**逻辑运算符**

它们用于组合两个或多个条件/约束，或者补充所考虑的原始条件的评估。它们描述如下:

*   **逻辑与:****'&&'**运算符在考虑的两个条件都满足时返回真。否则返回假。例如， **a & & b** 在 a 和 b 都为真(即非零)时返回真。
*   **逻辑或:**当所考虑的一个(或两个)条件满足时， **'||'** 运算符返回真。否则返回假。例如，如果 a 或 b 中的一个为真(即非零)，则 **a || b** 返回真。当然，当 a 和 b 都为真时，它返回真。
*   **逻辑非:****“！”**如果考虑的条件不满足，运算符返回 true。否则返回假。比如**！如果 a 为假，即当 a=0 时，a** 返回真。

**示例:**

## C#

```cs
// C# program to demonstrate the working
// of Logical Operators
using System;
namespace Logical {

class GFG {

    // Main Function
    static void Main(string[] args)
    {
            bool a = true,b = false, result;

            // AND operator
            result = a && b;
            Console.WriteLine("AND Operator: " + result);

            // OR operator
            result = a || b;
            Console.WriteLine("OR Operator: " + result);

            // NOT operator
            result = !a;
            Console.WriteLine("NOT Operator: " + result);

    }
}
}
```

**输出:**

```cs
AND Operator: False
OR Operator: True
NOT Operator: False
```

**按位运算符**

在 C# 中，有 6 个按位运算符，它们在位级别工作或用于执行逐位操作。以下是按位运算符:

*   **&(按位“与”)**将两个数字作为操作数，并对两个数字的每一位进行“与”。仅当两位都为 1 时，“与”的结果才为 1。
*   **|(按位“或”)**将两个数字作为操作数，并对两个数字的每一位进行“或”。“或”的结果是 1，两位中的任何一位都是 1。
*   **^(按位异或)**将两个数字作为操作数，并对两个数字的每一位进行异或运算。如果两位不同，异或的结果是 1。
*   **< <(左移)**取两个数，左移第一个操作数的位，第二个操作数决定移位的位数。
*   **> >(右移)**取两个数，右移第一个操作数的位，第二个操作数决定移位的位数。

**示例:**

## C#

```cs
// C# program to demonstrate the working
// of Bitwise Operators
using System;
namespace Bitwise {

class GFG {

    // Main Function
    static void Main(string[] args)
    {
         int x = 5, y = 10, result;

            // Bitwise AND Operator
            result = x & y;
            Console.WriteLine("Bitwise AND: " + result);

            // Bitwise OR Operator
            result = x | y;
            Console.WriteLine("Bitwise OR: " + result);

            // Bitwise XOR Operator
            result = x ^ y;
            Console.WriteLine("Bitwise XOR: " + result);

            // Bitwise AND Operator
            result = ~x;
            Console.WriteLine("Bitwise Complement: " + result);

            // Bitwise LEFT SHIFT Operator
            result = x << 2;
            Console.WriteLine("Bitwise Left Shift: " + result);

            // Bitwise RIGHT SHIFT Operator
            result = x >> 2;
            Console.WriteLine("Bitwise Right Shift: " + result);

    }
}
}
```

**输出:**

```cs
Bitwise AND: 0
Bitwise OR: 15
Bitwise XOR: 15
Bitwise Complement: -6
Bitwise Left Shift: 20
Bitwise Right Shift: 1
```

**分配操作员**

赋值运算符用于给变量赋值。赋值运算符的左侧操作数是一个变量，而赋值运算符的右侧操作数是一个值。右侧的值必须与左侧变量的数据类型相同，否则编译器将引发错误。

不同类型的赋值运算符如下所示:

*   **"= "(简单赋值)**:这是最简单的赋值运算符。该运算符用于将右边的值赋给左边的变量。
    例:

```cs
a = 10;
b = 20;
ch = 'y';
```

*   **“+=”(添加赋值)**:这个运算符是“+”和“=”运算符的组合。该运算符首先将左边变量的当前值与右边的值相加，然后将结果赋给左边的变量。
    例:

```cs
(a += b) can be written as (a = a + b)
```

如果最初存储在 a 中的值是 5。然后(a += 6) = 11。

*   **"-= "(减法赋值)**:这个运算符是'-'和' = '运算符的组合。该运算符首先从右边的值中减去左边变量的当前值，然后将结果赋给左边的变量。
    例:

```cs
(a -= b) can be written as (a = a - b)
```

如果最初存储在 a 中的值是 8。然后(a -= 6) = 2。

*   **"*= "(乘法赋值)**:该运算符是' * '和' = '运算符的组合。该运算符首先将左边变量的当前值乘以右边的值，然后将结果赋给左边的变量。
    例:

```cs
(a *= b) can be written as (a = a * b)
```

如果最初存储在 a 中的值是 5。然后(a *= 6) = 30。

*   **"/= "(除法赋值):**这个运算符是“/”和“=”运算符的组合。该运算符首先将左边变量的当前值除以右边的值，然后将结果赋给左边的变量。
    例:

```cs
(a /= b) can be written as (a = a / b)
```

如果最初存储在 a 中的值是 6。然后(a /= 2) = 3。

*   **“% =”(模数赋值):**这个运算符是“%”和“=”运算符的组合。该运算符首先用右边的值对左边变量的当前值取模，然后将结果赋给左边的变量。
    例:

```cs
(a %= b) can be written as (a = a % b)
```

如果最初存储在 a 中的值是 6。然后(a %= 2) = 0。

*   **“<”T4】=”(左移分配)**:该运算符是“< <”和“=”运算符的组合。该运算符首先将左边变量的当前值左移右边的值，然后将结果赋给左边的变量。
    例:

```cs
(a <<= 2) can be written as (a = a << 2)
```

如果最初存储在 a 中的值是 6。然后(a <<= 2) = 24。

*   **“>”T4】=”(右移赋值)**:该运算符是“> >”和“=”运算符的组合。该运算符首先将左边变量的当前值右移右边的值，然后将结果赋给左边的变量。
    例:

```cs
(a >>= 2) can be written as (a = a >> 2)
```

如果最初存储在 a 中的值是 6。然后(a >>= 2) = 1。

*   **“&=”(按位 AND 赋值)**:这个运算符是“&”和“=”运算符的组合。这个运算符首先用右边的值“按位与”左边变量的当前值，然后将结果赋给左边的变量。
    例:

```cs
(a &= 2) can be written as (a = a & 2)
```

如果最初存储在 a 中的值是 6。然后(a &= 2) = 2。

*   **【^="(bitwise 异或】**:这个运算符是'^'和' = '运算符的组合。该运算符首先用右边的值“按位异或”左边变量的当前值，然后将结果赋给左边的变量。
    例:

```cs
(a ^= 2) can be written as (a = a ^ 2)
```

如果最初存储在 a 中的值是 6。那么(a ^= 2) = 4。

*   **"|= "(按位包含或)**:该运算符是“|”和“=”运算符的组合。这个运算符首先用右边的值“按位异或”左边变量的当前值，然后将结果赋给左边的变量。
    例:

```cs
(a |= 2) can be written as (a = a | 2)
```

如果最初存储在 a 中的值是 6。然后(a |= 2) = 6。

**示例:**

## C#

```cs
// C# program to demonstrate the working
// of Assignment Operators
using System;
namespace Assignment {

class GFG {

    // Main Function
    static void Main(string[] args)
    {

            // initialize variable x
            // using Simple Assignment
            // Operator "="
            int x = 15;

            // it means x = x + 10
            x += 10;
            Console.WriteLine("Add Assignment Operator: " + x);

             // initialize variable x again
            x = 20;

            // it means x = x - 5
            x -= 5;
            Console.WriteLine("Subtract Assignment Operator: " + x);

            // initialize variable x again
            x = 15;

            // it means x = x * 5
            x *= 5;
            Console.WriteLine("Multiply Assignment Operator: " + x);

            // initialize variable x again
            x = 25;

            // it means x = x / 5
            x /= 5;
            Console.WriteLine("Division Assignment Operator: " + x);

            // initialize variable x again
            x = 25;

            // it means x = x % 5
            x %= 5;
            Console.WriteLine("Modulo Assignment Operator: " + x);

            // initialize variable x again
            x = 8;

            // it means x = x << 2
            x <<= 2;
            Console.WriteLine("Left Shift Assignment Operator: " + x);

            // initialize variable x again
            x = 8;

            // it means x = x >> 2
            x >>= 2;
            Console.WriteLine("Right Shift Assignment Operator: " + x);

            // initialize variable x again
            x = 12;

            // it means x = x >> 4
            x &= 4;
            Console.WriteLine("Bitwise AND Assignment Operator: " + x);

            // initialize variable x again
            x = 12;

            // it means x = x >> 4
            x ^= 4;
            Console.WriteLine("Bitwise Exclusive OR Assignment Operator: " + x);

             // initialize variable x again
            x = 12;

            // it means x = x >> 4
            x |= 4;
            Console.WriteLine("Bitwise Inclusive OR Assignment Operator: " + x);

    }
}
}
```

**输出:**

```cs
Add Assignment Operator: 25
Subtract Assignment Operator: 15
Multiply Assignment Operator: 75
Division Assignment Operator: 5
Modulo Assignment Operator: 0
Left Shift Assignment Operator: 32
Right Shift Assignment Operator: 2
Bitwise AND Assignment Operator: 4
Bitwise Exclusive OR Assignment Operator: 8
Bitwise Inclusive OR Assignment Operator: 12
```

**条件运算符**

它是三元运算符，是 if-else 语句的简写版本。它有三个操作数，因此得名三元。它将根据布尔表达式的值返回两个值之一。

**语法:**

```cs
condition ? first_expression : second_expression;
```

**说明:**
条件:必须评估为真或假。
如果条件为真
第一个表达式被求值并成为结果。
如果条件为假，则
second_expression 被求值并成为结果。

**示例:**

## C#

```cs
// C# program to demonstrate the working
// of Conditional Operator
using System;
namespace Conditional {

class GFG {

    // Main Function
    static void Main(string[] args)
    {
            int x = 5, y = 10, result;

            // To find which value is greater
            // Using Conditional Operator
            result = x > y ? x : y;

            // To display the result
            Console.WriteLine("Result: " + result);

            // To find which value is greater
            // Using Conditional Operator
            result = x < y ? x : y;

            // To display the result
            Console.WriteLine("Result: " + result);
    }
}
}
```

**输出:**

```cs
Result: 10
Result: 5
```