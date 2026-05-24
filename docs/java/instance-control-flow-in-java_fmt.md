# Java 中的实例控制流

> 原文：[https://www.geeksforgeeks.org/instance-control-flow-in-java/](https://www.geeksforgeeks.org/instance-control-flow-in-java/)

本文将解释每当创建对象时实例控制流是如何发生的。

## 实例控制流概述

每当我们执行 `java` 类文件时，将执行第一个[静态控制流](https://www.geeksforgeeks.org/static-control-flow-in-java/)。在静态控制流中，如果我们正在创建一个对象，以下步骤序列将作为实例控制流的一部分执行：

1.  从上到下识别实例成员。
2.  从上到下执行实例变量赋值和实例块。
3.  执行构造函数。

### 普通类中的实例控制流

**例：**

```java
// InstanceControlFlow class
class InstanceControlFlow {

    // initializing instance integer i = 10
    int i = 10;

    // first instance block
    {
        // call instance method (methodeOne())
        methodOne();
        System.out.println("First Instance Block");
    }

    // constructor
    InstanceControlFlow()
    {
        System.out.println("Constructor");
    }

    // main method
    public static void main(String[] args)
    {
        // create InstanceControlFlow class object
        InstanceControlFlow f = new InstanceControlFlow();
        System.out.println("Main method");
    }

    // instance method (methodOne())
    public void methodOne() { System.out.println(j); }

    // second instance block
    {
        System.out.println("Second Instance Block");
    }

    // initializing instance integer j = 20
    int j = 20;
}
```

**输出**

```java
First Instance Block
Second Instance Block
Constructor
Main method
```