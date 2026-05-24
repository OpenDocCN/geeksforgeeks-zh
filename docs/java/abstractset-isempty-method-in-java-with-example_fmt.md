# Java中AbstractSet.isEmpty()方法详解

> 原文：[https://www.geeksforgeeks.org/abstractset-isempty-method-in-java-with-example/](https://www.geeksforgeeks.org/abstractset-isempty-method-in-java-with-example/)

在Java中，`AbstractSet`的`isEmpty()`方法用来检查这个抽象集是否为空。它返回一个布尔值，表示相同的内容。

## 语法

```java
public boolean isEmpty()
```

## 参数
此功能无参数。

## 返回值
该方法返回一个`boolean`值，表示抽象集的这个实例是否为空。

## 示例
以下示例说明了`AbstractSet.isEmpty()`方法：

### 示例 1

```java
// Java code to demonstrate the working of
// isEmpty() method in AbstractSet

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // creating an AbstractSet
        AbstractSet<Integer> arr
            = new TreeSet<Integer>();

        // using add() to initialize values
        // [1, 2, 3, 4]
        arr.add(1);
        arr.add(2);
        arr.add(3);
        arr.add(4);

        // print AbstractSet
        System.out.println("AbstractSet: "
                           + arr);

        // Check if AbstractSet is empty
        // using isEmpty() value
        System.out.println("Is AbstractSet empty? "
                           + arr.isEmpty());
    }
}
```

**输出：**

```java
AbstractSet: [1, 2, 3, 4]
Is AbstractSet empty? false
```

### 示例 2

```java
// Java code to demonstrate the working of
// isEmpty() method in AbstractSet

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // creating an AbstractSet
        AbstractSet<String> arr
            = new TreeSet<String>();

        // print AbstractSet
        System.out.println("AbstractSet: "
                           + arr);

        // Check if AbstractSet is empty
        // using isEmpty() value
        System.out.println("Is AbstractSet empty? "
                           + arr.isEmpty());
    }
}
```

**输出：**

```java
AbstractSet: []
Is AbstractSet empty? true
```