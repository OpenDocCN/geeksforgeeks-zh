# 检查给定类是否是匿名类的 Java 程序

> 原文：[https://www.geeksforgeeks.org/java-program-to-check-if-a-given-class-is-an-anonymous-class/](https://www.geeksforgeeks.org/java-program-to-check-if-a-given-class-is-an-anonymous-class/)

[匿名类](https://www.geeksforgeeks.org/anonymous-inner-class-java/)是没有名字的内部类。我们不能创建这个匿名类的实例，因为它们没有名字。

匿名内部类主要通过两种方式创建：
* 类（可以是抽象的或具体的）
* 接口

**语法：** 匿名类表达式的语法类似于构造函数的调用，只是代码块中包含一个类定义。

```java
// Test can be interface,abstract/concrete class
Test t = new Test() 
{
   // data members and methods
   public void test_method() 
   {
      ........
      ........
    }   
};
```

**可以通过两种方式创建对象：**

**1.** 通过调用类的构造函数。

```java
GFG gfg = new GFG();
```

**2.** 通过使用匿名类。

```java
GFG gfg = new GFG(){
    // An anonymous class that extends GFG class
}
```

上述两个对象都有效。现在，如果因为某些原因（调试、代码分析等）如果要检查该对象是否是使用匿名类创建的，可以使用以下方法之一：

## 方法 1

* 检查一个类是否匿名是最好的（也是最简单的！）方式是使用 `java.lang.Class` 类中定义的 `isAnonymousClass()` 库函数。
* 类的实例表示运行的 Java 应用程序中的类和接口。
* 所有类（因此它们的对象）都有一个 `getClass()` 方法（从 `java.lang.Object` 类继承而来），该方法返回代表该特定类的类实例。
* 使用 `getClass()` 方法，您可以访问它对应的类实例，然后可以调用它的 `isAnonymousClass()` 方法来检查它是否是一个匿名类。如果类是匿名类，则返回 `true`，否则返回 `false`。

执行以下代码：

```java
// Java program to check if a class is an anonymous class
// using isAnonymous() method
import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        // Creating an object by calling its default
        // constructor
        GFG obj = new GFG();

        // obj.getClass() returns the Class instance
        // representing obj's class(i.e. it represents the
        // GFG class) The Class instance has a method called
        // "isAnonymousClass()" (defined in java.lang.Class
        // class) Which returns true if obj's class is an
        // anonymous class
        // and false otherwise
        System.out.println(
            "Is obj a anonymous class? :"
            + obj.getClass().isAnonymousClass());

        // Creating an object using an anonymous class
        GFG object = new GFG() {
            // This is an anonymous class that extends the
            // GFG class
        }; // Remember to put the semicolon here

        System.out.println(
            "Is object an anonymous class? :"
            + object.getClass().isAnonymousClass());
    }
}
```

**Output**

```java
Is obj a anonymous class? :false
Is object an anonymous class? :true
```

## 方法 2

* 虽然第一种方法是检查给定类是否匿名的最好和直接的方法，但是我们可以使用不同的方法来实现同样的目的。
* 这种方法利用了**匿名类没有任何名字**的事实。
* 因此，如果您有一个对象，您可以检查它的类（表示为类实例）是否有名称。
* 我们知道类实例可以用来获取这个实例所代表的类的元数据。
* 如果我们有代表对象类的类实例的引用，我们可以通过调用 `getSimpleName()` 方法来获得类的名称。
* 此方法以字符串的形式返回相应类的简单名称。因此，如预期的那样，如果类是匿名类，此方法将返回空字符串（`""`）。因此，我们可以用这种方法来完成我们的任务。

```java
// Java program to check if the class is 
// anonymous or not using getSimpleName() method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        // Creating a GFG object by calling
        // its default constructor
        GFG obj = new GFG();

        // Note that getSimpleName() is defined in
        // java.lang.Class class

        // So you need to first call obj's getClass() method
        // and then call getSimpleName() method

        System.out.println(
            "Is obj an anonymous class object? :"
            + obj.getClass().getSimpleName().equals(""));
        // Check the above line carefully

        // getSimpleName() returns a string

        // So the equals() method of String is called
        // To check whether the name of the class
        // is empty or not

        // Creating an anonymous class

        GFG object = new GFG() {
            // This is an anonymous class that
            // extends the GFG class
        }; // Again remember to put the semicolon here

        System.out.println(
            "Is object an anonymous class object? :"
            + object.getClass().getSimpleName().equals(""));
    }
}
```

**Output**

```java
Is obj an anonymous class object? :false
Is object an anonymous class object? :true
```

**注：**

> * 如果您尝试在上面的代码中使用 `getName()` 方法而不是 `getSimpleName()` 方法，它将不起作用。
> * 在这种情况下，`getName()` 将返回 `GFG$1`（`GFG` 类中的第一个匿名类），这不是一个空字符串。
> * 因此，最后一行的条件将被评估为 `false`。
> * 如果您在 `GFG` 类中有另一个匿名类，如果您调用 `getName()` 方法，您将返回 `GFG$2`（`GFG` 类中的第二个匿名类）。