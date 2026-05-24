# Java 中的 AbstractSequentialList hashCode() 方法示例

> 原文：[https://www.geeksforgeeks.org/abstractsequentiallist-hashcode-method-in-java-with-example/](https://www.geeksforgeeks.org/abstractsequentiallist-hashcode-method-in-java-with-example/)

Java 中 `AbstractSequentialList` 的 `hashCode()` 方法用来获取 `AbstractSequentialList` 这个实例的 `hashCode` 值。它返回一个整数值，该整数值是 `AbstractSequentialList` 实例的哈希值。

## 语法

```java
public int hashCode()
```

## 参数

该方法没有参数。

## 返回值

该方法返回一个整数值，这是 `AbstractSequentialList` 实例的哈希值。

以下示例说明了 `AbstractSequentialList.hashCode()` 方法：

## 示例 1

```java
// Java code to demonstrate the working of
// hashCode() method in AbstractSequentialList

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // creating an AbstractSequentialList
        AbstractSequentialList<Integer> arr
            = new LinkedList<Integer>();

        // using add() to initialize values
        // [1, 2, 3, 4]
        arr.add(1);
        arr.add(2);
        arr.add(3);
        arr.add(4);

        // print AbstractSequentialList
        System.out.println("AbstractSequentialList: "
                           + arr);

        // Get the hashCode value
        // using hashCode() value
        System.out.println("HashCode value: "
                           + arr.hashCode());
    }
}
```

**输出：**

```java
AbstractSequentialList: [1, 2, 3, 4]
HashCode value: 955331
```

## 示例 2

```java
// Java code to demonstrate the working of
// hashCode() method in AbstractSequentialList

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // creating an AbstractSequentialList
        AbstractSequentialList<String> arr
            = new LinkedList<String>();

        // using add() to initialize values
        // [Geeks, For, ForGeeks, GeeksForGeeks]
        arr.add("Geeks");
        arr.add("For");
        arr.add("ForGeeks");
        arr.add("GeeksForGeeks");

        // print AbstractSequentialList
        System.out.println("AbstractSequentialList: "
                           + arr);

        // Get the hashCode value
        // using hashCode() value
        System.out.println("HashCode value: "
                           + arr.hashCode());
    }
}
```

**输出：**

```java
AbstractSequentialList: [Geeks, For, ForGeeks, GeeksForGeeks]
HashCode value: -927254198
```