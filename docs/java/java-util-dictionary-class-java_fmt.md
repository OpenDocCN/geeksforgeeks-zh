# Java 中的 `Dictionary` 类

> 原文: [https://www.geeksforgeeks.org/java-util-dictionary-class-java/](https://www.geeksforgeeks.org/java-util-dictionary-class-java/)

`java.util.Dictionary` 是一个抽象类，表示键值映射关系，工作方式类似于 `Map`。给定一个键，您可以存储值，并在需要时使用它的键将值检索回来。因此，它是键值对的列表。

## 声明

```java
public abstract class Dictionary extends Object
```

## 构造函数

`Dictionary()` 是其唯一的构造函数。

## `Dictionary` 类的使用方法

### 1. `put(K key, V value)`

`java.util.Dictionary.put(K key, V value)` 向字典中添加键值对。

**语法:**

```java
public abstract V put(K key, V value)
```

**参数:**
- `key`
- `value`

**返回:**
- 映射到字典中的键值对。

### 2. `elements()`

`java.util.Dictionary.elements()` 返回字典中值的枚举表示。

**语法:**

```java
public abstract Enumeration elements()
```

**参数:**
- 无

**返回:**
- 字典中值的枚举。

### 3. `get(Object key)`

`java.util.Dictionary.get(Object key)` 返回与字典中指定键映射的值。

**语法:**

```java
public abstract V get(Object key)
```

**参数:**
- `key` - 我们想要获取其映射值的键。

**返回:**
- 与指定键映射的值。

### 4. `isEmpty()`

`java.util.Dictionary.isEmpty()` 检查字典是否为空。

**语法:**

```java
public abstract boolean isEmpty()
```

**参数:**
- 无

**返回:**
- 如果字典中没有键值对关系，则返回 `true`；否则返回 `false`。

### 5. `keys()`

`java.util.Dictionary.keys()` 返回字典中键的枚举表示。

**语法:**

```java
public abstract Enumeration keys()
```

**参数:**
- 无

**返回:**
- 字典中键的枚举。

### 6. `remove(Object key)`

`java.util.Dictionary.remove(Object key)` 移除用参数化键映射的键值对。

**语法:**

```java
public abstract V remove(Object key)
```

**参数:**
- `key` : 要移除的键。

**返回:**
- 与该键映射的值。

### 7. `size()`

`java.util.Dictionary.size()` 返回字典中键值对的个数。

**语法:**

```java
public abstract int size()
```

**参数:**
- 无

**返回:**
- 返回 `Dictionary` 中的键值对数量。

## Java 示例代码

```java
// Java Program explaining util.Dictionary class Methods
// put(), elements(), get(), isEmpty(), keys()
// remove(), size()

import java.util.*;
public class New_Class
{
    public static void main(String[] args)
    {

        // Initializing a Dictionary
        Dictionary geek = new Hashtable();

        // put() method
        geek.put("123", "Code");
        geek.put("456", "Program");

        // elements() method :
        for (Enumeration i = geek.elements(); i.hasMoreElements();)
        {
            System.out.println("Value in Dictionary : " + i.nextElement());
        }

        // get() method :
        System.out.println("\nValue at key = 6 : " + geek.get("6"));
        System.out.println("Value at key = 456 : " + geek.get("123"));

        // isEmpty() method :
        System.out.println("\nThere is no key-value pair : " + geek.isEmpty() + "\n");

        // keys() method :
        for (Enumeration k = geek.keys(); k.hasMoreElements();)
        {
            System.out.println("Keys in Dictionary : " + k.nextElement());
        }

        // remove() method :
        System.out.println("\nRemove : " + geek.remove("123"));
        System.out.println("Check the value of removed key : " + geek.get("123"));

        System.out.println("\nSize of Dictionary : " + geek.size());

    }
}
```

## 输出

```java
Value in Dictionary : Code
Value in Dictionary : Program

Value at key = 6 : null
Value at key = 456 : Code

There is no key-value pair : false

Keys in Dictionary : 123
Keys in Dictionary : 456

Remove : Code
Check the value of removed key : null

Size of Dictionary : 1
```

本文由 **Mohit Gupta _OMG** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [write.geeksforgeeks.org](http://www.write.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。