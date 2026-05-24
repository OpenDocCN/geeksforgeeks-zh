# Java 中的 `Class.getDeclaredMethods()` 方法，带示例

> 原文：[https://www.geeksforgeeks.org/class-getdeclaredmethods-method-in-java-with-examples/](https://www.geeksforgeeks.org/class-getdeclaredmethods-method-in-java-with-examples/)

[`java.lang.Class`](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/) 类的 `getDeclaredMethods()` 方法用于获取该类声明的方法，这些方法是私有的、公共的、受保护的或默认的，包括该类自身、其成员类和接口的成员，但不包括继承的方法。方法以 `Method` 对象数组的形式返回。

## 语法

```java
public Method[] getDeclaredMethods()
               throws SecurityException
```

## 参数

此方法不接受任何参数。

## 返回值

此方法以 `Method` 对象数组的形式返回这个类的所有声明方法。

## 异常

如果存在安全管理器且安全条件不满足，此方法将抛出 `SecurityException`。

## 示例

下面的程序演示了 `getDeclaredMethods()` 方法。

### 例 1

```java
// Java program to demonstrate getDeclaredMethods() method

import java.util.*;

public class Test {
    public static void main(String[] args)
        throws ClassNotFoundException
    {
        // returns the Class object for this class
        Class myClass = Class.forName("Test");

        System.out.println("Class represented by myClass: "
                           + myClass.toString());

        // Get the methods of myClass
        // using getDeclaredMethods() method
        System.out.println(
            "DeclaredMethods of myClass: "
            + Arrays.toString(
                  myClass.getDeclaredMethods()));
    }
}
```

**输出：**

> 由 myClass 表示的类：`class Test`
> DeclaredMethods of myClass: `[public static void Test.main(java.lang.String[]) throws java.lang.ClassNotFoundException]`

### 例 2

```java
// Java program to demonstrate getDeclaredMethods() method

import java.util.*;

class Main {

    public Object obj;

    private void function() {}

    Main()
    {
        class Arr {
        };

        obj = new Arr();
    }

    public static void main(String[] args)
        throws ClassNotFoundException
    {
        // returns the Class object for this class
        Class myClass = Class.forName("Main");

        System.out.println("Class represented by myClass: "
                           + myClass.toString());

        // Get the methods of myClass
        // using getDeclaredMethods() method
        System.out.println(
            "DeclaredMethods of myClass: "
            + Arrays.toString(
                  myClass.getDeclaredMethods()));
    }
}
```

**输出：**

> 由 myClass 表示的类：`class Main`
> DeclaredMethods of myClass: `[public static void Main.main(java.lang.String[]) throws java.lang.ClassNotFoundException, private void Main.function()]`

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/lang/Class.html#getDeclaredMethods--](https://docs.oracle.com/javase/9/docs/api/java/lang/Class.html#getDeclaredMethods--)