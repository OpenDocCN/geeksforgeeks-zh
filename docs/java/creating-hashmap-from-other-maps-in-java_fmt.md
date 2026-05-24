# 用 Java 从其他地图创建哈希表

> 原文：[https://www.geeksforgeeks.org/creating-hashmap-from-other-maps-in-java/](https://www.geeksforgeeks.org/creating-hashmap-from-other-maps-in-java/)

[`java.util`](https://www.geeksforgeeks.org/java-util-package-java/) 包中的 [`Map`](https://www.geeksforgeeks.org/map-interface-java-examples/) 接口表示键和值之间的映射。`Map` 接口不是 [`Collection`](https://www.geeksforgeeks.org/collections-in-java-2/) 接口的子类型。因此，它的行为与其他集合类型有点不同。`Map` 包含唯一的键。

**Java 中的 `Map` 主要有三种类型**

1.  [`HashMap`](https://www.geeksforgeeks.org/java-util-hashmap-in-java-with-examples/#:~:text=HashMap%20is%20similar%20to%20the,you%20need%20to%20import%20java.)
2.  [`LinkedHashMap`](https://www.geeksforgeeks.org/linkedhashmap-class-java-examples/)
3.  [`TreeMap`](https://www.geeksforgeeks.org/treemap-in-java/)

这些接口扩展了 `Map` 接口。

**将一张地图转换成另一张地图有多种方式：**

1.  使用迭代器/循环
2.  使用构造函数
3.  使用 `putAll()` 方法

**方法 1：使用迭代器/循环**

迭代 `Map` 的每个元素（在本例中是 `LinkedHashMap`），并在新的 `HashMap` 中添加每个元素。

## Java 代码示例

```java
// Java program for creating HashMap from Other Maps

import java.util.*;

public class to_hashmap {

    public static void main(String a[])
    {
        // create an instance of LinkedHashMap
        LinkedHashMap<String, String> lhm
               = new LinkedHashMap<String, String>();

        // Add mappings using put method
        lhm.put("Apurva", "Bhatt");
        lhm.put("James", "Bond");
        lhm.put("Scarlett ", "Johansson");

        // It prints the elements in same order
        // as they were inserted
        System.out.println(lhm);

        Map<String, String> gfg = new HashMap<String, String>();

        // Using entrySet() method create a set out of the same elements
        // contained in the hash map
        for (Map.Entry<String, String> entry : lhm.entrySet())
            gfg.put(entry.getKey(), entry.getValue());

        System.out.println(gfg);
    }
}
```

**Output**

```java
{Apurva=Bhatt, James=Bond, Scarlett =Johansson}
{James=Bond, Apurva=Bhatt, Scarlett =Johansson}
```

**方法二：使用构造器**

将给定的 `Map`（在本例中是 `TreeMap`）传递给 `HashMap` 构造器——它将自动负责将给定的 `Map` 转换为 `HashMap`。

## Java 代码示例

```java
// Java program for creating HashMap from Other Maps
// using constructor

import java.util.*;

public class to_hashmap {

    public static void main(String a[])
    {
        // create an instance of TreeMap
        Map<String, String> tm = new TreeMap<String, String>();

        // Add mappings using put method
        tm.put("Apurva", "Bhatt");
        tm.put("James", "Bond");
        tm.put("Scarlett ", "Johansson");

        // It prints the elements in same order
        // as they were inserted
        System.out.println(tm);

        Map<String, String> gfg = new HashMap<String, String>(tm);

        System.out.println(gfg);
    }
}
```

**Output**

```java
{Apurva=Bhatt, James=Bond, Scarlett =Johansson}
{Apurva=Bhatt, James=Bond, Scarlett =Johansson}
```

**方法三：使用 [`putAll()`](https://www.geeksforgeeks.org/hashmap-putall-method-in-java/#:~:text=putAll()%20is%20an%20inbuilt,from%20one%20map%20into%20another.&text=Parameters%3A%20The%20method%20takes%20one,we%20want%20to%20copy%20from.) 方法**

它类似于前面的方法，不是将给定的 `Map` 传递给 `HashMap` 构造函数，而是将其传递给 `putAll()` 方法，它将自动将其转换为 `HashMap`。

## Java 代码示例

```java
// Java program for creating HashMap from Other Maps
// using putAll() method

import java.util.*;

public class two_hashmap {

    public static void main(String a[])
    {
        // create an instance of TreeMap
        Map<String, String> tm = new TreeMap<String, String>();

        // Add mappings using put method
        tm.put("Apurva", "Bhatt");
        tm.put("James", "Bond");
        tm.put("Scarlett ", "Johansson");

        // It prints the elements in same order
        // as they were inserted
        System.out.println(tm);

        Map<String, String> gfg = new HashMap<String, String>();

        // using put all command
        gfg.putAll(tm);

        System.out.println(gfg);
    }
}
```

**Output**

```java
{Apurva=Bhatt, James=Bond, Scarlett =Johansson}
{Apurva=Bhatt, James=Bond, Scarlett =Johansson}
```