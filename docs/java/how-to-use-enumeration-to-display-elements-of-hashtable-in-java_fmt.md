# Java 中如何用枚举显示哈希表的元素？

> 原文：[https://www.geeksforgeeks.org/how-to-use-enumeration-to-display-elements-of-hashtable-in-java/](https://www.geeksforgeeks.org/how-to-use-enumeration-to-display-elements-of-hashtable-in-java/)

[`Hashtable`](https://www.geeksforgeeks.org/hashtable-in-java/) 类实现了一个哈希表，将键映射到值。任何非空对象都可以用作键或值。为了成功地从哈希表中存储和检索对象，用作键的对象必须实现 `hashCode` 方法和 `equals` 方法。

现在，我们可以使用 [`key()`](https://www.geeksforgeeks.org/hashtable-keys-method-in-java/) 和 [`elements()`](https://www.geeksforgeeks.org/hashtable-elements-method-in-java/) 方法将哈希表的键和值作为枚举对象。我们可以使用像 [`hasMoreElements()`](https://www.geeksforgeeks.org/enumeration-hasmoreelements-method-in-java-with-examples/) 和 [`nextElement()`](https://www.geeksforgeeks.org/enumeration-nextelement-method-in-java-with-examples/) 这样的枚举方法分别获取所有键和值作为枚举对象，我们可以读取一个哈希表对应的所有键和值。

**示例 1：**

```java
// Java Program to Demonstrate Getting Values
// as an Enumeration of Hashtable class

import java.io.*;
import java.util.Enumeration;
import java.util.Hashtable;

// Main class
// EnumerationOnKeys
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating an empty hashtable
        Hashtable<Integer, String> ht
            = new Hashtable<Integer, String>();

        // Inserting key-value pairs into hash table
        // using put() method
        ht.put(1, "Geeks");
        ht.put(2, "for");
        ht.put(3, "Geeks");

        // Now creating an Enumeration object
        //  to read elements
        Enumeration e = ht.elements();

        // Condition holds true till there is
        // single key remaining

        // Printing elements of hashtable
        // using enumeration
        while (e.hasMoreElements()) {

            // Printing the current element
            System.out.println(e.nextElement());
        }
    }
}
```

**输出**

```java
Geeks
for
Geeks
```

**示例 2：**

```java
// Java Program to Demonstrate Getting Keys
// as an Enumeration of Hashtable class

// Importing required classes
import java.io.*;
import java.util.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating an empty hashtable
        Hashtable<String, String> ht
            = new Hashtable<String, String>();

        // Inserting key-value pairs into hash table
        // using put() method
        ht.put("Name", "Rohan");
        ht.put("Age", "23");
        ht.put("Address", "India");
        ht.put("Article", "GeeksforGeeks");

        // Now creating an Enumeration object
        // to store keys
        Enumeration<String> e = ht.keys();

        // Condition holds true till there is
        // single key remaining
        while (e.hasMoreElements()) {

            // Getting key
            String key = e.nextElement();

            // Printing key and value corresponding to
            // that key
            System.out.println(key + ":" + ht.get(key));
        }
    }
}
```

**输出**

```java
Name:Rohan
Article:GeeksforGeeks
Age:23
Address:India
```