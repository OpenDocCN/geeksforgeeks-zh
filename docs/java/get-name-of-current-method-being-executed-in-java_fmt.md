# 获取当前正在Java中执行的方法名称

> 原文：[https://www.geeksforgeeks.org/get-name-of-current-method-being-executed-in-java/](https://www.geeksforgeeks.org/get-name-of-current-method-being-executed-in-java/)

获取当前执行方法的名称对于处理异常和调试非常有用。下面是获取当前执行方法的不同方法：

## 使用Throwable堆栈跟踪

使用`Throwable`类：在Java中，`Throwable`类是`java.lang`包中所有异常和错误的超类。Java `Throwable`类提供了多种方法，如`addSuppressed()`、`getMessage()`、`getStackTrace()`、`getSuppressed()`、`toString()`、`printStackTrace()`等。
我们可以通过在`Throwable`实例上调用`getStackTrace()`来获取一个表示与该可抛出对象相关的堆栈跟踪的堆栈跟踪元素数组。数组中索引为0的元素代表堆栈顶部，即序列中最近的方法调用。

```java
// Java program to demonstrate
// Getting name of current method 
// using Throwable Class
public class GFG {

    public static void foo()
    {
        // getStackTrace() method return
        // current method name at 0th index
        String nameofCurrMethod = new Throwable()
                                      .getStackTrace()[0]
                                      .getMethodName();

        System.out.println("Name of current method: "
            + nameofCurrMethod);
    }

    public static void main(String[] args)
    {
        // call function
        foo();
    }
}
```

**输出：**

```java
Name of current method: foo
```

### 使用异常类

我们还可以使用扩展`Throwable`类的`Exception`类。

```java
// Java program to demonstrate
// Getting name of current method 
// using Exception Class
public class GFG {

    public static void foo()
    {
        // getStackTrace() method return current
        // method name at 0th index
        String nameofCurrMethod = new Exception()
                                      .getStackTrace()[0]
                                      .getMethodName();

        System.out.println("Name of current method: " 
             + nameofCurrMethod);
    }

    public static void main(String[] args)
    {
        // call function
        foo();
    }
}
```

**输出：**

```java
Name of current method: foo
```

## 使用getEnclosingMethod()方法

### 通过Object类

我们可以使用`Class.getEnclosingMethod()`，此方法返回一个表示该类直接封闭方法的`Method`对象。但这会带来额外的开销，因为它在后台涉及创建一个新的匿名内部类。

```java
// Java program to demonstrate
// Getting name of current method 
// using Object Class
public class GFG {

    // create a static method foo
    public static void foo()
    {
        // this method return a Method object representing
        // the instantly enclosing method of the method class
        String nameofCurrMethod = new Object() {}
                                      .getClass()
                                      .getEnclosingMethod()
                                      .getName();

        System.out.println("Name of current method: " 
           + nameofCurrMethod);
    }

    public static void main(String[] args)
    {
        // call function
        foo();
    }
}
```

**输出：**

```java
Name of current method: foo
```

### 通过内部类

我们也可以在方法内部定义一个内部类来获取`Class`引用。

```java
// Java program to demonstrate
// Getting name of current method 
// using Inner Class
public class GFG {

    // create a static method foo
    public static void foo()
    {
        // Local inner class
        class Inner {
        };

        // this method return a Method object representing
        // the instantly enclosing method of the method class
        String nameofCurrMethod = Inner.class
                                      .getEnclosingMethod()
                                      .getName();

        System.out.println("Name of current method: "
              + nameofCurrMethod);
    }

    public static void main(String[] args)
    {
        // call function
        foo();
    }
}
```

**输出：**

```java
Name of current method: foo
//This java program on our machine because inner class
// have some restriction for security purpose
```

## 使用线程堆栈跟踪

`Thread.getStackTrace()`方法返回一个堆栈跟踪元素数组。返回数组的第二个元素包含当前线程的方法名称。

```java
// Java program to demonstrate
// Getting name of current method 
// using Thread.getStackTrace() 
public class GFG {

    // create a static method foo
    public static void foo()
    {
        // Thread.currentThread() return current method name
        // at 1st index in Stack Trace
        String nameofCurrMethod = Thread.currentThread()
                                      .getStackTrace()[1]
                                      .getMethodName();

        System.out.println("Name of current method: "
            + nameofCurrMethod);
    }

    public static void main(String[] args)
    {
        // call function
        foo();
    }
}
```

**输出：**

```java
Name of current method: foo
```