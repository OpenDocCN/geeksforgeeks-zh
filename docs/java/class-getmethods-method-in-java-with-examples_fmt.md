
# 用示例在 Java 中类 getMethods()方法

> 原文: [https://www.geeksforgeeks.org/class-getmethods-method-in-java-with-examples/](https://www.geeksforgeeks.org/class-getmethods-method-in-java-with-examples/)

[`java.lang.Class`](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/) 类的 `getMethods()` 方法用于获取该类的方法，这些方法是公共的及其成员或者其成员类和接口的成员。方法以方法对象数组的形式返回此类的方法。

## 语法

```java
public Method[] getMethods()
```

## 参数

此方法不接受任何参数。

## 返回值

这个方法以 `Method` 对象数组的形式返回这个类的**方法**。

## 异常

如果有安全经理在场且不满足安全条件，此方法抛出 `SecurityException`。

下面的程序演示了 `getMethods()` 方法。

## 例 1

```java
// Java program to demonstrate getMethods() method

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
        // using getMethods() method
        System.out.println("Methods of myClass: "
                           + Arrays.toString(
                                 myClass.getMethods()));
    }
}
```

**Output:**

> 由 myClass 表示的类: class Test
> my class 的方法:[
> public static void Test.main(java.lang.String[]) throws java.lang.ClassNotFoundException,
> public final void java.lang.Object.wait(long,int) throws java.lang.InterruptedException,
> public final native void java.lang.Object.wait(long) throws java.lang.InterruptedException,
> public final void java.lang.Object.wait() throws java.lang.InterruptedException,

## 例 2

```java
// Java program to demonstrate getMethods() method

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
        Main t = new Main();

        // returns the Class object
        Class myClass = t.obj.getClass();

        // Get the methods of myClass
        // using getMethods() method
        System.out.println("Methods of myClass: "
                           + Arrays.toString(
                                 myClass.getMethods()));
    }
}
```

**Output:**

> myClass 的方法:[
> public static void test.main(java.lang.String[]) throws java.lang.ClassNotFoundException,
> public final void java.lang.Object.wait(long,int) throws java.lang.InterruptedException,
> public final native void java.lang.Object.wait(long) throws java.lang.InterruptedException,
> public boolean java.lang.Object.

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/lang/Class.html#getMethods--](https://docs.oracle.com/javase/9/docs/api/java/lang/Class.html#getMethods--)
