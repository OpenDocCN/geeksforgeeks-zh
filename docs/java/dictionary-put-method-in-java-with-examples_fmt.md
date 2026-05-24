# Java 中的 `Dictionary.put()` 方法详解（带示例）

> 原文：[https://www.geeksforgeeks.org/dictionary-put-method-in-java-with-examples/](https://www.geeksforgeeks.org/dictionary-put-method-in-java-with-examples/)

`Dictionary` 的 `put()` 方法用于将键值对映射插入到字典中。这意味着特定的键和值可以映射到特定的字典中。

## 语法

```java
dictionary.put(key, value)
```

## 参数

该方法接受两个参数，都是字典的对象类型。

*   `Key`：需要插入字典进行映射的键元素。
*   `Value`：上述键将映射到的值。

## 返回值

方法返回键之前映射到的值。如果键之前没有映射到任何值，则返回 `null`。

以下程序用于说明 `java.util.Dictionary.put()` 方法：

### 程序 1

```java
// Java code to illustrate the put() method
import java.util.*;

public class Dictionary_Demo {
    public static void main(String[] args)
    {

// Creating an empty Dictionary
        Dictionary<Integer, String> dict
            = new Hashtable<Integer, String>();

// Inserting values into the Dictionary
        dict.put(10, "Geeks");
        dict.put(15, "4");
        dict.put(20, "Geeks");
        dict.put(25, "Welcomes");
        dict.put(30, "You");

// Displaying the Dictionary
        System.out.println("Initial Dictionary is: " + dict);

// Inserting existing key along with new value
        String returned_value = (String)dict.put(20, "All");

// Verifying the returned value
        System.out.println("Returned value is: " + returned_value);

// Displaying the new table
        System.out.println("New Dictionary is: " + dict);
    }
}
```

**输出：**

```java
Initial Dictionary is: {10=Geeks, 20=Geeks, 30=You, 15=4, 25=Welcomes}
Returned value is: Geeks
New Dictionary is: {10=Geeks, 20=All, 30=You, 15=4, 25=Welcomes}
```

### 程序 2

```java
// Java code to illustrate the put() method
import java.util.*;

public class Dictionary_Demo {
    public static void main(String[] args)
    {

// Creating an empty Dictionary
        Dictionary<Integer, String> dict
            = new Hashtable<Integer, String>();

// Inserting values into the Dictionary
        dict.put(10, "Geeks");
        dict.put(15, "4");
        dict.put(20, "Geeks");
        dict.put(25, "Welcomes");
        dict.put(30, "You");

// Displaying the Dictionary
        System.out.println("Initial Dictionary is: " + dict);

// Inserting existing key along with new value
        String returned_value = (String)dict.put(50, "All");

// Verifying the returned value
        System.out.println("Returned value is: " + returned_value);

// Displaying the new table
        System.out.println("New Dictionary is: " + dict);
    }
}
```

**输出：**

```java
Initial Dictionary is: {10=Geeks, 20=Geeks, 30=You, 15=4, 25=Welcomes}
Returned value is: null
New Dictionary is: {10=Geeks, 20=Geeks, 30=You, 50=All, 15=4, 25=Welcomes}
```