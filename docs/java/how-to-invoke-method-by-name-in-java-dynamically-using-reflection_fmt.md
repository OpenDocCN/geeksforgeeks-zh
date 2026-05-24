# 如何利用反射动态调用 Java 中的方法名？

> 原文: [https://www.geeksforgeeks.org/how-to-invoke-method-by-name-in-java-dynamically-using-reflection/](https://www.geeksforgeeks.org/how-to-invoke-method-by-name-in-java-dynamically-using-reflection/)

Java [反射 API](https://www.geeksforgeeks.org/reflection-in-java/#:~:text=Reflection%20is%20an%20API%20which,reflect%20package.&text=Through%20reflection%20we%20can%20invoke,access%20specifier%20used%20with%20them.) 为我们提供了关于对象所属类的信息，包括这个类中的方法。使用这些反射应用编程接口，我们将能够获得类中方法的调用指针及其名称。

有两个函数用于此目的：

1.  调用名称为 `getDeclaredMethod()` 的方法。
2.  `getDeclaredMethods()` 方法通过名称在类中查找方法并调用它。

## 1. 调用名称为 `getDeclaredMethod()` 的方法

`getDeclaredMethod()` 就是为此而使用的。

**语法：**

```java
Class.getDeclaredMethod(“method name”, parameterType)
```

-   **方法名：** 我们想通过名字找到的方法。
-   **参数类型：** 方法接受的参数类型。
-   **返回类型：** 该方法将返回一个引用该方法地址的对象，该地址随后将用于调用该方法。我们将为此使用 `invoke` 方法。

如果有许多同名的重载方法，编译器将调用与参数匹配的方法。

### 调用功能

`invoke` 将用于使用方法对象调用方法。

**语法：**

```java
Method.invoke(classObj, param1, param2…)
```

-   **方法对象：** 从 `getDeclaredMethod` 返回的方法的对象。
-   **参数：** 用于调用方法的参数值。如果该方法没有任何要传递的参数，那么我们将在这里传递 `null`。

**示例**

```java
// Java program to invoke method with its name
// using Reflection API

import java.io.*;
import java.lang.reflect.InvocationTargetException;
import java.lang.reflect.Method;
import java.lang.reflect.Type;

class GFG {
    public void printMessage(String message)
    {
        System.out.println(
            "you invoked me with the message:" + message);
    }

    public static void main(String[] args) throws Exception
    {
        System.out.println("Invoke method by Name in Java using Reflection!");

        // create class object to get its details
        GFG obj = new GFG();
        Class<?> classObj = obj.getClass();

        // get method object for "printMessage" function by name
        Method printMessage = classObj.getDeclaredMethod("printMessage", String.class);

        try {
            // invoke the function using this class obj
            // pass in the class object
            printMessage.invoke(obj, "hello");
        }
        catch (InvocationTargetException e)
        {
            System.out.println(e.getCause());
        }
    }
}
```

**输出：**

```java
Invoke method by Name in Java using Reflection!
you invoked me with the message:hello
```

## 2. 在一个类中通过名称找到一个方法并调用相同的方法

如果我们不知道确切的方法参数，我们也可以获取类中的所有方法，并按名称搜索方法，然后获取其详细信息。

-   我们将使用 `getDeclaredMethods()` API 来做同样的事情。这将返回类中方法对象的数组。
-   我们可以使用它来遍历方法对象，并使用 `getName()` 根据其名称查找方法。
-   然后我们将使用 `getGenericParameterTypes()` 来查找它需要的参数，并使用 `getGenericReturnType()` 来查找其返回类型。
-   一旦我们有了参数和返回类型，我们将使用上面提到的 `invoke` 函数来调用该方法。

**语法：**

```java
Method[] methods = Class.getDeclaredMethods()
```

**示例：**

```java
// Java program of Finding a method by Name in a class
// and invoking the same

import java.io.*;
import java.lang.reflect.InvocationTargetException;
import java.lang.reflect.Method;
import java.lang.reflect.Type;

class GeeksForGeeks {
    public void printMessage(String message)
    {
        System.out.println(
            "you invoked me with the message:" + message);
    }

    public void addMe(int num1, int num2)
    {
        System.out.println("sum is:" + (num1 + num2));
    }

    public static void main(String[] args) throws Exception
    {
        System.out.println("Find method by Name in Java using Reflection!");

        // create class object to get its details
        GeeksForGeeks obj = new GeeksForGeeks();
        Class classObj = obj.getClass();

        // get all methods in the class
        Method[] allMethods = classObj.getDeclaredMethods();

        // loop through the methods to find the method addMe
        for (Method m : allMethods) {
            String methodName = m.getName();
            if (methodName.equals("addMe")) {
                try {
                    // invoke the method directly with its parameters
                    m.invoke(obj, 10, 20);
                }
                catch (InvocationTargetException e) {
                }
            }
        }
    }
}
```

**输出：**

```java
Find method by Name in Java using Reflection!
sum is:30
```

### 调用方法抛出异常

当被调用的基础方法抛出异常时，调用方法将抛出 `InvocationTargetException`。我们将能够通过使用 `InvocationTargetException` 的 `getCause()` 方法来检索该方法的异常。