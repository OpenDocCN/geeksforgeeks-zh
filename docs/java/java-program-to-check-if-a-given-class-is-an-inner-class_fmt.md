# 检查给定类是否是内部类的 Java 程序

> 原文：[https://www.geeksforgeeks.org/java-program-to-check-if-a-given-class-is-an-inner-class/](https://www.geeksforgeeks.org/java-program-to-check-if-a-given-class-is-an-inner-class/)

[内部类](https://www.geeksforgeeks.org/inner-class-java/)是另一个类的成员，这个类基本上是非静态嵌套类，也就是说，如果一个类在另一个类里面，并且不是静态的，那么这个类被调用就称为内部类。

## 内部类的类型

1.  [Nested inner class](https://www.geeksforgeeks.org/nested-classes-java/)
2.  Method [Local internal class](https://www.geeksforgeeks.org/local-inner-class-java/)
3.  [Anonymous inner class](https://www.geeksforgeeks.org/anonymous-inner-class-java/)
4.  [Static nested class](https://www.geeksforgeeks.org/nested-classes-java/)

## 方法 1

1.  首先，检查给定类是否是嵌套类。
2.  进一步检查该类是否是非静态的。
    *   如果两个条件都为真，那么给定的类就是一个内部类。
3.  现在，为了检查给定类是否是嵌套类，我们使用 [`java.lang.Class#getEnclosingClass()`](https://www.geeksforgeeks.org/class-getenclosingclass-method-in-java-with-examples/) 方法，该方法返回一个 [`Class`](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/) 实例，代表该对象的直接封闭类。
    *   如果该类是顶层类，则此方法将返回 `null`。
    *   这意味着如果类不是嵌套的，该方法返回 `null`。
4.  进一步使用[该方法检查给定类是否是静态的](https://www.geeksforgeeks.org/modifier-isstaticmod-method-in-java-with-examples/)。

程序用于检查嵌套的内部类。

```java
// Java Program to Check if a Given Class is an Inner Class

// Importing package where Modifier is defined
import java.lang.reflect.Modifier;

class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating as GFG class object
        GFG gfg = new GFG();

        // Creating a InnerClass object
        InnerClass innerClass = gfg.new InnerClass();

        // Creating a Static Nested Class object
        StaticNestedClass statNested
            = new StaticNestedClass();

        // getClass() method of an object returns a
        // java.lang.Class instance representing the class
        // of the object
        Class classInstance1 = innerClass.getClass();
        Class classInstance2 = statNested.getClass();

        // Checking if the given classes are nested

        // getEnclosingClass() of Class instance returns a
        // class object representing the immediate enclosing
        // class of the instance
        boolean isNested1
            = classInstance1.getEnclosingClass() != null;
        // If the specified class is a top-level class, then
        // it would return null

        boolean isNested2
            = classInstance2.getEnclosingClass() != null;

        // Check if the given classes are static

        // getModifiers() method of a class returns the
        // modifiers of the class encoded as an integer

        // Modifier.isStatic returns true if the class
        // has a static modifier else returns false
        boolean isStatic1 = Modifier.isStatic(
            classInstance1.getModifiers());
        boolean isStatic2 = Modifier.isStatic(
            classInstance2.getModifiers());

        // If the given classes are nested and non-static,
        // then given classes are surely inner classes

        // Display message
        System.out.println(
            "Is innerClass an inner class object? : "
            + (isNested1 && !isStatic1));

        // Display message
        System.out.println(
            "Is statNested an inner class object? : "
            + (isNested2 && !isStatic2));
    }

    // Inner Class
    class InnerClass {
    }

    // Static nested class
    static class StaticNestedClass {
    }
}
```

**输出**

```java
Is innerClass an inner class object? : true
Is statNested an inner class object? : false
```