# 如何在 Java 中调用返回其他方法的方法

> 原文：[https://www.geeksforgeeks.org/how-to-call-a-method-that-returns-some-other-method-in-java/](https://www.geeksforgeeks.org/how-to-call-a-method-that-returns-some-other-method-in-java/)

一个[方法](https://www.geeksforgeeks.org/methods-in-java/)是执行一些特定任务并将结果返回给调用者的语句的集合。一个方法也可以在不返回任何东西的情况下执行一些特定的任务。在本文中，我们将了解如何在 Java 中调用返回其他方法的方法。

## 方法类型

在 Java 中，有两种类型的方法。它们是：

1.  **[static method](https://www.geeksforgeeks.org/static-methods-vs-instance-methods-java/)**：一个静态方法是可以在不创建类对象的情况下被调用的方法。它们通过类名本身或对类对象的引用进行引用。
2.  **[Instance method](https://www.geeksforgeeks.org/static-methods-vs-instance-methods-java/)**：实例方法是一种在调用前需要创建其类对象的方法。要调用实例方法，我们必须创建一个定义其类的对象。

## 调用一个静态方法返回一些其他静态方法

由于静态方法与它们所在的类相关联（即它们可以被调用，即使没有创建类的实例），我们可以通过调用方法的定义直接定义一个调用方法的方法。让我们通过以下示例来了解如何做到这一点：

### 示例 1

在这个例子中，让我们想象一辆汽车。汽车在驾驶前必须启动。因此，汽车具有启动汽车的启动功能。为了使汽车启动，其引擎必须首先启动，并且其他实体也必须启动，以便汽车最终准备好运行。因此，这个 `carStart()` 函数需要一个 `engineStart()` 来启动引擎。即，

```java
// Java program to visualize the Car

// A class Car
public class CarFunc {

    // A method engineStart() which
    // simply starts the engine
    public static void engineStart()
    {
        System.out.println("Engine Started!");
    }

    // A method carStart() which starts
    // the engine and other entities
    // required
    public static void carStart()
    {
        // Calling the function
        // engineStart() inside the
        // definition of function
        // carStart()
        engineStart();

        // Definitions of starting
        // various other entities
        // can be defined here

        // Finally, the car is
        // started
        System.out.println("Car Started!");
    }

    public static void main(String[] args)
    {
        carStart();

        // When the car is started,
        // we are ready to drive
        System.out.println("Let's Drive!");
    }
}
```

**输出：**

```java
Engine Started!
Car Started!
Let's Drive!
```