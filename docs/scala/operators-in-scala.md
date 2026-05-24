# Scala 中的运算符

> 原文:[https://www.geeksforgeeks.org/operators-in-scala/](https://www.geeksforgeeks.org/operators-in-scala/)

运算符是一种符号，表示要用一个或多个操作数执行的操作。运算符是任何编程语言的基础。运算符允许我们对操作数执行不同类型的操作。Scala 中使用了不同类型的运算符，如下所示:

**算术运算符**

这些用于对操作数执行算术/数学运算。

*   **加法(+)** 运算符将两个操作数相加。例如 **x+y** 。
*   **减法(-)** 运算符减去两个操作数。例如 **x-y** 。
*   **乘法(*)** 运算符将两个操作数相乘。例如 **x*y** 。
*   **除法(/**运算符将第一个操作数除以第二个操作数。例如 **x/y** 。
*   **模数(%)** 运算符在第一个操作数除以第二个操作数时返回余数。例如， **x%y** 。
*   **指数(**)** 运算符返回操作数的指数(幂)。例如 **x**y** 。

**示例:**

## 斯卡拉

```scala
// Scala program to demonstrate
// the Arithmetic Operators

object Arithop
{

def main(args: Array[String])
{
    // variables
    var a = 50;
    var b = 30;

    // Addition
    println("Addition of a + b = " + (a + b));

    // Subtraction
    println("Subtraction of a - b = " + (a - b));

    // Multiplication
    println("Multiplication of a * b = " + (a * b));

    // Division
    println("Division of a / b = " + (a / b));

    // Modulus
    println("Modulus of a % b = " + (a % b));

}
}
```

**输出:**

```scala
Addition of a + b = 80
Subtraction of a - b = 20
Multiplication of a * b = 1500
Division of a / b = 1
Modulus of a % b = 20
```

**关系运算符**

关系运算符或比较运算符用于比较两个值。让我们一个一个来看:

*   **等于(==)** 运算符检查两个给定的操作数是否相等。如果是，它返回真。否则返回假。例如， **5==5** 将返回真。
*   **不等于(！=)** 运算符检查两个给定的操作数是否相等。如果不是，它返回真。否则返回假。它是**= =“**运算符的精确布尔补码。比如， **5！=5** 将返回假。
*   **大于(> )** 运算符检查第一个操作数是否大于第二个操作数。如果是，它返回真。否则返回假。比如 **6 > 5** 会回真。
*   **小于(< )** 运算符检查第一个操作数是否小于第二个操作数。如果是，它返回真。否则返回假。比如 **6 < 5** 会回假。
*   **大于等于(> =)** 运算符检查第一个操作数是否大于或等于第二个操作数。如果是，它返回真。否则返回假。比如 **5 > =5** 会回真。
*   **小于等于(< =)** 运算符检查第一个操作数是否小于或等于第二个操作数。如果是，它返回真。否则返回假。比如 **5 < =5** 也会回真。

**示例:**

## 斯卡拉

```scala
// Scala program to demonstrate
// the Relational Operators
object Relop
{

def main(args: Array[String])
{
    // variables
    var a = 50;
    var b = 30;

    // Equal to operator
    println("Equality of a == b is : " + (a == b));

    // Not equal to operator
    println("Not Equals of a != b is : " + (a != b));

    // Greater than operator
    println("Greater than of a > b is : " + (a > b));

    // Lesser than operator
    println("Lesser than of a < b is : " + (a < b));

    // Greater than equal to operator
    println("Greater than or Equal to of a >= b is : " + (a >= b));

    // Lesser than equal to operator
    println("Lesser than or Equal to of a <= b is : " + (a <= b));

}
}
```

**输出:**

```scala
Equality of   a == b is : false
Not Equals of a != b is : true
Greater than of a > b is : true
Lesser than of  a = b is : true
Lesser than or Equal to of a <= b is : false
```

**逻辑运算符**

它们用于组合两个或多个条件/约束，或者补充所考虑的原始条件的评估。它们描述如下:

*   **逻辑与(& & )** 运算符在考虑的两个条件都满足时返回真。否则返回假。使用“*和*是& &运算符的替代。例如，当 a 和 b 都为真(即非零)时， **a & & b** 返回真。
*   **当所考虑的一个(或两个)条件满足时，逻辑或(||)** 运算符返回真。否则返回假。使用“*或*是||运算符的替代。例如，如果 a 或 b 中的一个为真(即非零)，则 **a || b** 返回真。当然，当 a 和 b 都为真时，它返回真。
*   **逻辑非(！)**如果所考虑的条件不满足，运算符返回 true。否则返回假。使用“*而不是*是一种替代！操作员。比如**！真**返回假。

**示例:**

## 斯卡拉

```scala
// Scala program to demonstrate
// the Logical Operators
object Logop
{

def main(args: Array[String])
{

    // variables
    var a = false
    var b = true

    // logical NOT operator
    println("Logical Not of !(a && b) = " + !(a && b));

    // logical OR operator
    println("Logical Or of a || b = " + (a || b));

    // logical AND operator
    println("Logical And of a && b = " + (a && b));

}
}
```

**输出:**

```scala
Logical Not of !(a && b) = true
Logical Or of a || b = true
Logical And of a && b = false
```

**分配操作员**

赋值运算符用于给变量赋值。赋值运算符的左侧操作数是一个变量，而赋值运算符的右侧操作数是一个值。右侧的值必须与左侧变量的数据类型相同，否则编译器将引发错误。
不同类型的赋值运算符如下所示:

*   **简单赋值(=)** 运算符是最简单的赋值运算符。该运算符用于将右边的值赋给左边的变量。
*   **Add AND Assignment (+=)** 运算符用于将左操作数和右操作数相加，然后赋值给左边的变量。
*   **减法与赋值(-=)** 运算符用于用右操作数减去左操作数，然后赋值给左边的变量。
*   **乘法与赋值(*=)** 运算符用于将左操作数与右操作数相乘，然后将其赋值给左边的变量。
*   **除与赋值(/=)** 运算符用于将左操作数与右操作数相除，然后将其赋值给左边的变量。
*   **模数与赋值(%=)** 运算符用于赋值左操作数与右操作数的模，然后赋值给左边的变量。
*   **指数与赋值(**=)** 运算符用于将左操作数的幂提高到右操作数，并将其赋值给左边的变量。
*   **左移和赋值(< < =)** 运算符用于对左操作数和右操作数进行二进制左移，并将其赋值给左边的变量。
*   **右移和赋值(> > =)** 运算符用于对左操作数和右操作数进行二进制右移，并将其赋值给左边的变量。
*   **按位 And 赋值(& =)** 运算符用于对左操作数和右操作数执行按位 AND 运算，并将其赋给左边的变量。
*   **按位异或和 Assignment(^=)** 运算符用于对左操作数和右操作数执行按位异或运算，并将其分配给左边的变量。
*   **按位包含 or 和赋值(|=)** 运算符用于对左操作数和右操作数执行按位包含 OR 运算，并将其赋给左边的变量。

**示例:**

## 斯卡拉

```scala
// Scala program to demonstrate
// the Assignments Operators
object Assignop
{

def main(args: Array[String])
{

    // variables
    var a = 50;
    var b = 40;
    var c = 0;

    // simple addition
    c = a + b;
    println("simple addition: c= a + b = " + c);

    // Add AND assignment
    c += a;
    println("Add and assignment of c += a = " + c);

    // Subtract AND assignment
    c -= a;
    println("Subtract and assignment of c -= a = " + c);

    // Multiply AND assignment
    c *= a;
    println("Multiplication and assignment of c *= a = " + c);

    // Divide AND assignment
    c /= a;
    println("Division and assignment of c /= a = " + c);

    // Modulus AND assignment
    c %= a;
    println("Modulus and assignment of c %= a = " + c);

    // Left shift AND assignment
    c <<= 3;
    println("Left shift and assignment of c <<= 3 = " + c);

    // Right shift AND assignment
    c >>= 3;
    println("Right shift and assignment of c >>= 3 = " + c);

    // Bitwise AND assignment
    c &= a;
    println("Bitwise And assignment of c &= 3 = " + c);

    // Bitwise exclusive OR and assignment
    c ^= a;
    println("Bitwise Xor and assignment of c ^= a = " + c);

    // Bitwise inclusive OR and assignment
    c |= a;
    println("Bitwise Or and assignment of c |= a = " + c);
}
}
```

**输出:**

```scala
simple addition: c= a + b = 90
Add and assignment of c += a = 140
Subtract and assignment of c -= a = 90
Multiplication and assignment of c *= a = 4500
Division and assignment of c /= a = 90
Modulus and assignment of c %= a = 40
Left shift and assignment of c <<= 3 = 320
Right shift and assignment of c >>= 3 = 40
Bitwise And assignment of c &= 3 = 32
Bitwise Xor and assignment of c ^= a = 18
Bitwise Or and assignment of c |= a = 50
```

**按位运算符**

在 Scala 中，有 7 个按位运算符，它们在位级别工作或用于执行逐位操作。以下是按位运算符:

*   **按位“与”(& ):** 将两个数字作为操作数，并对两个数字的每一位进行“与”。仅当两位都为 1 时，“与”的结果才为 1。
*   **按位 OR (|):** 取两个数作为操作数，对两个数的每一位进行 OR 运算。“或”的结果是 1，两位中的任何一位都是 1。
*   **按位异或(^):** 将两个数字作为操作数，并对两个数字的每一位进行异或运算。如果两位不同，异或的结果是 1。
*   **按位左移(< < ):** 取两个数，左移第一个操作数的位，第二个操作数决定移位的位数。
*   **按位右移(> > ):** 取两个数，右移第一个操作数的位，第二个操作数决定要移位的位数。
*   **按位一补码(~):** 该运算符取一个数字，用于执行 8 位的补码运算。
*   **按位右移零填充(> > > ):** 在右移零填充运算符中，左操作数向右移动右操作数指定的位数，移动后的值用零填充。

**示例:**

## 斯卡拉

```scala
// Scala program to demonstrate
// the Bitwise Operators
object Bitop
{
def main(args: Array[String])
{
    // variables
    var a = 20;
    var b = 18;
    var c = 0;

    // Bitwise AND operator
    c = a & b;
    println("Bitwise And of a & b = " + c);

    // Bitwise OR operator
    c = a | b;
    println("Bitwise Or of a | b = " + c);

    // Bitwise XOR operator
    c = a ^ b;
    println("Bitwise Xor of a ^ b = " + c);

    // Bitwise once complement operator
    c = ~a;
    println("Bitwise Ones Complement of ~a = " + c);

    // Bitwise left shift operator
    c = a << 3;
    println("Bitwise Left Shift of a << 3 = " + c);

    // Bitwise right shift operator
    c = a >> 3;
    println("Bitwise Right Shift of a >> 3 = " + c);

    // Bitwise shift right zero fill operator
    c = a >>> 4;
    println("Bitwise Shift Right a >>> 4 = " + c);
}
}
```

**输出:**

```scala
Bitwise And of a & b = 16
Bitwise Or of a | b = 22
Bitwise Xor of a ^ b = 6
Bitwise Ones Complement of ~a = -21
Bitwise Left Shift of a << 3 = 160
Bitwise Right Shift of a >> 3 = 2
Bitwise Shift Right a >>> 4 = 1
```