# 检查 Java HashMap 中是否存在特定密钥

> 原文：[https://www.geeksforgeeks.org/check-if-particular-key-exists-in-java-hashmap/](https://www.geeksforgeeks.org/check-if-particular-key-exists-in-java-hashmap/)

[`HashMap`](https://www.geeksforgeeks.org/java-util-hashmap-in-java-with-examples/) 在 Java 中是实现了 Hash Table 数据结构的排序。它由键和值对组成，符号表示为`< K, V >`，其中`K`代表键，`V`代表值。它是映射接口的一个实现，并且在分别通过`put`和`get`方法分配和访问元素时提供了恒定的时间性能。它用于形成关联的对，并基于另一对访问或修改一个对。

有多种方法可以检查特定的键是否存在，如下所述：

*   使用 `HashMap` 类内置的 `containsKey()` 方法。
*   将 `HashMap` 的键转换为一个列表，然后遍历它们。
*   从 `HashMap` 的所有条目创建一个映射，然后遍历它。

## 方法 1

使用这种方法，我们使用了 `HashMap` 类的 [`containsKey()`](https://www.geeksforgeeks.org/hashmap-containskey-method-in-java/) 预定义方法，该方法返回一个布尔值。

**语法：**

```java
Hash_Map.containsKey(key_element)
```

**参数：** 该方法只取一个参数 `key_element`，该参数是指映射应该在地图内部检查的键。

**返回值：** 如果检测到键的存在，则该方法返回布尔真，否则返回假。

**算法：**

1.  创建一个返回类型为布尔值的函数。
2.  在函数内部，创建一个新的 `HashMap`，分别指定键和值的数据类型。
3.  使用 `HashMap` 类的 `put()` 方法用键值对填充 `HashMap`。
4.  声明一个布尔变量来存储结果。
5.  调用 `HashMap` 类的 `containsKey()` 方法，将要检查的键作为参数。
6.  返回一个变量。

**代码：**

```java
// java program to check if a particular
// key exists in HashMap

import java.util.*;

class GFG {

// declaring the method
    // the parameter keyToBeChecked is the
    // key to be checked
    boolean checkForKey(String keyToBeChecked)
    {

// initializing the hashmap
        HashMap<String, Integer> hashMap =
          new HashMap<>();

// filling the key - value pairs in hashmap
        hashMap.put("first", 1);
        hashMap.put("second", 2);
        hashMap.put("third", 3);
        hashMap.put("fourth", 4);

// variable to store the boolean value
        // for result
        boolean result
            = hashMap.containsKey(keyToBeChecked);

// returning the result
        return result;
    }

// Driver Code
    public static void main(String[] args)
    {

// instantiating the class
        GFG ob = new GFG();

// displaying and calling the checkForKey()
        // method
        System.out.println(ob.checkForKey("fourth"));
    }
}
```

**输出**

```java
true
```

## 方法 2

我们从 `HashMap` 的键创建一个 `ArrayList`，然后遍历它们来检查指定的键是否存在。

**算法：**

1.  重复第一种方法中提到的步骤 1 到 3。
2.  接下来，我们使用 `HashMap` 类的预定义方法 `keySet()` 来初始化一个与 `HashMap` 键数据类型相同的 `ArrayList`。
3.  接下来，我们声明一个迭代器来遍历上面创建的 `ArrayList` 的元素。
4.  然后，如果特定键与上面创建的数组列表中的任何元素匹配，我们将在每次迭代中遍历数组列表进行检查。
5.  返回相应的输出。

**代码：**

```java
// java program to check if a particular
// key exists in the HashMap

import java.util.*;

class GFG {

// declaring the method
    // the parameter keyToBeChecked is
    // the key to be checked
    boolean checkForKey(String keyToBeChecked)
    {

// initializing the HashMap
        HashMap<String, Integer> hashMap =
          new HashMap<>();

// filling the key-value pairs
        // in the HashMap
        hashMap.put("first", 1);
        hashMap.put("second", 2);
        hashMap.put("third", 3);
        hashMap.put("fourth", 4);

// creating an ArrayList from the keys
        ArrayList<String> listOfKeys
            = new ArrayList<>(hashMap.keySet());

// declaring the iterator
        Iterator<String> itr = listOfKeys.iterator();

// loop to iterate through the
        // elements of the ArrayList
        while (itr.hasNext()) {

// condition to check against
            // the specific key
            if (itr.next() == keyToBeChecked)
                return true;
        }
        return false;
    }

// Driver Code
    public static void main(String[] args)
    {

// instantiating the class
        GFG ob = new GFG();

// displaying and calling the
        // checkForKey method
        System.out.println(ob.checkForKey("second"));
    }
}
```

**输出**

```java
true
```

## 方法 3

我们遍历这些键，检查指定的键是否存在。

**算法：**

1.  重复第一种方法中的步骤 1 到 3 以创建一个 `HashMap`。
2.  使用 `HashMap` 类的预定义方法 `for each` 循环和 `entrySet()` 来创建一个相同的映射。
3.  在 `for` 循环的每次迭代中，使用 `Map` 类内置的 [`getKey()`](https://www.geeksforgeeks.org/java-tuples-getkey-method/#:~:text=The%20getKey()%20method%20in,index%200%20of%20the%20KeyValueClassObject.) 方法从上面构造的映射中获取一个键。
4.  与指定的键进行比较。
5.  如果键与键集中的任何元素匹配，则返回 `true`，否则返回 `false`。

**代码：**

```java
// java program to check if a particular
// key exists in the HashMap

import java.util.*;

class GFG {

// declaring the method
    // the parameter keyToBeChecked specifies
    // the particular key
    boolean checkForKey(String keyToBeChecked)
    {

// initializing the HashMap
        HashMap<String, Integer> hashMap = new HashMap<>();

// filling up the key-value
        // pairs in the HashMap
        hashMap.put("first", 1);
        hashMap.put("second", 2);
        hashMap.put("third", 3);
        hashMap.put("fourth", 4);

// initializing the for each loop
        // using which the entries of the
        // HashMap are stored in a Set
        for (Map.Entry<String, Integer> mapEntries :
             hashMap.entrySet()) {

// getting the keys and checking
            // against the specified key
            if (mapEntries.getKey() == keyToBeChecked)
                return true;
        }
        return false;
    }

// Driver Code
    public static void main(String[] args)
    {

// instantiating the class
        GFG ob = new GFG();

// displaying and calling the
        // checkForKey method
        System.out.println(ob.checkForKey("seventh"));
    }
}
```

**输出**

```java
false
```