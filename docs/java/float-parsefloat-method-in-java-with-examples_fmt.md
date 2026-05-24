# Java 中 Float parseFloat()方法，带示例

> 原文: [https://www.geeksforgeeks.org/float-parsefloat-method-in-java-with-examples/](https://www.geeksforgeeks.org/float-parsefloat-method-in-java-with-examples/)

[`Float`](https://www.geeksforgeeks.org/java-lang-float-class-in-java/) 类中的 `parseFloat()` 方法是 Java 中的一个内置方法，它返回一个新的 `Float`，该 `Float` 被初始化为由指定字符串表示的值，就像 `Float` 类的 `valueOf` 方法一样。

## 语法:

```java
public static float parseFloat(String s)
```

## 参数:
它接受一个指定要解析的字符串的强制参数。

## 返回类型:
它返回由字符串参数表示的浮点值。

## 异常:
函数抛出两个异常，如下所述:
*   `NullPointerException` - 当被解析的字符串为 `null` 时。
*   `NumberFormatException` – 当被解析的字符串不包含可解析的浮点数时。

下面是上述方法的实现。

### 程序 1:

```java
// Java Code to implement
// parseFloat() method of Float class

class GFG {

    // Driver method
    public static void main(String[] args)
    {
        String str = "100";

        // returns the float value
        // represented by the string argument
        float val = Float.parseFloat(str);

        // prints the float value
        System.out.println("Value = " + val);
    }
}
```

**输出:**

```java
Value = 100.0
```

### 程序 2: 显示数字格式异常

```java
// Java Code to implement
// parseFloat() method of Float class

class GFG {

    // Driver method
    public static void main(String[] args)
    {

        try {
            String str = "";

            // returns the float value
            // represented by the string argument
            float val = Float.parseFloat(str);

            // prints the float value
            System.out.println("Value = " + val);
        }

        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**输出:**

```java
Exception: java.lang.NumberFormatException: empty String
```

### 程序 3: 显示空指针异常

```java
// Java Code to implement
// parseFloat() method of Float class

class GFG {

    // Driver method
    public static void main(String[] args)
    {

        try {

            String str = null;

            // returns the float value
            // represented by the string argument
            float val = Float.parseFloat(str);

            // prints the float value
            System.out.println("Value = " + val);
        }

        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**输出:**

```java
Exception: java.lang.NullPointerException
```

## 参考:
[https://docs.oracle.com/javase/7/docs/api/java/lang/Float.html#parseFloat(java.lang.String)](https://docs.oracle.com/javase/7/docs/api/java/lang/Float.html#parseFloat(java.lang.String))