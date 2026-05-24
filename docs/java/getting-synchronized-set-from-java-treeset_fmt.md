# 从 Java 树集中获取同步集

> 原文：[https://www.geeksforgeeks.org/getting-synchronized-set-from-java-treeset/](https://www.geeksforgeeks.org/getting-synchronized-set-from-java-treeset/)

在 [`java.util.Collections`](https://www.geeksforgeeks.org/collections-in-java-2/) 类中，`synchronizedSet()` 方法用于返回由指定集合支持的同步（线程安全）集合。此方法将 `TreeSet` 作为参数。为了保证串行访问，通过返回的集合完成对支持集合的所有访问是非常关键的。我们有 Java `TreeSet`，我们的任务是从中获取一个同步集。为此，请使用 `Collections` 类的 `synchronizedSet` 方法。

## 示例

```java
Input : HashSet = [3, 4, 5]
Output: synchronizedSet = [3, 4, 5]

Input : HashSet = ['A', 'B', 'C']
Output: synchronizedSet = ['A', 'B', 'C']
```

## 语法

```java
public static <T> Set<T> synchronizedSet(Set<T> s)
```

## 参数

`TreeSet` 作为一个要“包装”在同步集中的参数。

## 返回值

```java
Synchronized view of the specified set.
```

## 方法

1.  创建一个 [`TreeSet`](https://www.geeksforgeeks.org/treeset-in-java-with-examples/)。
2.  向 `TreeSet` 中添加一些元素。
3.  创建一个集合变量，并使用 `Collections.synchronizedSet()` 方法为其赋值。
4.  打印新的同步集合。

下面是上述方法的实现：

```java
// Java program to get synchronized
// set from given tree set
import java.util.Collections;
import java.util.Set;
import java.util.TreeSet;

class GFG {
    public static void main(String[] args)
    {
        TreeSet<Integer> treeSet = new TreeSet<Integer>();

        // Elements are added using add() method
        treeSet.add(48);
        treeSet.add(49);
        treeSet.add(59);
        treeSet.add(38);
        System.out.println("TreeSet : "+treeSet);

        // converting tree set to synchronized set
        Set set = Collections.synchronizedSet(treeSet);
        System.out.println("SynchronizedSet : "+set);
    }
}
```

## 输出

```
TreeSet : [38, 48, 49, 59]
SynchronizedSet : [38, 48, 49, 59]
```