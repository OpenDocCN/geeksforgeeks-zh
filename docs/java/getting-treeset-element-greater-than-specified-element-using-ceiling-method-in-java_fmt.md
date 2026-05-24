# 使用 Java 中的天花板方法获取大于指定元素的树集元素

> 原文：[https://www.geeksforgeeks.org/getting-treeset-element-greater-than-specified-element-using-ceiling-method-in-java/](https://www.geeksforgeeks.org/getting-treeset-element-greater-than-specified-element-using-ceiling-method-in-java/)

使用 Java 中的 [`ceiling()` 方法](https://www.geeksforgeeks.org/treeset-ceiling-method-in-java-with-examples/)获取大于指定元素的 [`TreeSet`](https://www.geeksforgeeks.org/treeset-in-java-with-examples/) 元素。Java 中的天花板方法返回集合中大于或等于给定元素的最少元素，如果没有这样的元素，则返回 `null`。

[`java.util.TreeSet<E>`](https://www.geeksforgeeks.org/treeset-in-java-with-examples/) 类的 `ceiling()` 方法用于返回该集合中大于或等于给定元素的最少元素，如果没有该元素，则返回 `null`。

**语法：**

```java
public E ceiling(E e)
```

**参数：** 该方法将值 `e` 作为待匹配的参数。

**返回值：** 该方法返回大于等于 `e` 的最小元素，如果没有则返回空值。

**异常：** 如果指定的元素为空，并且该集合使用自然排序，或者其比较器不允许空元素，则该方法抛出 `NullPointerException`。

```java
set = {10,20,30,40,50}

// Least element in the set greater than or equal to the 23
Ceiling value of 23: 30

// There is no such element so it returns null
Ceiling value of 55: null
```

## 示例代码

```java
// Java Program demonstrate how to get TreeSet Element
// Greater than Specified Element using ceiling() Method

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

// New TreeSet
        TreeSet<Integer> set = new TreeSet<>();

// Adding element to TreeSet
        set.add(40);
        set.add(50);
        set.add(30);
        set.add(10);
        set.add(20);

// Print TreeSet
        System.out.println("TreeSet: " + set);

// Print ceiling of 23
        System.out.println("Ceiling value of 23: "
                           + set.ceiling(23));
    }
}
```

**输出**

```java
TreeSet: [10, 20, 30, 40, 50]
Ceiling value of 23: 30
```

## 示例代码

```java
// Java Program demonstrate how to get TreeSet Element
// Greater than Specified Element using ceiling() Method

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

// New TreeSet
        TreeSet<Integer> set = new TreeSet<>();

// Adding element to TreeSet
        set.add(40);
        set.add(50);
        set.add(30);
        set.add(10);
        set.add(20);

// Print TreeSet
        System.out.println("TreeSet: " + set);

// Print ceiling of 55
        System.out.println("Ceiling value of 55: "
                           + set.ceiling(55));
    }
}
```

**输出**

```java
TreeSet: [10, 20, 30, 40, 50]
Ceiling value of 55: null
```