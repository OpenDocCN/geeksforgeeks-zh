# Java 中的 HashMap getOrDefault(key, defaultValue) 方法示例

> 原文：[https://www.geeksforgeeks.org/hashmap-getordefaultkey-defaultvalue-method-in-java-with-examples/](https://www.geeksforgeeks.org/hashmap-getordefaultkey-defaultvalue-method-in-java-with-examples/)

[`Map`](https://www.geeksforgeeks.org/map-interface-java-examples/) 接口的 `getOrDefault(Object key, V defaultValue)` 方法由 [`HashMap`](https://www.geeksforgeeks.org/java-util-hashmap-in-java/) 类实现，用于获取与指定键关联的值。如果没有值与提供的键映射，则返回默认值。

## 语法

```java
default V getOrDefault(Object key, V defaultValue)
```

## 参数

此方法接受两个参数：

*   `key`：要获取其值的元素的键。
*   `defaultValue`：当没有值与指定键映射时，必须返回的默认值。

## 返回值

此方法返回与指定键映射的值，否则返回默认值。

## 程序 1

```java
// Java program to demonstrate
// getOrDefault(Object key, V defaultValue) method

import java.util.*;

public class GFG {

    // Main method
    public static void main(String[] args)
    {

        // Create a HashMap and add some values
        HashMap<String, Integer> map
            = new HashMap<>();
        map.put("a", 100);
        map.put("b", 200);
        map.put("c", 300);
        map.put("d", 400);

        // print map details
        System.out.println("HashMap: "
                           + map.toString());

        // provide key whose value has to be obtained
        // and default value for the key. Store the
        // return value in k
        int k = map.getOrDefault("b", 500);

        // print the value of k returned by
        // getOrDefault(Object key, V defaultValue) method
        System.out.println("Returned Value: " + k);
    }
}
```

**输出：**

```java
HashMap: {a=100, b=200, c=300, d=400}
Returned Value: 200
```

## 程序 2

```java
// Java program to demonstrate
// getOrDefault(Object key, V defaultValue) method

import java.util.*;

public class GFG {

    // Main method
    public static void main(String[] args)
    {

        // Create a HashMap and add some values
        HashMap<String, Integer> map
            = new HashMap<>();
        map.put("a", 100);
        map.put("b", 200);
        map.put("c", 300);
        map.put("d", 400);

        // print map details
        System.out.println("HashMap: "
                           + map.toString());

        // provide key whose value has to be obtained
        // and default value for the key. Store the
        // return value in k
        int k = map.getOrDefault("y", 500);

        // print the value of k returned by
        // getOrDefault(Object key, V defaultValue) method
        System.out.println("Returned Value: " + k);
    }
}
```

**输出：**

```java
HashMap: {a=100, b=200, c=300, d=400}
Returned Value: 500
```

## 参考文献

[https://docs.oracle.com/javase/8/docs/api/java/util/HashMap.html#getOrDefault-java.lang.Object-V-](https://docs.oracle.com/javase/8/docs/api/java/util/HashMap.html#getOrDefault-java.lang.Object-V-)