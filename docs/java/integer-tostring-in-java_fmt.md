# Java 中的整数 toString()

> 原文:[https://www.geeksforgeeks.org/integer-tostring-in-java/](https://www.geeksforgeeks.org/integer-tostring-in-java/)

## 1. `java.lang.Integer.toString()`

`java.lang.Integer.toString()` 是 Java 中的一个内置方法，用于返回表示此 `Integer` 值的 `String` 对象。

**语法:**

```java
public static String toString()
```

**参数:** 该方法不接受任何参数。

**返回值:** 该方法返回特定整数值的字符串对象。

下面的程序说明了 `Java.lang.Integer.toString()` 方法:

```java
// Java program to illustrate the
// toString() Method
import java.lang.*;

public class Geeks{
    public static void main(String[] args) {
        Integer obj = new Integer(8);
        //It will return a string representation     
        String stringvalue1 = obj.toString();
        System.out.println("String Value= " + 
                            stringvalue1);

        Integer obj3 = new Integer(10);
        //It will return a string representation 
        String stringvalue3 = obj3.toString();
        System.out.println("String Value = " + 
                            stringvalue3);
    }
}
```

**Output:**

```java
String Value= 8
String Value = 10
```

## 2. `java.lang.Integer.toString(int a)`

`java.lang.Integer.toString(int a)` 是 Java 中的一个内置方法，用于返回一个 `String` 对象，表示参数中指定的整数。

**语法:**

```java
public static String toString(int a)
```

**参数:** 该方法接受一个整数类型的参数 `a`，指需要转换为字符串的整数。

**返回值:** 该方法返回特定基中参数的字符串表示形式。

**示例:**

```java
For base 8: 
Input: int a = 75 
Output: "75"

For base 10:
Input: int a = -787 
Output: "-787"
```

以下程序说明了 `Java.lang.Integer.toString(int a)` 方法:

**程序 1:**

```java
// Java program to illustrate the
// toString(int a) method
import java.lang.*;

public class Geeks{
    public static void main(String[] args) {
        Integer obj = new Integer(8);
        // It will return a string representation
        // in base 8
        String stringvalue1 = obj.toString(75);
        System.out.println("String Value = " + 
                            stringvalue1);

        Integer obj2 = new Integer(8);
        // It will return a string representation
        // in base 2
        String stringvalue2 = obj2.toString(6787);
        System.out.println("String Value = " + 
                            stringvalue2);

        Integer obj3 = new Integer(10);
        // It will return a string representation 
        // in base 10
        String stringvalue3 = obj3.toString(-787);
        System.out.println("String Value = " + 
                            stringvalue3);
    }
}
```

**Output:**

```java
String Value = 75
String Value = 6787
String Value = -787
```

**程序 2:** 用于十进制和字符串参数。
**注意:** 这将导致一个错误，以及缺少合适的整数构造函数。

```java
// Java program to illustrate the
// Java.lang.Integer.toString(int a)method
import java.lang.*;
public class Geeks{
    public static void main(String[] args) {
        Integer obj = new Integer(8);    
        String stringvalue1 = obj.toString(58.5);
        System.out.println("String Value = " + 
                            stringvalue1);

        Integer obj2 = new Integer(8);    
        String stringvalue2 = obj2.toString("317");
        System.out.println("String Value = " + 
                            stringvalue2);

        // Empty constructor will result in an error
        Integer obj3 = new Integer();
        String stringvalue3 = obj3.toString(-787);
        System.out.println("String Value = " + 
                            stringvalue3);
    }
}
```

**输出:**

```java
prog.java:8: error: incompatible types: possible 
lossy conversion from double to int
    String stringvalue1 = obj.toString(58.5);
                                       ^
prog.java:12: error: incompatible types: String cannot 
be converted to int
    String stringvalue2 = obj2.toString("317");
                                        ^
prog.java:17: error: no suitable constructor found for 
Integer(no arguments)
    Integer obj3 = new Integer();
                   ^
    constructor Integer.Integer(int) is not applicable
      (actual and formal argument lists differ in length)
    constructor Integer.Integer(String) is not applicable
      (actual and formal argument lists differ in length)
Note: Some messages have been simplified; recompile with 
-Xdiags:verbose to get full output
3 errors
```

## 3. `java.lang.Integer.toString(int a, int base)`

`java.lang.Integer.toString(int a, int base)` 是 Java 中的一个内置方法，用于返回参数 `a` 在由第二个参数 `base` 指定的基数中的字符串表示形式。如果基数/进制小于 `Character.MIN_RADIX` 或大于 `Character.MAX_RADIX`，则使用基数 10。用作数字的 ASCII 字符：0 到 9 和 a 到 z。

**语法:**

```java
public static String toString(int a, int base)
```

**参数:** 该方法接受两个参数:

*   `a` : 这是整数类型，指的是要转换的整数值。
*   `基数`: 这也是整数类型，指的是表示字符串时要使用的基数。

**返回值:** 该方法返回指定基中指定参数的字符串表示形式。

**示例:**

```java
Input: a = 71, base = 2
Output: 1000111

Input: a = 314, base = 16
Output: 13a
```

下面的程序说明了方法:

**程序 1:**

```java
// Java program to illustrate the
// toString(int, int) Method
import java.lang.*;

public class Geeks{
    public static void main(String[] args) {
        Integer a = new Integer(10);
        // It returns a string representation 
        // in base 2
        String returnvalue = a.toString(5254, 2);
        System.out.println("String Value = " + 
                            returnvalue);

        // It returns a string representation 
        // in base 8
        returnvalue = a.toString(35, 8);
        System.out.println("String Value = " + 
                            returnvalue);

        // It returns a string representation 
        // in base 16
        returnvalue = a.toString(47, 16);
        System.out.println("String Value = " + 
                            returnvalue);

        // It returns a string representation 
        // in base 10
        returnvalue = a.toString(451, 10);
        System.out.println("String Value = " + 
                            returnvalue);
    }
}
```

**Output:**

```java
String Value = 1010010000110
String Value = 43
String Value = 2f
String Value = 451
```

**程序 2:**

```java
// Java program to illustrate the
// toString(int, int) Method
import java.lang.*;

public class Geeks{
    public static void main(String[] args) {
        Integer a = new Integer(10);
        // It returns a string representation 
        // in base 2
        String returnvalue = a.toString(-525, 2);
        System.out.println("String Value = " + 
                            returnvalue);

        // It returns a string representation 
        // in base 8
        returnvalue = a.toString(31, 8);
        System.out.println("String Value = " + 
                            returnvalue);

        // It returns a string representation 
        // in base 16
        returnvalue = a.toString(28, 16);
        System.out.println("String Value = " + 
                            returnvalue);

        // It returns a string representation 
        // in base 10
        returnvalue = a.toString(29, 10);
        System.out.println("String Value = " + 
                            returnvalue);
    }
}
```

**Output:**

```java
String Value = -1000001101
String Value = 37
String Value = 1c
String Value = 29
```