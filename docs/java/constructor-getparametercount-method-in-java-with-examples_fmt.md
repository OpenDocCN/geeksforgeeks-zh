# Java中构造函数getParameterCount()方法示例

> 原文：[https://www.geeksforgeeks.org/constructor-getparametercount-method-in-java-with-examples/](https://www.geeksforgeeks.org/constructor-getparametercount-method-in-java-with-examples/)

`java.lang.reflect.Constructor`类的`getParameterCount()`方法用于返回此构造函数对象上存在的参数数量。每个构造函数都包含从零到多个参数。这种方法有助于获得这些数量的参数。

## 语法

```java
public int getParameterCount()
```

**参数：** 此方法不接受任何内容。

**返回：** 该方法返回该对象所代表的可执行文件的形式参数的数量。

下面的程序说明了`getParameterCount()`方法：

## 程序1

```java
// Java program to illustrate getParameterCount() method

import java.lang.reflect.Constructor;

public class GFG {

    public static void main(String[] args)
    {
        // create a class object
        Class classObj = String.class;

        // get Constructor object
        // array from class object
        Constructor[] cons = classObj.getConstructors();

        // get count of parameter
        int params = cons[0].getParameterCount();

        // print parameter count
        System.out.println("No of Parameters: " + params);
    }
}
```

**Output:**

```java
No of Parameters: 3
```

## 程序2

```java
// Java program to illustrate getParameterCount() method

import java.lang.reflect.Constructor;
import java.util.ArrayList;

public class GFG {

    public static void main(String[] args)
    {
        // create a class object
        Class classObj = ArrayList.class;

        // get Constructor object
        // array from class object
        Constructor[] cons = classObj.getConstructors();

        for (int i = 0; i < cons.length; i++) {
            // get count of parameter
            int params = cons[i].getParameterCount();

            // print parameter count
            System.out.println(
                cons[i].toGenericString()
                + "-> parameter count = " + params);
        }
    }
}
```

**Output:**

```java
public java.util.ArrayList(java.util.Collection)-> parameter count = 1
public java.util.ArrayList()-> parameter count = 0
public java.util.ArrayList(int)-> parameter count = 1
```

**参考文献：** [https://docs.oracle.com/javase/10/docs/api/java/lang/reflect/Constructor.html#getParameterCount()](https://docs.oracle.com/javase/10/docs/api/java/lang/reflect/Constructor.html#getParameterCount())