# Java 中的 `Class.forName(String, boolean, ClassLoader)` 方法示例

> 原文：[https://www.geeksforgeeks.org/class-fornamestring-boolean-classloader-method-in-java-with-examples/](https://www.geeksforgeeks.org/class-fornamestring-boolean-classloader-method-in-java-with-examples/)

[`Class.forName(String, boolean, ClassLoader)`](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/) 方法用于使用指定的类加载器获取具有指定类名的类的实例。只有当 `initialize` 参数为 `true` 并且该类之前没有初始化过时，该类才会初始化。

## 语法

```java
public static Class<T> forName(String className, 
                                boolean initialize, 
                                ClassLoader classLoader) 
                                throws ClassNotFoundException
```

## 参数

该方法接受以下参数：

*   `className`：是需要其实例的类。
*   `initialize`：一个布尔状态，指示此类实例是否需要初始化。
*   `classLoader`：是必须从中加载该类的类加载器。

## 返回值

该方法返回使用指定参数获取的该类的实例。

## 异常

此方法抛出以下异常：

*   `LinkageError`：如果链接失败。
*   `ExceptionInInitializerError`：如果此方法引发的初始化失败。
*   `ClassNotFoundException`：如果找不到该类。
*   `SecurityException`：如果存在安全管理器，并且加载程序为空，并且调用者的类加载程序不为空，并且调用者没有 `RuntimePermission("getClassLoader")`。

下面的程序演示了 `forName()` 方法。

### 示例 1

```java
// Java program to demonstrate forName() method

public class Test {
    public static void main(String[] args)
        throws ClassNotFoundException
    {
        // returns the Class object for this class
        Class myClass = Class.forName("Test");

        ClassLoader loader = myClass.getClassLoader();

        // get the Class instance using forName method
        Class c1 = Class.forName("java.lang.String",
                                 true,
                                 loader);

        System.out.print("Class represented by c1: "
                         + c1.toString());
    }
}
```

**输出：**

```java
Class represented by c1: class java.lang.String
```

### 示例 2

```java
// Java program to demonstrate forName() method

public class Test {
    public static void main(String[] args)
        throws ClassNotFoundException
    {
        // returns the Class object for this class
        Class myClass = Class.forName("Test");

        ClassLoader loader = myClass.getClassLoader();

        // get the Class instance using forName method
        Class c1 = Class.forName("java.lang.Integer",
                                 false,
                                 loader);

        System.out.print("Class represented by c1: "
                         + c1.toString());
    }
}
```

**输出：**

```java
Class represented by c1: class java.lang.Integer
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/lang/Class.html#forName-java.lang.String-boolean-java.lang.ClassLoader-](https://docs.oracle.com/javase/9/docs/api/java/lang/Class.html#forName-java.lang.String-boolean-java.lang.ClassLoader-)