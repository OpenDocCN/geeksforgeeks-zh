# 用示例替换 Java 中的 HashMap(key, oldValue, newValue) 方法

> 原文: [https://www.geeksforgeeks.org/hashmap-replacekey-oldvalue-newvalue-method-in-java-with-examples/](https://www.geeksforgeeks.org/hashmap-replacekey-oldvalue-newvalue-method-in-java-with-examples/)

由 [`HashMap`](https://www.geeksforgeeks.org/java-util-hashmap-in-java/) 类实现的 [`Map`](https://www.geeksforgeeks.org/map-interface-java-examples/) 接口的 [`replace(K key, V oldValue, V newValue)`](https://www.geeksforgeeks.org/map-interface-java-examples/) 方法，仅当该键之前映射了指定的旧值时，用于替换指定键的旧值。

## 语法

```java
default boolean replace(K key, V oldValue, V newValue)
```

## 参数

该方法接受三个参数:

*   `key`: 需要替换其值的元素的键。
*   `oldValue`: 必须与提供的键映射的旧值。
*   `newValue`: 必须与指定键映射的新值。

## 返回值

如果旧值被替换，该方法返回布尔值 `true`，否则返回 `false`。

## 异常

如果指定的键或值为 `null`，并且此映射不允许 `null` 键或值，则此方法将抛出:

*   [`NullPointerException`](https://www.geeksforgeeks.org/null-pointer-exception-in-java/)，如果指定键或值的某些属性阻止其存储在此映射中，则抛出此异常。
*   `IllegalArgumentException`。

## 程序 1

```java
// Java program to demonstrate
// replace(K key, V oldValue, V newValue) method

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

        // provide old value, new value for the key
        // which has to replace it's old value, using
        // replace(K key, V oldValue, V newValue) method
        map.replace("b", 300, 200);

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
// replace(K key, V oldValue, V newValue) method

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

        // provide old value, new value for the key
        // which has to replace it's old value,
        // and store the return value in isReplaced using
        // replace(K key, V oldValue, V newValue) method
        boolean isReplaced = map.replace("b", 200, 500);

        // print the value of isReplaced
        System.out.println("Old value for 'b' was "
                           + "replaced: " + isReplaced);

        // print new mapping
        System.out.println("New HashMap: "
                           + map.toString());
    }
}
```

**输出:**

```java
HashMap: {a=100, b=300, c=300, d=400}
Old value for 'b' was replaced: false
New HashMap: {a=100, b=300, c=300, d=400}
```

**参考文献:** [https://docs.oracle.com/javase/8/docs/api/java/util/HashMap.html#replace-K-V-V-](https://docs.oracle.com/javase/8/docs/api/java/util/HashMap.html#replace-K-V-V-)