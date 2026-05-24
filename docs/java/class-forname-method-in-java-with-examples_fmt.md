# Java Class.forName() 方法详解与示例

> 原文：[https://www.geeksforgeeks.org/class-forname-method-in-java-with-examples/](https://www.geeksforgeeks.org/class-forname-method-in-java-with-examples/)

[`java.lang.Class`](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/) 类的 `forName()` 方法用于获取具有指定类名的该类的实例。该类名被指定为字符串参数。

## 语法

```java
public static Class<T> forName(String className) throws ClassNotFoundException
```

## 参数
该方法接受参数 `className`，这是需要其实例的类。

## 返回值
这个方法用指定的类名返回这个类的实例。

## 异常
此方法抛出以下异常：
*   `LinkageError`：如果链接失败。
*   `ExceptionInInitializerError`：如果此方法引发的初始化失败。
*   `ClassNotFoundException`：如果找不到该类。

下面的程序演示了 `forName()` 方法。

## 示例 1

```java
// Java program to demonstrate forName() method

public class Test {
    public static void main(String[] args)
        throws ClassNotFoundException
    {
        // get the Class instance using forName method
        Class c1 = Class.forName("java.lang.String");

        System.out.print("Class represented by c1: "
                         + c1.toString());
    }
}
```

**输出：**

```java
Class represented by c1: class java.lang.String
```