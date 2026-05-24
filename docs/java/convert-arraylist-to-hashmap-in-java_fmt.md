# 将数组列表转换为 Java 中的 HashMap

> 原文：[https://www.geeksforgeeks.org/convert-arraylist-to-hashmap-in-java/](https://www.geeksforgeeks.org/convert-arraylist-to-hashmap-in-java/)

[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)可以转换成[HashMap](https://www.geeksforgeeks.org/java-util-hashmap-in-java-with-examples/)，但是`HashMap`不维护数组列表的顺序。为了维护顺序，我们可以使用`LinkedHashMap`，它是`HashMap`的一个实现。

基本上，有两种不同的方式将`ArrayList`转换为`HashMap`：

1.  使用数组列表迭代
2.  使用带有`LinkedHashMap`的数组列表迭代

## 使用数组列表迭代

在这里，我们只需要迭代数组列表的每个元素，元素就可以转换成键值对并存储在`HashMap`中。

```java
// Java program to convert ArrayList
// to HashMap

import java.util.ArrayList;
import java.util.Arrays;
import java.util.HashMap;
import java.util.Map;

public class ArrayListExample {
    public static void main(String[] args)
    {

        // ArrayList of string
        ArrayList<String> languageList
           = new ArrayList<>(Arrays.asList("Java", "C++", "Python", 
                                           "PHP", "NodeJS"));

        System.out.println(
            "-------------ArrayList---------------");

        // printing the ArrayList
        for (String language : languageList)
        {
           System.out.println(language);
        }

        System.out.println(
            "--------------HashMap----------------");

        // convertArrayListToHashMap() method directly 
        // converts ArrayList to Hashmap
        HashMap<String, Integer> languageMap = convertArrayListToHashMap(languageList);

        // printing the HashMap
        for (Map.Entry<String, Integer> entry : languageMap.entrySet()) {

            System.out.println(entry.getKey() + " : "
                               + entry.getValue());
        }
    }

    private static HashMap<String, Integer>
        convertArrayListToHashMap(ArrayList<String> arrayList)
    {

        HashMap<String, Integer> hashMap = new HashMap<>();

        for (String str : arrayList) {

            hashMap.put(str, str.length());
        }

        return hashMap;
    }
}
```

**Output**

```java
-------------ArrayList---------------
Java
C++
Python
PHP
NodeJS
--------------HashMap----------------
Java : 4
C++ : 3
PHP : 3
NodeJS : 6
Python : 6
```

## 使用带有 LinkedHashMap 的数组列表迭代

*   这里，数组列表被转换成一个散列表，但是普通的`HashMap`并不维持数组列表的顺序。
*   为了维护顺序，我们使用了`LinkedHashMap`，它是`HashMap`的一个实现，帮助我们维护元素的插入顺序，我们可以很容易地将`ArrayList`转换成`LinkedHashMap`。

```java
// Java program to convert ArrayList
// to HashMap

import java.util.ArrayList;
import java.util.Arrays;
import java.util.HashMap;
import java.util.*;

public class ArrayListExample {
    public static void main(String[] args)
    {
        // ArrayList of string
        ArrayList<String> languageList
            = new ArrayList<>(Arrays.asList(
                "Java", "C++", "Python", "PHP", "NodeJS"));

        System.out.println(
            "-------------ArrayList---------------");

        // printing the ArrayList
        for (String language : languageList) {

            System.out.println(language);
        }

        System.out.println(
            "--------------HashMap----------------");

        // convertArrayListToHashMap() method directly 
        // converts ArrayList to HashMap
        HashMap<String, Integer> languageMap
            = convertArrayListToHashMap(languageList);

        // printing the HashMap
        for (Map.Entry<String, Integer> entry :
             languageMap.entrySet()) {

            System.out.println(entry.getKey() + " : "
                               + entry.getValue());
        }
    }

    private static HashMap<String, Integer>
                           convertArrayListToHashMap(ArrayList<String> arrayList)
    {

        LinkedHashMap<String, Integer> linkedHashMap
                                      = new LinkedHashMap<>();

        for (String str : arrayList) {

            linkedHashMap.put(str, str.length());
        }

        return linkedHashMap;
    }
}
```

**Output**

```java
-------------ArrayList---------------
Java
C++
Python
PHP
NodeJS
--------------HashMap----------------
Java : 4
C++ : 3
Python : 6
PHP : 3
NodeJS : 6
```