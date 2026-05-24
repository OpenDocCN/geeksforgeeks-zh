# Java 中的等式(==)运算符，示例

> 原文：[https://www.geeksforgeeks.org/equality-operator-in-java-with-examples/](https://www.geeksforgeeks.org/equality-operator-in-java-with-examples/)

`==`运算符是 Java 中关系运算符的一种，用于检查等式关系。它在比较后返回一个布尔结果，广泛用于循环语句以及条件 if-else 语句。

## 语法

```java
LHS value == RHS value
```

但是，在比较这些值时，通常会出现三种情况：

### 案例 1：当 LHS 和 RHS 值都是原始值时

这是案例中最简单的。由于原始数据存储在堆栈存储器中，在这种情况下，从堆栈存储器中获取双方的实际值并进行比较。如果两者相等，则返回 `true`，否则返回 `false`。

**语法：**

```java
Actual value == Actual value
```

**示例：**

```java
// Java program for using == operator

import java.io.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring primitive values
        int a = 4;
        int b = 4;
        int c = 5;

        // Comparing a and b using == operator
        System.out.println("Are " + a
                           + " and " + b
                           + " equal? "
                           + (a == b));

        // Comparing b and c using == operator
        System.out.println("Are " + b
                           + " and " + c
                           + " equal? "
                           + (b == c));
    }
}
```

**Output：**

```java
Are 4 and 4 equal? true
Are 4 and 5 equal? false
```

### 案例 2：当 LHS 和 RHS 值一个是原始值，另一个是引用值时

在这种情况下，对于原始值一侧，从堆栈存储器中获取实际值进行比较。但对于引用值一侧，当声明并初始化一个数组时，数据存储在堆内存中，而引用指针存储在堆栈存储器中。因此，堆栈存储器中只有内存地址。

**语法：**

```java
Actual value == Address value
    OR
Address value == Actual value
```

因此，当比较原始值和引用值时，程序不会编译并抛出一个错误：

**Java 代码编译错误：**

```java
prog.java:20: error: incomparable types: int and int[]
                       + (a == b));
                            ^
1 error
```

这是因为原始值一侧的值很容易从堆栈存储器中获取，但对于引用值一侧，该值无法获取，因为该值位于堆内存中。因此出现了错误。

**示例：**

```java
// Java program for using == operator

import java.io.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring primitive value
        int a = 4;

        // Declaring reference value
        int[] b = { 1, 2, 3, 4 };

        // Comparing a and b using == operator
        System.out.println("Are " + a
                           + " and " + b
                           + " equal? "
                           + (a == b));
    }
}
```

### 案例 3：当 LHS 和 RHS 值都是引用值时

在这种情况下，对于两侧，当声明并初始化一个数组时，数据存储在堆内存中，而引用指针存储在堆栈存储器中。因此，两个变量比较的是它们的地址。如果两个变量指向相同的内存地址，则此运算符返回 `true`。否则返回 `false`。

**语法：**

```java
Address value == Address value
```

**示例：**

```java
// Java program for using == operator

import java.io.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring reference value
        int[] a = { 1, 2, 3, 4 };
        int[] b = { 1, 2, 3, 4 };
        int[] c = b;

        // Comparing a and b using == operator
        // Though they both have the same value
        // the output will be false because
        // they both have a different address in the memory
        System.out.println("Are " + a
                           + " and " + b
                           + " equal? "
                           + (a == b));

        // Comparing b and c using == operator
        // Though they both have the same value
        // the output will be true because
        // they both have same address in the memory
        System.out.println("Are " + b
                           + " and " + c
                           + " equal? "
                           + (b == c));
    }
}
```

**Output：**

```java
Are [I@232204a1 and [I@4aa298b7 equal? false
Are [I@4aa298b7 and [I@4aa298b7 equal? true
```