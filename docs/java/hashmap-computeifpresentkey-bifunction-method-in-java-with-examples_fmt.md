# HashMap computeIfPresent方法详解

## 方法介绍

`HashMap`类的`computeIfPresent(key, BiFunction)`方法，如果Key已经与值相关联（或映射为空），则允许您计算指定Key的映射值。

*   如果此方法的映射函数返回`null`，则移除映射。
*   如果重新映射函数引发异常，该异常将被重新引发，并且映射保持不变。
*   在计算过程中，不允许使用此方法修改此地图。

## 语法

```java
public Object computeIfPresent(Object key,
                  BiFunction remappingFunction)
```

## 参数

该方法接受两个参数：

*   `键`：与数值相关联的键。
*   `重编程功能`：对数值进行运算的功能。

## 返回值

该方法返回与指定键关联的`新的重映射值`，如果映射返回空值，则返回`null`。

下面的程序说明了`computeIfPresent(key, BiFunction)`方法：

## 示例1

此示例演示了密钥不在 hashmap 中的情况。

```java
// Java program to demonstrate
// computeIfPresent(Key, BiFunction) method.

import java.util.concurrent.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

// Create a HashMap and add some values
        HashMap<String, Integer> wordCount = new HashMap<>();
        wordCount.put("Geeks", 1);
        wordCount.put("for", 2);
        wordCount.put("geeks", 3);

// print HashMap details
        System.out.println("Hashmap before operation :\n "
                           + wordCount);

// provide new value for keys which is present
        // using computeIfPresent method
        wordCount.computeIfPresent("Geek",
                                   (key, val) -> val + 100);

// print new mapping
        System.out.println("HashMap after operation :\n "
                           + wordCount);
    }
}
```

**Output:**

```java
Hashmap before operation :
 {geeks=3, Geeks=1, for=2}
HashMap after operation :
 {geeks=3, Geeks=1, for=2}
```

## 示例2

本示例演示了密钥出现在散列表中的情况。

```java
// Java program to demonstrate
// computeIfPresent(Key, BiFunction) method.

import java.util.concurrent.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

// Create a HashMap and add some values
        HashMap<String, Integer> wordCount = new HashMap<>();
        wordCount.put("Geeks", 1);
        wordCount.put("for", 2);
        wordCount.put("geeks", 3);

// print HashMap details
        System.out.println("Hashmap before operation :\n "
                           + wordCount);

// provide new value for keys which is present
        // using computeIfPresent method
        wordCount.computeIfPresent("for",
                                   (key, val) -> val + 1);

// print new mapping
        System.out.println("HashMap after operation :\n "
                           + wordCount);
    }
}
```

**Output:**

```java
Hashmap before operation :
 {geeks=3, Geeks=1, for=2}
HashMap after operation :
 {geeks=3, Geeks=1, for=3}
```

## 参考

[https://docs.oracle.com/javase/8/docs/api/java/util/HashMap.html#computeIfPresent-K-java.util.function.BiFunction-](https://docs.oracle.com/javase/8/docs/api/java/util/HashMap.html#computeIfPresent-K-java.util.function.BiFunction-)