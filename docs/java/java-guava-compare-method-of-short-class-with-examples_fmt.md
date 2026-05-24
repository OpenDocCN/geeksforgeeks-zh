# Java Guava：使用示例比较Shorts.compare()方法

> 原文：[https://www.geeksforgeeks.org/java-guava-compare-method-of-short-class-with-examples/](https://www.geeksforgeeks.org/java-guava-compare-method-of-short-class-with-examples/)

`Shorts.compare()`方法是Guava [`Shorts`](https://www.geeksforgeeks.org/shorts-class-guava-java/)类中的一个方法，用于比较两个指定的`short`值。这些值作为参数传递，比较的结果是第一个值和第二个值的差值。因此它可以是正的、零的或负的。

## 语法

```java
public static int compare(short x, short y)
```

## 参数

该方法接受两个参数：

*   `x`： 是第一个要比较的`Short`对象。
*   `y`： 是要比较的`Short`对象。

## 返回类型

返回一个`int`值。它返回：

*   如果`x`等于`y`，则为 0，
*   正值`x`大于`y`，
*   负值`x`小于`y`

下面是`compare()`方法在Java中的实现：

### 示例 1

```java
// Java code to show implementation of
// Guava's Shorts.compare() method
import com.google.common.primitives.Shorts;

class GFG {
    public static void main(String[] args)
    {

        short a = 4;

        short b = 4;

        // compare method in Short class
        int output = Shorts.compare(a, b);

        // printing the output
        System.out.println("Comparing " + a
                           + " and " + b + " : "
                           + output);
    }
}
```

**Output:**

```java
Comparing 4 and 4 : 0
```

### 示例 2

```java
// Java code to show implementation of
// Guava's Shorts.compare() method
import com.google.common.primitives.Shorts;

class GFG {
    public static void main(String[] args)
    {

        short a = 4;

        short b = 2;

        // compare method in Short class
        int output = Shorts.compare(a, b);

        // printing the output
        System.out.println("Comparing " + a
                           + " and " + b + " : "
                           + output);
    }
}
```

**Output:**

```java
Comparing 4 and 2 : 2
```

### 示例 3

```java
// Java code to show implementation of
// Guava's Shorts.compare() method
import com.google.common.primitives.Shorts;

class GFG {
    public static void main(String[] args)
    {

        short a = 2;

        short b = 4;

        // compare method in Short class
        int output = Shorts.compare(a, b);

        // printing the output
        System.out.println("Comparing " + a
                           + " and " + b + " : "
                           + output);
    }
}
```

**Output:**

```java
Comparing 2 and 4 : -2
```