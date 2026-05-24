# Java 中 `==` 和 `equals()` 方法之间的差异

> 原文：[https://www.geeksforgeeks.org/difference-between-and-equals-method-in-java/](https://www.geeksforgeeks.org/difference-between-and-equals-method-in-java/)

在 Java 中，`equals()` 方法和 `==` 运算符都用于比较两个对象。`==` 是运算符，`equals()` 是方法。但是 `==` 运算符比较堆中对象的引用或内存位置，不管它们是否指向同一个位置。

每当我们使用运算符 `new` 创建一个对象时，它都会为该对象创建一个新的内存位置。因此，我们使用 `==` 运算符来检查两个对象的内存位置或地址是否相同。

一般来说，Java 中的 `equals()` 和 `==` 运算符都是用来比较对象来检查相等性的，但是这里有两者之间的一些区别：

1.  主要区别在于，`equals()` 方法是一个方法，而 `==` 是一个运算符。
2.  我们可以使用 `==` 运算符进行引用比较（地址比较），而 `equals()` 方法用于内容比较。简单来说，`==` 检查两个对象是否指向相同的内存位置。`equals()` 计算对象中值的比较。
3.  如果一个类没有重写 `equals` 方法，那么默认情况下，它会使用最近的、已经重写了该方法的父类的 `equals(Object o)` 方法。详见[为什么需要重写 `equals(Object)` 和 `hashCode()` 方法？](https://www.geeksforgeeks.org/override-equalsobject-hashcode-method/)。

## Java 代码示例

```java
// Java program to understand 
// the concept of == operator

public class Test {
    public static void main(String[] args)
    {
        String s1 = "HELLO";
        String s2 = "HELLO";
        String s3 = new String("HELLO");

        System.out.println(s1 == s2); // true
        System.out.println(s1 == s3); // false
        System.out.println(s1.equals(s2)); // true
        System.out.println(s1.equals(s3)); // true
    }
}
```

**输出**

```
true
false
true
true
```