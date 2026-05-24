# Java 番石榴 Shorts.hashCode() 方法带示例

> 原文：[https://www.geeksforgeeks.org/java-guava-shorts-hashcode-method-with-examples/](https://www.geeksforgeeks.org/java-guava-shorts-hashcode-method-with-examples/)

`Shorts.hashCode()` 是番石榴库中 [`Shorts`](https://www.geeksforgeeks.org/shorts-class-guava-java/) 类的一种方法，用于返回一个短值的哈希码。哈希码是由编译器为对象计算的唯一整数值。如果对象值不变，则哈希码保持不变。

## 语法

```java
public static int hashCode(short value)
```

## 参数

该方法采用强制参数 `value`，这是一个短值，可以为其找到哈希值。

## 返回值

该方法返回一个整数值，该整数值是指定值的哈希代码。

下面的程序说明了上述方法的使用：

## 例 1

```java
// Java code to show implementation of
// Guava's Shorts.hashCode() method

import com.google.common.primitives.Shorts;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Using Shorts.hashCode() method to
        // get the hash code for value
        System.out.println("HashCode value of 15: "
                           + Shorts.hashCode((short)15));
    }
}
```

## 输出

```java
HashCode value of 15: 15
```

## 例 2

```java
// Java code to show implementation of
// Guava's Shorts.hashCode() method

import com.google.common.primitives.Shorts;
import java.util.Arrays;

class GFG {
    // Driver's code
    public static void main(String[] args)
    {
        // Using Shorts.hashCode() method to
        // get the hash code for value
        System.out.println("HashCode value of 10: "
                           + Shorts.hashCode((short)10));
    }
}
```

## 输出

```java
HashCode value of 10: 10
```

## 参考

[https://google.github.io/guava/releases/23.0/api/docs/com/google/common/primitives/Shorts.html#hashCode-short-](https://google.github.io/guava/releases/23.0/api/docs/com/google/common/primitives/Shorts.html#hashCode-short-)