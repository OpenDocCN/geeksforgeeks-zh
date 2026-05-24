# Java 中的布尔 hashCode()方法，带示例

> 原文: [https://www.geeksforgeeks.org/boolean-hashcode-method-in-java-with-examples/](https://www.geeksforgeeks.org/boolean-hashcode-method-in-java-with-examples/)

[`Boolean`](https://www.geeksforgeeks.org/java-lang-boolean-class-java/)类的 `hashCode()` 方法是一个内置方法，用于返回与布尔对象对应的 `int` hashcode 值。

## 语法

```java
BooleanObject.hashCode()
```

## 返回类型

返回一个与布尔对象对应的 `int` hashcode 值。如果布尔对象存储值为 `true`，则返回 `1231`。如果布尔对象存储值为 `false`，则返回 `1237`。

下面是 `hashCode()` 方法在 Java 中的实现：

## 程序 1

```java
// java code to demonstrate
// Boolean hashCode() method

class GFG {
    public static void main(String[] args)
    {

// creating Boolean object
        Boolean b = new Boolean(true);

// hashCode method of Boolean class
        int output = b.hashCode();

// printing the output
        System.out.println(output);
    }
}
```

**Output:**

```java

```

## 程序 2

```java
// java code to demonstrate
// Boolean hashCode() method

class GFG {
    public static void main(String[] args)
    {

// creating Boolean object
        Boolean b = new Boolean(false);

// hashCode method of Boolean class
        int output = b.hashCode();

// printing the output
        System.out.println(output);
    }
}
```

**Output:**

```java

```