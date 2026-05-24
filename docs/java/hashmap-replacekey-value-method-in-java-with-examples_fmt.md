# 用示例替换 Java 中的 HashMap(键，值)方法

> 原文: [https://www.geeksforgeeks.org/hashmap-replacekey-value-method-in-java-with-examples/](https://www.geeksforgeeks.org/hashmap-replacekey-value-method-in-java-with-examples/)

由 [`HashMap`](https://www.geeksforgeeks.org/java-util-hashmap-in-java/) 类实现的 [`Map`](https://www.geeksforgeeks.org/map-interface-java-examples/) 接口的 [`replace(K key, V value)`](https://www.geeksforgeeks.org/map-interface-java-examples/) 方法，只有在该键之前映射了某个值的情况下，才用于替换指定键的值。

## 语法

```java
public V replace(K key, V value)
```

## 参数

该方法接受两个参数:

*   `key`: 是需要替换其值的元素的键。
*   `value`: 是与提供的键映射的新值。

## 返回值

该方法返回与指定键关联的上一个值。如果没有映射这样的键，那么如果实现支持空值，则返回 `null`。

## 异常

如果指定的键或值为 `null`，并且此映射不允许空键或值，则此方法将抛出:

*   [`NullPointerException`](https://www.geeksforgeeks.org/null-pointer-exception-in-java/)，如果指定键或值的某些属性阻止其存储在此映射中，则抛出此异常。
*   `IllegalArgumentException`。

## 程序 1

```java
// Java program to demonstrate
// replace(K key, V value) method

import java.util.*;

public class GFG {

    // Main method
    public static void main(String[] args)
    {
        // Create a HashMap and add some values
        HashMap<String, Integer> map
            = new HashMap<>();
        map.put("a", 100);
        map.put("b", 300);
        map.put("c", 300);
        map.put("d", 400);

        // print map details
        System.out.println("HashMap: "
                           + map.toString());

        // provide value for the key which has
        // to replace it's current value,
        // using replace(K key, V value) method
        map.replace("b", 200);

        // print new mapping
        System.out.println("New HashMap: "
                           + map.toString());
    }
}
```

**输出:**

```java
HashMap: {a=100, b=300, c=300, d=400}
New HashMap: {a=100, b=200, c=300, d=400}
```

## 程序 2

```java
// Java program to demonstrate
// replace(K key, V value) method

import java.util.*;

public class GFG {

    // Main method
    public static void main(String[] args)
    {
        // Create a HashMap and add some values
        HashMap<String, Integer> map
            = new HashMap<>();
        map.put("a", 100);
        map.put("b", 300);
        map.put("c", 300);
        map.put("d", 400);

        // print map details
        System.out.println("HashMap: "
                           + map.toString());

        // provide value for the key which has
        // to replace it's current value, and will
        // store the value in k using the
        // replace(K key, V value) method
        int k = map.replace("b", 200);

        // print the value of k
        System.out.println("Previous value of 'b': "
                           + k);

        // print new mapping
        System.out.println("New HashMap: "
                           + map.toString());
    }
}
```

**输出:**

```java
HashMap: {a=100, b=300, c=300, d=400}
Previous value of 'b': 300
New HashMap: {a=100, b=200, c=300, d=400}
```

## 程序 3

```java
// Java program to demonstrate
// replace(K key, V value) method

import java.util.*;

public class GFG {

    // Main method
    public static void main(String[] args)
    {
        // Create a HashMap and add some values
        HashMap<String, Integer> map
            = new HashMap<>();
        map.put("a", 100);
        map.put("b", 300);
        map.put("c", 300);
        map.put("d", 400);

        // print map details
        System.out.println("HashMap: "
                           + map.toString());

        // provide value for the key which is
        // not mapped previously and store the
        // return value in Integer k, using
        // replace(K key, V value) method
        Integer k = map.replace("e", 200);

        // print the value of k
        System.out.println("Value of k, returned "
                           + "for key 'e': " + k);

        // print new mapping
        System.out.println("New HashMap: "
                           + map.toString());
    }
}
```

**输出:**

```java
HashMap: {a=100, b=300, c=300, d=400}
Value of k, returned for key 'e': null
New HashMap: {a=100, b=300, c=300, d=400}
```

**参考文献:** [https://docs.oracle.com/javase/8/docs/api/java/util/HashMap.html#replace-K-V-](https://docs.oracle.com/javase/8/docs/api/java/util/HashMap.html#replace-K-V-)