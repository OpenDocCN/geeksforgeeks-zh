# Java 中的布尔 parseBoolean()方法，带示例

> 原文：[https://www.geeksforgeeks.org/boolean-parseboolean-method-in-java-with-examples/](https://www.geeksforgeeks.org/boolean-parseboolean-method-in-java-with-examples/)

[`Boolean`](https://www.geeksforgeeks.org/java-lang-boolean-class-java/)类的`parseBoolean()`方法是该类的内置静态方法，用于将给定字符串转换为其布尔值。

## 语法：
```java
Boolean.parseBoolean(String value)
```

## 参数：
取类型字符串的一个参数`value`，该值包含要转换为布尔值的值。

## 返回值：
返回一个原始布尔值。如果给定值等于“true”（忽略大小写），则返回`true`。否则返回`false`。

下面是 Java 代码来说明`parseBoolean()`方法：

## 示例：

### 例 1：
```java
class GeeksforGeeks {

    // Driver method
    public static void main(String[] args)
    {

        // string value
        String value = "TrUe";

        // parseBoolean using parseBoolean() method
        boolean result = Boolean.parseBoolean(value);

        // printing the result
        System.out.println(result);
    }
}
```
**输出：**
```java
true
```

### 例 2：
```java
class GeeksforGeeks {

    // Driver method
    public static void main(String[] args)
    {

        // string value
        String value = "true";

        // parseBoolean using parseBoolean() method
        boolean result = Boolean.parseBoolean(value);

        // printing the result
        System.out.println(result);
    }
}
```
**输出：**
```java
true
```

### 例 3：
```java
class GeeksforGeeks {

    // Driver method
    public static void main(String[] args)
    {

        // string value
        String value = "gfg";

        // parseBoolean using parseBoolean() method
        boolean result = Boolean.parseBoolean(value);

        // printing the result
        System.out.println(result);
    }
}
```
**输出：**
```java
false
```