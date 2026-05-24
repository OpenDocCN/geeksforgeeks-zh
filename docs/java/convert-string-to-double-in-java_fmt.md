# 在 Java 中将字符串转换为双精度

> 原文: [https://www.geeksforgeeks.org/convert-string-to-double-in-java/](https://www.geeksforgeeks.org/convert-string-to-double-in-java/)

给定一个字符串，任务是在 Java 中将其转换为 `Double`。

**示例:**

```java
Input: String = "20.156"
Output: 20.156

Input: String = "456.21"
Output: 456.21
```

我们可以使用各种方法来执行任务:

## 1. 使用 `Double.parseDouble()`

**语法:**

```java
double str1 = Double.parseDouble(str);
```

**示例:**

```java
// Java program to convert String to Double
// using parseDouble()

public class GFG {

    // main method
    public static void main(String args[])
    {
        // create a String
        String str = "2033.12244";

        // convert into Double
        double str1 = Double.parseDouble(str);

        // print String as Double
        System.out.println(str1);
    }
}
```

**Output:**

```java
2033.12244
```

## 2. 使用 `Double.valueOf()`

**语法:**

```java
double str1 = Double.valueOf(str);
```

**示例:**

```java
// Java program to convert String to Double
// using valueOf()

public class GFG {

    // main method
    public static void main(String args[])
    {
        // create a String
        String str = "2033.12244";

        // convert into Double
        double str1 = Double.valueOf(str);

        // print String as Double
        System.out.println(str1);
    }
}
```

**Output:**

```java
2033.12244
```

## 3. 使用 `Double` 类的构造函数

**语法:**

```java
Double str1 = new Double(str);
```

**示例:**

```java
// Java program to convert String to Double
// using Double constructor

public class GFG {

    // main method
    public static void main(String args[])
    {
        // create a String
        String str = "2033.12244";

        // convert into Double
        Double str1 = new Double(str);

        // print String as Double
        System.out.println(str1);
    }
}
```

**Output:**

```java
2033.12244
```