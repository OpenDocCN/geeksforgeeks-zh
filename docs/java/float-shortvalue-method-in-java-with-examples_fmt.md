# Java 中的 Float shortValue() 方法

> 原文：[https://www.geeksforgeeks.org/float-shortvalue-method-in-java-with-examples/](https://www.geeksforgeeks.org/float-shortvalue-method-in-java-with-examples/)

`Float` 类中的 `shortValue()` 方法是 Java 中的一个内置方法，它在类型转换后将对象调用为 `short` 来返回指定的值。

## 语法

```java
public short shortValue()
```

## 返回值

返回浮点值的 `short` 简称。

## 示例

下面的程序说明了 Java 中的 `shortValue()` 方法：

### 程序 1

```java
// Java code to demonstrate
// Float shortValue() method

class GFG {
    public static void main(String[] args)
    {

        // Float value
        Float a = 17.47f;

        // wrapping the Float value
        // in the wrapper class Float
        Float b = new Float(a);

        // shortValue of the Float Object
        short output = b.shortValue();

        // prshorting the output
        System.out.println("Short value of "
                           + b + " is : " + output);
    }
}
```

**输出：**

```java
Short value of 17.47 is : 17
```

### 程序 2

```java
// Java code to demonstrate
// Float shortValue() method

class GFG {
    public static void main(String[] args)
    {

        String value = "54.1f";

        // wrapping the Float value
        // in the wrapper class Float
        Float b = new Float(value);

        // shortValue of the Float Object
        short output = b.shortValue();

        // prshorting the output
        System.out.println("Short value of "
                           + b + " is : " + output);
    }
}
```

**输出：**

```java
Short value of 54.1 is : 54
```

## 参考

[https://docs.oracle.com/javase/7/docs/api/java/lang/Float.html#shortValue()](https://docs.oracle.com/javase/7/docs/api/java/lang/Float.html#shortValue())