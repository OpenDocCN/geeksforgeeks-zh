# 将 Lambdas 与 Java 中的接口进行匹配

> 原文：[https://www.geeksforgeeks.org/match-lambdas-to-interfaces-in-java/](https://www.geeksforgeeks.org/match-lambdas-to-interfaces-in-java/)

最受欢迎和最重要的话题之一是 Java 中的 [`lambda` 表达式](https://www.geeksforgeeks.org/lambda-expressions-java-8/)。但是在直接进入我们的讨论之前，让我们对一些重要的事情有所了解。从 Java 中的接口开始，引用类型类似于类，但只包含抽象方法。这是我们在 Java 1.8 之前对接口的定义。在 Java 1.8 版本之前，接口有三种类型，即如下所示：

*   普通接口
*   多方法接口。
*   标签接口（该接口不包含任何方法）。

> 从 1.8 开始，所有 SAM（单一抽象方法）接口被称为*函数式接口*。

**函数式接口：** 函数式接口是一个只包含一个抽象方法的接口，但重要的一点是要记住，它可以有任意数量的默认方法或静态方法以及 `Object` 类方法，因为这最让程序员困惑。

**例：**

## Java

```java
// Java Program to Illustrate Functional Interface

// Importing required classes
import java.io.*;

// Interface
@FunctionalInterface
interface display {

    // Attribute
    void show(String msg);

    // Method
    // To compute the sum
    default int doSum(int a, int b) { return a + b; }
}

// Main class implementing the above interface
class GFG implements display {

    // Overriding the existing show() method
    @Override
    public void show(String msg)
    {
        // Print message
        System.out.println(msg);
    }

    // Main driver method
    public static void main(String[] args)
    {
        // Creating object of class inside main()
        GFG object = new GFG();

        // Calling show() method in main()
        object.show("Hello World!");

        // Print statement
        System.out.println(object.doSum(2, 3));
    }
}
```

**输出**

```java
Hello World!
5
```