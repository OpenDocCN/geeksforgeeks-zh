# Java 中的 `Double.longValue()` 方法示例

> 原文：[https://www.geeksforgeeks.org/double-longvalue-in-java-with-examples/](https://www.geeksforgeeks.org/double-longvalue-in-java-with-examples/)

`Double` 类的 `longValue()` 方法是一个内置方法，用于在类型转换后将调用对象指定的值作为 `long` 返回。

## 语法

```java
DoubleObject.longValue()
```

## 参数

不取参数。

## 返回类型

它返回一个 `long` 值，即 `DoubleObject` 的类型铸造值。

下面是上述方法的实现。

### 代码 1

```java
// Java Code to implement 
// longValue() method of Double class
class GFG {
    // Driver method
    public static void main(String[] args)
    {
        // creating a Double object
        Double d = new Double(1022);

        // longValue() method of Double class
        // typecast the value
        long output = d.longValue();

        // printing the output
        System.out.println(output);
    }
}
```

### 输出

```java

```

### 代码 2

```java
// Java Code to implement 
// longValue() method of Double class
class GFG {
    // Driver method
    public static void main(String[] args)
    {
        // creating a Double object
        Double d = new Double(-1023.23);

        // longValue() method of Double class
        // typecast the value
        long output = d.longValue();

        // printing the output
        System.out.println(output);
    }
}
```

### 输出

```java

```