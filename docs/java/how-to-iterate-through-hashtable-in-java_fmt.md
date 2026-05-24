# 如何在 Java 中迭代哈希表？

> 原文：[https://www.geeksforgeeks.org/how-to-iterate-through-hashtable-in-java/](https://www.geeksforgeeks.org/how-to-iterate-through-hashtable-in-java/)

[`HashTable`](https://www.geeksforgeeks.org/hashtable-in-java/) 是一个底层数据结构，其中 `HashTable` 中的插入顺序没有被保留，它基于键的 `hashcode`。不允许重复键，但值可以重复。键和值都允许使用异构对象。键和值都不允许为空值，否则我们会得到[运行时间异常](https://www.geeksforgeeks.org/java-program-to-handle-runtime-exceptions/)表示[空指针异常](https://www.geeksforgeeks.org/null-pointer-exception-in-java/)。它实现了 `Serializable` 和 `Cloneable` 接口，但没有实现 `RandomAccess`。其中的每个方法都是同步的，因此哈希表对象是线程安全的。如果我们频繁的操作是搜索操作，`HashTable` 是最好的选择。

## 方法

我们可以通过多种方式迭代哈希表，具体如下：

1.  使用 `Enumeration` 接口。
2.  使用 `keySet()` 方法获取集合，然后使用增强 `for` 循环。
3.  使用 `keySet()` 方法获取集合，然后使用迭代器接口。
4.  使用 `entrySet()` 方法获取集合，然后使用增强 `for` 循环。
5.  使用 `entrySet()` 方法获取集合，然后使用迭代器接口。
6.  从 Java 8 开始，使用 `Iterable.forEach()` 方法。

现在让我们逐一详细讨论所有方法的内部实现，以便通过哈希表更好地理解迭代。

### 方法 1：使用 `Enumeration` 接口

[`java.util.Enumeration`](https://www.geeksforgeeks.org/enumeration-interface-in-java/) 接口是预定义的接口之一，其对象用于从 `collections` 框架变量中检索数据。只能向前，不能向后。这个接口已经被 `Iterator` 取代了。

```java
// Java Program to Iterate through HashTable
// using enumeration interface

// Importing required packages
import java.util.*;
import java.util.Enumeration;

// Main Class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating Hashtable object where key is of Integer
        // type and value is of String type
        Hashtable<Integer, String> ht = new Hashtable<>();

        // Putting key-value pairs to HashTable object
        // Custom input entries
        ht.put(1, "Ram");
        ht.put(2, "Shyam");
        ht.put(3, "Bijay");
        ht.put(4, "Hritik");
        ht.put(5, "Piyush");

        // Creating Enumeration interface
        // and get keys() from Hashtable
        Enumeration<Integer> e = ht.keys();

        // Iterating through the Hashtable
        // object

        // Checking for next element in Hashtable object
        // with the help of hasMoreElements() method
        while (e.hasMoreElements()) {

            // Getting the key of a particular entry
            int key = e.nextElement();

            // Print and display the Rank and Name
            System.out.println("Rank : " + key
                               + "\t\t Name : "
                               + ht.get(key));
        }
    }
}
```

**输出**

```java
Rank : 5         Name : Piyush
Rank : 4         Name : Hritik
Rank : 3         Name : Bijay
Rank : 2         Name : Shyam
Rank : 1         Name : Ram
```

### 方法 2：使用 `keySet()` 方法进行映射和增强 `for` 循环

Java 中的 [`java.util.HashMap.keySet()`](https://www.geeksforgeeks.org/hashmap-keyset-method-in-java/) 方法用于创建一组包含在哈希映射中的关键元素。它基本上返回一个键的集合视图，或者我们可以创建一个新的集合并将键元素存储在其中。

```java
// Java program to iterate through HashTable
// using keySet method and enhance for-loop

// Importing required packages
import java.util.*;
import java.util.Set;

// Main Class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating Hashtable object in where key is of
        // Integer type
        // and value is of String type
        Hashtable<Integer, String> ht = new Hashtable<>();

        // Putting key-value pairs to HashTable object
        // custom entries
        ht.put(1, "Java");
        ht.put(2, "Scala");
        ht.put(3, "Python");
        ht.put(4, "Pearl");
        ht.put(5, "R");

        // Getting keySets of Hashtable and
        // storing it into Set
        Set<Integer> setOfKeys = ht.keySet();

        // Iterating through the Hashtable
        // object using for-Each loop
        for (Integer key : setOfKeys) {
            // Print and display the Rank and Name
            System.out.println("Rank : " + key
                               + "\t\t Name : "
                               + ht.get(key));
        }
    }
}
```

**输出**

```java
Rank : 5         Name : R
Rank : 4         Name : Pearl
Rank : 3         Name : Python
Rank : 2         Name : Scala
Rank : 1         Name : Java
```

### 方法 3：使用 `keySet()` 方法和迭代器接口

同样，我们将使用与上面示例中实现的方法相同的方法，但是在这里，为了迭代，我们将使用 `Iterable` 接口。

# Java 语言

## 方法 3：使用 `keySet()` 方法和 `Iterator` 接口

```java
// Java program to iterate through HashTable
// using keySet method and Iterator Interface

// Importing required libraries
import java.util.*;
import java.util.Iterator;
import java.util.Set;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating Hashtable object where key is of Integer
        // type
        // and value is of String type
        Hashtable<Integer, String> ht = new Hashtable<>();

        // Putting key-value pairs to HashTable object
        // Custom input entries
        ht.put(1, "Java");
        ht.put(2, "Scala");
        ht.put(3, "Python");
        ht.put(4, "Pearl");
        ht.put(5, "R");

        // Getting keySets of Hashtable and
        // storing it into Set
        Set<Integer> setOfKeys = ht.keySet();

        // Creating an Iterator object to
        // iterate over the given Hashtable
        Iterator<Integer> itr = setOfKeys.iterator();

        // Iterating through the Hashtable object
        // Checking for next element using hasNext() method
        while (itr.hasNext()) {

            // Getting key of a particular entry
            int key = itr.next();

            // Print and display the Rank and Name
            System.out.println("Rank : " + key
                               + "\t\t Name : "
                               + ht.get(key));
        }
    }
}
```

**输出**

```java
Rank : 5         Name : R
Rank : 4         Name : Pearl
Rank : 3         Name : Python
Rank : 2         Name : Scala
Rank : 1         Name : Java
```

## 方法 4：使用 `entrySet()` 方法和增强 for 循环

`java.util.HashMap.entrySet()` 方法用于创建一组包含在哈希映射中的相同元素。它基本上返回哈希映射的集合视图，或者我们可以创建一个新的集合并将映射元素存储到其中。

```java
// Java program to iterate through HashTable
// using entrySet method and enhance for-loop

// Importing required libraries
import java.util.*;
import java.util.Map.Entry;
import java.util.Set;
// Main Class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating Hashtable object where key is of Integer
        // type and value is of String type
        Hashtable<Integer, String> ht = new Hashtable<>();

        // Putting key-value pairs to HashTable object
        // Custom input entries
        ht.put(1, "Java");
        ht.put(2, "Scala");
        ht.put(3, "Python");
        ht.put(4, "Pearl");
        ht.put(5, "R");

        // Storing all entries of Hashtable
        // in a Set using entrySet() method
        Set<Entry<Integer, String> > entrySet
            = ht.entrySet();

        // Iterating through the Hashtable object
        // using for-each loop
        for (Entry<Integer, String> entry : entrySet) {

            // print ad display the Rank and Name
            System.out.println("Rank : " + entry.getKey()
                               + "\t\t Name : "
                               + entry.getValue());
        }
    }
}
```

**输出**

```java
Rank : 5         Name : R
Rank : 4         Name : Pearl
Rank : 3         Name : Python
Rank : 2         Name : Scala
Rank : 1         Name : Java
```

## 方法 5：使用 `entrySet()` 方法和 `Iterator` 接口

同样，我们将使用与上面示例中实现的方法相同的方法，但是在这里进行迭代时，我们将使用 `Iterable` 接口。

```java
// Java program to iterate through hashtable using
// entrySet method and Iterator interface

// Importing required libraries
import java.util.*;
import java.util.Iterator;
import java.util.Map.Entry;
import java.util.Set;

// Main Class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating Hashtable object where key is of Integer
        // type
        // and value is of String type
        Hashtable<Integer, String> ht = new Hashtable<>();

        // Putting key-value pairs to Hashtable object
        // Custom input entries
        ht.put(1, "Java");
        ht.put(2, "Scala");
        ht.put(3, "Python");
        ht.put(4, "Pearl");
        ht.put(5, "R");

        // Storing all entries of Hashtable in a Set
        // using entrySet() method
        Set<Entry<Integer, String> > entrySet
            = ht.entrySet();

        // Creating an Iterator object to
        // iterate over the given Hashtable
        Iterator<Entry<Integer, String> > itr
            = entrySet.iterator();

        // Iterating through the Hashtable object
        // using iterator

        // Checking for next element
        // using hasNext() method
        while (itr.hasNext()) {

            // Getting a particular entry of HashTable
            Entry<Integer, String> entry = itr.next();

            // Print and display the Rank and Name
            System.out.println("Rank : " + entry.getKey()
                               + "\t\t Name : "
                               + entry.getValue());
        }
    }
}
```

**输出**

```java
Rank : 5         Name : R
Rank : 4         Name : Pearl
Rank : 3         Name : Python
Rank : 2         Name : Scala
Rank : 1         Name : Java
```

## 方法 6：使用 Java 8 版中的 `Iterable.forEach()` 方法

随着 Java 8 版本的发布，他们改进了一些现有的 API，并增加了一些新功能。其中一个就是 `java.lang.Iterable` 接口中的 `forEach()` 方法。

```java
// Java program to iterate through HashTable
// using Iterable forEach()method of java 8

// Import required libraries
import java.util.*;

// Main Class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating Hashtable object in where key is of
        // Integer type
        // and value is of String type
        Hashtable<Integer, String> ht = new Hashtable<>();

        // Putting key-value pairs to HashTable object
        // Custom input entries
        ht.put(1, "Java");
        ht.put(2, "Scala");
        ht.put(3, "Python");
        ht.put(4, "Ruby");
        ht.put(5, "R");

        // Iterating through Hashtable using
        // forEach loop of java 8
        ht.forEach((key, value)
                       -> System.out.println(
                           "Rank : " + key
                           + "\t\t Name : " + value));
    }
}
```

**输出**

```java
Rank : 1         Name : Java
Rank : 2         Name : Scala
Rank : 3         Name : Python
Rank : 4         Name : Ruby
Rank : 5         Name : R
```