# AbstractSequentialList contains()方法详解

> 原文：[https://www.geeksforgeeks.org/abstractsequentiallist-contains-method-in-java-with-example/](https://www.geeksforgeeks.org/abstractsequentiallist-contains-method-in-java-with-example/)

`AbstractSequentialList`的`contains()`方法用于检查集合中是否存在元素。它将元素作为参数，如果元素存在于集合中，则返回`true`。

## 语法

```java
public boolean contains(Object element)
```

## 参数

参数`element`为集合类型。此参数引用需要在集合中检查其出现的元素。

## 返回值

该方法返回一个`boolean`值。如果元素存在于集合中，则返回`true`，否则返回`false`。

下面的程序说明了`AbstractSequentialList.contains()`方法：

## 程序 1

```java
// Java code to illustrate
// AbstractSequentialList.contains()

import java.util.*;

public class GFG {
    public static void main(String args[])
    {

        // Creating an empty Collection
        AbstractSequentialList<String>
            abs = new LinkedList<String>();

        // Use add() method to add
        // elements in the collection
        abs.add("Geeks");
        abs.add("for");
        abs.add("Geeks");
        abs.add("10");
        abs.add("20");

        // Displaying the collection
        System.out.println("AbstractSequentialList: "
                           + abs);

        // Check if the collection contains "Hello"
        System.out.println("\nDoes the Collection"
                           + " contains 'Hello': "
                           + abs.contains("Hello"));

        // Check if the Collection contains "20"
        System.out.println("Does the collection"
                           + " contains '20': "
                           + abs.contains("20"));

        // Check if the Collection contains "Geeks"
        System.out.println("Does the Collection"
                           + " contains 'Geeks': "
                           + abs.contains("Geeks"));
    }
}
```

## Output

```java
AbstractSequentialList: [Geeks, for, Geeks, 10, 20]

Does the Collection contains 'Hello': false
Does the collection contains '20': true
Does the Collection contains 'Geeks': true
```

## 程序 2

```java
// Java code to illustrate
// AbstractSequentialList.contains()

import java.util.*;

public class GFG {
    public static void main(String args[])
    {

        // Creating an empty Collection
        AbstractSequentialList<Integer>
            abs = new LinkedList<Integer>();

        // Use add() method to add
        // elements in the collection
        abs.add(10);
        abs.add(20);
        abs.add(30);
        abs.add(40);
        abs.add(50);

        // Displaying the collection
        System.out.println("AbstractSequentialList:"
                           + abs);

        // Check if the collection contains 10
        System.out.println("\nDoes the Collection "
                           + "contains '10': "
                           + abs.contains(10));

        // Check if the collection contains 50
        System.out.println("\nDoes the Collection"
                           + " contains '50': "
                           + abs.contains(50));

        // Check if the Collection contains 100
        System.out.println("Does the collection"
                           + " contains '100': "
                           + abs.contains(100));
    }
}
```

## Output

```java
AbstractSequentialList:[10, 20, 30, 40, 50]

Does the Collection contains '10': true

Does the Collection contains '50': true
Does the collection contains '100': false
```