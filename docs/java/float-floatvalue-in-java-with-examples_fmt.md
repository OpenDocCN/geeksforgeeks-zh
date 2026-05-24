# Java 中的 `Float floatValue()` 示例

> 原文: [https://www.geeksforgeeks.org/float-floatvalue-in-java-with-examples/](https://www.geeksforgeeks.org/float-floatvalue-in-java-with-examples/)

[`Float`](https://www.geeksforgeeks.org/java-lang-float-class-in-java/) 类中的 `floatValue()` 方法是 Java 中的内置函数，在类型转换后将调用对象指定的值作为 `float` 返回。

**语法:**

```java
public float floatValue()
```

**返回值:** 将浮点对象的值作为 `float` 返回。

下面的程序用 Java 说明了 `floatValue()` 方法:

### 示例 1

```java
// Java code to demonstrate
// Float floatValue() method

class GFG {
    public static void main(String[] args)
    {
        // Float value
        Float a = 17.47f;

        // wrapping the Float value
        // in the wrapper class Float
        Float b = new Float(a);

        // floatValue of the Float Object
        float output = b.floatValue();

        // printing the output
        System.out.println("Float value of "
                           + b + " is : " + output);
    }
}
```

**Output:**

```java
Float value of 17.47 is : 17.47
```

### 示例 2

```java
// Java code to demonstrate
// Float floatValue() method

class GFG {
    public static void main(String[] args)
    {
        String value = "54.1";

        // wrapping the Float value
        // in the wrapper class Float
        Float b = new Float(value);

        // floatValue of the Float Object
        float output = b.floatValue();

        // printing the output
        System.out.println("Float value of "
                           + b + " is : " + output);
    }
}
```

**Output:**

```java
Float value of 54.1 is : 54.1
```

**参考:** [https://docs.oracle.com/javase/7/docs/api/java/lang/Float.html#floatValue()](https://docs.oracle.com/javase/7/docs/api/java/lang/Float.html#floatValue())