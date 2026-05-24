# 如何从 Java TreeMap 中删除第一个条目或最后一个条目？

> 原文：[https://www.geeksforgeeks.org/how-to-remove-the-first-entry-or-last-entry-from-the-java-treemap/](https://www.geeksforgeeks.org/how-to-remove-the-first-entry-or-last-entry-from-the-java-treemap/)

`TreeMap` 是 `Map` 接口的实现类。它允许根据关键字对对象进行排序，排序可以是自然排序，也可以使用比较器。插入顺序也不会保留在 `TreeMap` 中。

**语法：**

```java
TreeMap<String,Integer> map = new TreeMap<>();
```

在下面的例子中，我们将创建一个 `TreeMap`，并使用 `put()` 方法在其中插入记录。当 `TreeMap` 根据关键字对记录进行排序时，您可以看到输出是按从 a 到 z 的关键字排序的。为了迭代 `TreeMap`，我们使用 `keySet()` 方法迭代 `TreeMap` 的所有关键字，该方法给出了 `TreeMap` 的所有关键字。

## Java 实现

```java
// Java Program to remove the first entry
// or last entry from TreeMap
import java.io.*;
import java.util.TreeMap;
import java.util.Set;

class GFG {

    public static void main(String[] args)
    {

        // treemap with keys as string and
        // values of type integer
        TreeMap<String, Integer> gfg = new TreeMap<>();

        // adding values to treemap
        gfg.put("interviews", 97);
        gfg.put("fang", 86);
        gfg.put("competitive programming", 95);
        gfg.put("dsa", 99);
        gfg.put("java", 99);
        gfg.put("c++", 99);

        // iterating over the treemap
        for (String key : gfg.keySet()) {
            System.out.println(key + "," + gfg.get(key));
        }
    }
}
```

**输出**

```java
c++,99
competitive programming,95
dsa,99
fang,86
interviews,97
java,99
```

## 从 TreeMap 中删除第一个和最后一个条目

### 1. 使用 `pollFirstEntry()` 和 `pollLastEntry()` 方法

`TreeMap` 有两种方法可以删除第一个和最后一个条目。`pollFirstEntry()` 删除第一个条目，`pollLastEntry()` 删除最后一个条目。

**语法：**

```java
mapObject.pollFirstEntry();
mapObject.pollLastEntry();
```

**返回类型：** 两种方法的返回类型都是从地图中移除的条目对象。

首先，我们将创建一个 `TreeMap`，并使用 `put()` 方法在其中添加记录，然后使用 for 循环打印所有记录。对于打印，我们将使用通过 `keySet()` 方法获得的所有键。现在我们将在 `TreeMap` 上使用 `pollFirstEntry()` 和 `pollLastEntry()` 来移除第一个和最后一个条目。删除第一个和最后一个条目后，我们将再次使用 for 循环遍历 `TreeMap`。

## Java 实现

```java
// Java Program remove the first entry
// or last entry from the TreeMap
import java.io.*;
import java.util.TreeMap;
import java.util.Set;

class GFG {
    public static void main(String[] args)
    {

        // treemap with keys as string and values of type
        // integer
        TreeMap<String, Integer> gfg = new TreeMap<>();

        // adding values to tree map
        gfg.put("Interviews", 97);
        gfg.put("fang", 86);
        gfg.put("competitive programming", 95);
        gfg.put("dsa", 99);
        gfg.put("java", 99);
        gfg.put("c++", 99);

        System.out.println(
            "-------before removing first and last entry-------");

        // iterating over the treemap in java
        for (String key : gfg.keySet()) {
            System.out.println(key + "," + gfg.get(key));
        }

        // removing and printing first entry
        System.out.println(
            "----printing the first removed entry----");

        System.out.println(gfg.pollFirstEntry());

        // removing and printing last entry
        System.out.println(
            "----printing the last removed entry");

        System.out.println(gfg.pollLastEntry());

        System.out.println(
            "-------after removing first and last entry-------");

        // iterating over the treemap
        for (String key : gfg.keySet()) {
            System.out.println(key + "," + gfg.get(key));
        }
    }
}
```

**输出**

```java
-------before removing first and last entry-------
Interviews,97
c++,99
competitive programming,95
dsa,99
fang,86
java,99
----printing the first removed entry----
Interviews=97
----printing the last removed entry
java=99
-------after removing first and last entry-------
c++,99
competitive programming,95
dsa,99
fang,86
```

### 2. 使用 `lastKey()` 和 `firstKey()` 方法

**语法：**

```java
map.remove(map.lastKey());
map.remove(map.firstKey());
```

**思路：**

首先，我们将创建 `TreeMap`，并使用 `put()` 方法在其中插入一条记录。现在，我们将使用 for 循环打印所有记录，输出将按照从 a 到 z 的键排序顺序。要删除第一个条目和最后一个条目，我们将使用 `remove(key)` 方法。在 `remove` 方法中，我们需要将键作为参数传递。现在，如果我们能获得第一个和最后一个键，我们将能够删除第一个和最后一个条目。`TreeMap` 给了我们两个这样的方法，它们可以给我们第一个和最后一个键，即 `firstKey()` 和 `lastKey()`。在获取这些键之后，我们将在 `remove()` 方法中传递这些键，然后再次使用 for 循环打印 `TreeMap` 中的值。

## Java 实现

```java
// Java Program to remove the first entry
// or last entry from the TreeMap
import java.io.*;
import java.util.TreeMap;
import java.util.Set;

class GFG {
    public static void main(String[] args)
    {

        // treemap with keys as string and values of type
        // integer
        TreeMap<String, Integer> gfg = new TreeMap<>();

        gfg.put("Interviews", 97);
        gfg.put("fang", 86);
        gfg.put("competitive programming", 95);
        gfg.put("dsa", 99);
        gfg.put("java", 99);
        gfg.put("c++", 99);

        // iterating over the treemap in java
        System.out.println(
            "-------before removing first and last entry-------");

        for (String key : gfg.keySet()) {
            System.out.println(key + "," + gfg.get(key));
        }

        // removing first entry through firstKey()
        gfg.remove(gfg.firstKey());

        // removing last entry through lastKey()
        gfg.remove(gfg.lastKey());

        System.out.println(
            "-------after removing first and last entry-------");

        // iterating over the treemap
        for (String key : gfg.keySet()) {
            System.out.println(key + "," + gfg.get(key));
        }
    }
}
```

**输出**

```java
-------before removing first and last entry-------
Interviews,97
c++,99
competitive programming,95
dsa,99
fang,86
java,99
-------after removing first and last entry-------
c++,99
competitive programming,95
dsa,99
fang,86
```

### 3. 使用 `stream()`

在这里，我们将使用 `stream` 获取第一个和最后一个键，然后对其调用 `remove` 方法。

**语法：**

```java
firstkey = map.entrySet().stream().findFirst().get()
treemap.remove(firstkey);

lastkey = map.entrySet().stream().skip(map.size()-1).findFirst().get()
treemap.remove(lastkey);
```

**思路：**

在这里，我们将创建一个 `TreeMap`，并使用 `put()` 方法在其中添加记录，然后使用 for 循环打印每个记录。现在我们将使用 `stream` 来获取第一个和最后一个键。对于第一个键，我们将使用 `keySet()` 方法获得一组所有的键，然后我们将在其上使用 `stream()`。现在为了从流中获得第一个项（一条记录），我们将在其上使用 `findFirst()` 和 `get()` 来获得第一个键，然后在 `remove` 方法中传递这个键来移除第一个条目（一条记录）。

对于最后一个键，我们将再次对所有键使用 `keySet()`，在其后使用 `stream()`，现在我们将跳过 n-1 个元素，因为如果我们跳过前 n-1 个记录，那么最终我们将到达最后一个记录。为了得到 n（总记录数或 `TreeMap` 的大小），我们使用 `size()` 方法。

## Java 实现

```java
// Java Program to remove the first entry
// or last entry from the TreeMap
import java.io.*;
import java.util.TreeMap;
import java.util.Set;
import java.util.Map;

class GFG {
    public static void main(String[] args)
    {

        // treemap with keys as string and values of type
        // integer
        TreeMap<String, Integer> gfg = new TreeMap<>();

        gfg.put("Interviews", 97);
        gfg.put("fang", 86);
        gfg.put("competitive programming", 95);
        gfg.put("dsa", 99);
        gfg.put("java", 99);
        gfg.put("c++", 99);

        // iterating over the treemap in java
        System.out.println(
            "-------before removing first and last entry-------");

        for (String key : gfg.keySet()) {
            System.out.println(key + "," + gfg.get(key));
        }

        // removing first entry through stream
        String firstkey = gfg.keySet().stream().findFirst().get();
        gfg.remove(firstkey);

        // removing last entry through stream
        String lastkey = gfg.keySet().stream().skip(gfg.size() - 1).findFirst().get();
        gfg.remove(lastkey);

        System.out.println(
            "-------after removing first and last entry-------");

        // iterating over the treemap
        for (String key : gfg.keySet()) {
            System.out.println(key + "," + gfg.get(key));
        }
    }
}
```

**输出**

```java
-------before removing first and last entry-------
Interviews,97
c++,99
competitive programming,95
dsa,99
fang,86
java,99
-------after removing first and last entry-------
c++,99
competitive programming,95
dsa,99
fang,86
```

## Java 语言

```java
// Java Program remove the first entry
// or last entry from the TreeMap
import java.io.*;
import java.util.TreeMap;
import java.util.Set;

class GFG {
    public static void main(String[] args)
    {
        // treemap with keys as string and values of type
        // integer
        TreeMap<String, Integer> gfg = new TreeMap<>();

        gfg.put("Interviews", 97);
        gfg.put("fang", 86);
        gfg.put("competitive programming", 95);
        gfg.put("dsa", 99);
        gfg.put("java", 99);
        gfg.put("c++", 99);

        // iterating over the treemap in java
        System.out.println(
            "-------before removing first and last entry-------");

        for (String key : gfg.keySet()) {
            System.out.println(key + "," + gfg.get(key));
        }

        // removing first entry through firstKey()
        String firstKey
            = gfg.keySet().stream().findFirst().get();
        gfg.remove(firstKey);

        // removing last entry through lastKey()
        String lastKey = gfg.keySet()
                             .stream()
                             .skip(gfg.size() - 1)
                             .findFirst()
                             .get();
        gfg.remove(lastKey);

        System.out.println(
            "-------after removing first and last entry-------");

        // iterating over the treemap
        for (String key : gfg.keySet()) {
            System.out.println(key + "," + gfg.get(key));
        }
    }
}
```

**Output**

```java
-------before removing first and last entry-------
Interviews,97
c++,99
competitive programming,95
dsa,99
fang,86
java,99
-------after removing first and last entry-------
c++,99
competitive programming,95
dsa,99
fang,86
```