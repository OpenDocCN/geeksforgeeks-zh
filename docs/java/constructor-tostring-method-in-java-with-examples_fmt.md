# Java 中的构造函数 `toString()` 方法示例

> 原文: [https://www.geeksforgeeks.org/constructor-tostring-method-in-java-with-examples/](https://www.geeksforgeeks.org/constructor-tostring-method-in-java-with-examples/)

`java.lang.reflect.Constructor` 类的 `toString()` 方法用于返回该构造函数的字符串表示。此字符串是此构造函数所有属性的集合。为了创建这个字符串，方法会使用构造函数的声明类的名称、构造函数的访问修饰符、括号以及构造函数的形式参数类型的逗号分隔列表。

## 语法

```java
public String toString()
```

## 参数

此方法不接受任何参数。

## 返回值

此方法返回描述此构造函数的 `String`。

下面的程序说明了 `toString()` 方法：

### 程序 1

```java
// Java program to illustrate toString() method

import java.lang.annotation.Annotation;
import java.lang.reflect.Constructor;

public class GFG {

    public static void main(String[] args)
    {
        // create a class object
        Class classObj = shape.class;

        // get Constructor object
        // array from class object
        Constructor[] cons = classObj.getConstructors();

        // check get string representation
        String str = cons[0].toString();

        // print result
        System.out.println("Constructor : " + str);
    }

    public class shape {

        public shape(Object... objects)
        {
        }
    }
}
```

**输出:**

```java
Constructor : public GFG$shape(GFG, java.lang.Object[])
```

### 程序 2

```java
// Java program to illustrate toString() method

import java.lang.annotation.Annotation;
import java.lang.reflect.Constructor;

public class GFG {

    public static void main(String[] args)
    {
        // create a class object
        Class classObj = String.class;

        // get Constructor object
        // array from class object
        Constructor[] cons = classObj.getConstructors();

        for (int i = 0; i < cons.length; i++) {

            String str = cons[i].toString();

            // print result
            System.out.println(str);
        }
    }
}
```

**输出:**

> public java.lang.String(byte[],int,int)
> public java.lang.String(byte[],java.nio.charset.Charset)
> public java.lang.String(byte[],java.lang.String) throws java.io.UnsupportedEncodingException
> public java.lang.String(byte[],int,int,java.lang.String) throws java.io.

## 参考文献

[https://docs.oracle.com/javase/10/docs/api/java/lang/reflect/Constructor.html#toString()](https://docs.oracle.com/javase/10/docs/api/java/lang/reflect/Constructor.html#toString())