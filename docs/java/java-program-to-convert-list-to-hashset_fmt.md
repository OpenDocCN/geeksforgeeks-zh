# 将列表转换为 HashSet 的 Java 程序

> 原文: [https://www.geeksforgeeks.org/java-program-to-convert-list-to-hashset/](https://www.geeksforgeeks.org/java-program-to-convert-list-to-hashset/)

[`List`](https://www.geeksforgeeks.org/list-interface-java-examples/) 界面提供了一种存储有序集合的方式。它是对象的有序集合，其中可以存储重复的值。因为列表保留了插入顺序，所以它允许元素的位置访问和插入。

[`HashSet`](https://www.geeksforgeeks.org/hashset-in-java/) 类允许空元素。该类还为基本操作（如添加、移除、包含和大小）提供了恒定的时间性能，假设哈希函数将元素适当地分散在桶中，我们将在本文中进一步看到这一点。

> **注意:** 集合不允许存储重复值。因此，列表中的任何重复值都将被忽略。

## 列表转换为哈希集的方式

1.  在哈希集中作为参数传递列表对象。
2.  使用循环将列表的每个元素添加到哈希集中。
3.  使用集合类的 `addAll()` 方法。
4.  使用 Java 中的流。

## 方法 1: 在 HashSet 中传递列表对象作为参数

我们使用 `HashSet` 构造函数将其转换为 `List`。

```java
// Java program to demonstrate conversion of
// list to set using constructor

import java.util.*;
class GFG {
    public static void main(String[] args)
    {
        // Create a List
        List<String> L = new ArrayList<String>();

        // Add values to the List
        L.add("Aragorn");
        L.add("Gandalf");
        L.add("Legolas");
        L.add("Frodo");

        // Create a Set and pass List object as parameter
        HashSet<String> S = new HashSet<String>(L);

        // Print values of Set
        System.out.println("HashSet Elements are : ");

        // since the set is of string type, create a String
        // object to iterate through set
        for (String ob : S)
        {
            System.out.println(ob);
        }
    }
}
```

**Output**

```java
HashSet Elements are : 
Aragorn
Frodo
Gandalf
Legolas
```

## 方法 2: 使用循环将 List 的每个元素添加到 HashSet 中

我们只需创建一个列表。我们遍历给定的列表，一个接一个地向集合中添加元素。

```java
// Java program to demonstrate conversion of
// list to set using simple traversal

import java.util.*;
class GFG {
    public static void main(String[] args)
    {
        // Create a List
        List<Integer> L = new ArrayList<Integer>();

        // Add values to the List
        L.add(1);
        L.add(4);
        L.add(30);
        L.add(100);
        L.add(15);
        L.add(30);

        // Create a Set and pass List object as parameter
        HashSet<Integer> S = new HashSet<Integer>();

        // add each element of list into set
        for (Integer ob : L)
        {
            S.add(ob);
        }

        // Print values of Set
        System.out.println("HashSet Elements are : ");

        // Create an Object ob that will automatically
        // identify the type of object of HashSet to iterate
        // through set
        for (Object ob : S)
        {
            System.out.println(ob);
        }
    }
}
```

**Output**

```java
HashSet Elements are : 
1
4
30
100
15
```

## 方法 3: 使用集合类的 `addAll()` 方法

[`java.util.Set.addAll(Collection C)`](https://www.geeksforgeeks.org/set-addall-method-in-java-with-examples/#:~:text=addAll(Collection%20C)%20method%20is,without%20following%20any%20specific%20order.&text=Parameters%3A%20The%20parameter%20C%20is,be%20added%20to%20the%20set.) 方法用于将参数集合中的所有元素追加到现有集合中。元素是随机添加的，没有遵循任何特定的顺序。

**语法:**

```java
boolean addAll(Collection C)
```

**参数:** 参数 `C` 是要添加到集合中的任何类型的集合。

**返回值:** 如果该方法成功地将集合 `C` 的元素追加到该集合中，则该方法返回真，否则返回假。

```java
// Java program to demonstrate conversion of
// Set to array using addAll() method.

import java.util.*;
class GFG {
    public static void main(String[] args)
    {
        // Create a List
        List<Integer> L = new ArrayList<Integer>();

        // Add values to the List
        L.add(1);
        L.add(4);
        L.add(30);
        L.add(100);
        L.add(15);
        L.add(30);

        Set<Integer> S = new HashSet<Integer>();

        // Use addAll() method
        S.addAll(L);

        // Print values of Set
        System.out.println("HashSet Elements are : ");

        // Create an Object ob that will automatically
        // identify the type of object of HashSet to iterate
        // through set
        for (Object ob : S)
        {
            System.out.println(ob);
        }
    }
}
```

**Output**

```java
HashSet Elements are : 
1
4
30
100
15
```

## 方法 4: 使用 Java 中的流

**注:** Stream 只在 Java 8 或其以上版本中工作。

我们在 Java 中使用 `stream` 将给定的列表转换为流，然后流转换为 `set`。这仅适用于 Java 8 或之后的版本。

```java
// Java program to demonstrate conversion of
// Set to list using stream

import java.util.*;
class GFG {
    public static void main(String[] args)
    {
        // Create a List
        List<String> L = new ArrayList<String>();

        // Add values to the List
        L.add("Rohan");
        L.add("Ritik");
        L.add("Yogesh");
        L.add("Sangeeta");
        L.add("Palak");
        L.add("Laxmi");

        // create a stream from List and convert it into a
        // Set
        Set<String> S = L.stream().collect(Collectors.toSet());

        // Print values of Set
        System.out.println("HashSet Elements are : ");

        // Create an Object ob that will automatically
        // identify the type of object of HashSet to iterate
        // through set
        for (String ob : S)
        {
            System.out.println(ob);
        }
    }
}
```

**输出:**

```java
HashSet Elements are : 
Rohan
Ritik
Yogesh
Sangeeta
Palak
Laxmi
```