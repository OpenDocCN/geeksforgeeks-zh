# 使用三元运算符寻找三个数中最大值的 Java 程序

> 原文：[https://www.geeksforgeeks.org/java-program-to-find-largest-between-three-numbers-using-ternary-operator/](https://www.geeksforgeeks.org/java-program-to-find-largest-between-three-numbers-using-ternary-operator/)

Java 提供了很多[运算符](https://www.geeksforgeeks.org/operators-in-java/)，其中一个这样的运算符是[三元运算符](https://www.geeksforgeeks.org/java-ternary-operator-with-examples/)。这是对 `if-else` 语句的线性替换。因此，它是一个非常有用的运算符，与 `if-else` 语句相比，它使用的**空间更少**。

## 三元运算符语法

```java
variable = condition ? expression1 : expression2 ;
```

## 同样的语句可以写成 if-else 语句如下

```java
if(condition){
      variable = expression1 ;
}
else{
      variable = expression2 ;
}
```

给定三个数，我们只需要用三元运算符就可以找到其中的最大值。

## 例

```java
Input : a = 15 , b = 10 , c = 45
Output : 45

Input : a = 31 , b = 67 , c = 23
Output : 67
```

这样，我们就可以利用**嵌套三元运算符**找到 3 个数的最大值如下所示：

```java
// Java program to find largest of three numbers
// using ternary operator

public class GFG {
    public static void main(String[] args) {
        int a = 15, b = 45, c = 34;
        int largest = (a > b) ? (a > c ? a : c) : (b > c ? b : c);
        System.out.println(largest);
    }
}
```

**输出**

```
45
```