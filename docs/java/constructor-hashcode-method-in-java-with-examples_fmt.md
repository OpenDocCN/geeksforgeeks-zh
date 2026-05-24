# Java 中的构造函数 hashCode() 方法示例

> 原文: [https://www.geeksforgeeks.org/constructor-hashcode-method-in-java-with-examples/](https://www.geeksforgeeks.org/constructor-hashcode-method-in-java-with-examples/)

`java.lang.reflect.Constructor` 类的 `hashCode()` 方法用于返回此 `Constructor` 对象的 `hashCode`。如果构造的对象没有改变，`hashCode` 总是相同的。`hashCode` 是 JVM 在创建类对象时生成的唯一代码。我们可以使用 `hashCode` 对哈希相关算法进行一些操作，比如 `hashtable`、`hashmap` 等。我们可以搜索一个具有唯一代码的对象。

## 语法

```java
public int hashCode()
```

## 参数

此方法不接受任何参数。

## 返回值

该方法返回该对象的哈希码整数值。

下面的程序说明了 `hashCode()` 方法：

## 程序 1

```java
// Java program to illustrate hashCode() method

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

        // get hash code of this constructor class
        int code = cons[0].hashCode();

        // print result
        System.out.println(
            "Hash Code count = " + code);
    }
}
```

## 输出

```java
Hash Code count = -1114099497
```

## 程序 2

```java
// Java program to illustrate hashCode() method

import java.lang.reflect.Constructor;

public class GFG {

    public static void main(String[] args)
    {
        // create a class object
        Class classObj = String.class;

        // get Constructor object
        // array from class object
        Constructor[] cons = classObj.getConstructors();

        // get hash code of this constructor class
        int code = cons[0].hashCode();

        // print result
        System.out.println(
            "Hash Code count for string class"
            + " constructor = " + code);
    }
}
```

## 输出

```java
Hash Code count for string class constructor = 1195259493
```

## 参考文献

[https://docs.oracle.com/javase/10/docs/api/java/lang/reflect/Constructor.html#hashCode()](https://docs.oracle.com/javase/10/docs/api/java/lang/reflect/Constructor.html#hashCode())