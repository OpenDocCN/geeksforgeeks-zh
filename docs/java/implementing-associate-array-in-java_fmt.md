# 在 Java 中实现关联数组

> 原文：[https://www.geeksforgeeks.org/implementing-associate-array-in-java/](https://www.geeksforgeeks.org/implementing-associate-array-in-java/)

一个**关联数组**以**(键，值)**对的形式存储元素集。**关联数组**是唯一键的集合和值的集合，其中每个键与一个值相关联。

关联数组是一种抽象数据类型，类似于由(键、值)对组成的映射，因此每个键-值在集合中最多出现一次。基本上，一个带有名为索引的数组被称为关联数组或散列。

在 Java 中，很难形成关联数组，但是这可以通过使用 [`HashMap`](https://www.geeksforgeeks.org/java-util-hashmap-in-java/) 轻松实现。

**语法：**

```java
Map<String, String> map = new HashMap<String, String>();

// method to add the key,value pair in hashmap
map.put("geeks", "course");
map.put("name", "geeks");

// method to get the value
map.get("name"); // returns "geeks"
```

## 使用映射函数实现关联数组或关联列表数组的步骤

1.  首先初始化地图。

    ```java
    Map<String ,String> map = new HashMap<>();
    ```

2.  然后使用 `put()` 方法将键、数值放入地图。

    ```java
    map.put("geeks","Course");
    ```

3.  将所有键值放入地图后，使用 `entrySet()` 方法将地图转换为集合。

    ```java
    Set<Map.Entry<String ,String> > set = map.entrySet();
    ```

4.  然后现在使用构造函数将集合转换为列表数组。

    ```java
    List<Map.Entry<String ,String>> list=new ArrayList<>(set);
    ```

## 关联数组的实现

```java
// Java program to implement the associate array

import java.io.*;
import java.util.*;

class GFG {

    public static void main(String[] args)
    {

        // Forming the map
        Map<String, String> map = new HashMap<>();

        // method to store the value and
        // key into the map
        map.put("name", "rohit");
        map.put("geeks", "course");
        map.put("India Capital", "Delhi");

        System.out.println(map.size());

        Set<Map.Entry<String, String> > set
                       = map.entrySet();

        List<Map.Entry<String, String> > list
                    = new ArrayList<>(set);

        for (int i = 0; i < list.size(); i++)
        {
            System.out.println(list.get(i).getKey() + ": "
                               + list.get(i).getValue());
        }
    }
}
```

**Output**

```java
India Capital: Delhi
geeks: course
name: rohit
```

*   **时间复杂度:** O(n)
*   **空间复杂度:** O(n)

我们可以使用 `iterator()` 方法迭代数组。

**语法：**

```java
Iterator it = map.entrySet().iterator();
```

## 使用迭代器方法实现关联数组

```java
// Java program to implement the associate array
// and iterate it using iterator() method

import java.io.*;
import java.util.*;
class GFG {
    public static void main(String[] args)
    {
        // Forming the map
        Map<String, Integer> map = new HashMap<>();

        // method to store the put the value and
        // key into the map
        map.put("Roll no", 45);
        map.put("Total Question", 113);
        map.put("Marks ", 400);

        // method to access the value based on
        // the key
        System.out.println(map.size());

        Set<Map.Entry<String, Integer> > set
            = map.entrySet();

        List<Map.Entry<String, Integer> > list
            = new ArrayList<>(set);

        // using the iterator
        Iterator it = list.iterator();
        while (it.hasNext()) {
            System.out.println(it.next());
        }
    }
}
```

**Output**

```java
Total Question=113
Roll no=45
Marks =400
```

*   **时间复杂度:** O(n)
*   **空间复杂度:** O(n)