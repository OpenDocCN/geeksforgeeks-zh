# Java 中的可迭代接口

> 原文：[https://www.geeksforgeeks.org/iterable-interface-in-java/](https://www.geeksforgeeks.org/iterable-interface-in-java/)

在 JDK 1.5 中引入了 `Iterable` 接口。属于 `java.lang` 包。一般来说，实现 `Iterable` 的对象允许它被迭代。`Iterable` 接口允许对象成为增强 for 循环（for-each loop）的[目标。](https://www.geeksforgeeks.org/for-each-loop-in-java/)

`Iterable` 的定义

```java
public interface Iterable<T>
{
  Iterator<T>    iterator();

  Spliterator<T> spliterator();

  void           forEach(Consumer<? super T> action);
}
```

这里， `T` 是迭代器返回的元素类型。

## 迭代方式

有三种方法可以迭代 `Iterable` 的对象。

1.  使用增强 for 循环（for-each loop）
2.  使用迭代式 `forEach` 循环。
3.  使用 `Iterator<T>` 接口

## 使用增强 for 循环迭代可迭代的

实现 `Collection` 接口的类的对象可以使用增强 for 循环进行迭代，`Collection` 接口扩展了 `Iterable` 接口。

```java
// Java Program to demonstrate iterate 
// an iterable using for-each loop

import java.io.*;
import java.util.*;

class IterateUsingEnhancedForLoop {
    public static void main (String[] args) {

      // create a list
      List<String> list = new ArrayList<String>();

      // add elements
      list.add("Geeks");
      list.add("for");
      list.add("Geeks");

      // Iterate through the list
      for( String element : list ){
          System.out.println( element );
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

## 使用 forEach 循环迭代一个 Iterable

[`forEach()`](https://www.geeksforgeeks.org/iterable-foreach-method-in-java-with-examples/) 方法以 `lambda` 表达式为参数。为集合的每个元素调用这个 Lambda 表达式。在下面的例子中，对于列表中的每个元素，该函数将该元素打印到控制台。

```java
// Java Program to demonstrate iterate
// an Iterable using forEach method

import java.io.*;
import java.util.*;

class IterateUsingforEach {
    public static void main(String[] args)
    {
          // create a list
        List<String> list = new ArrayList<>();

          // add elements to the list
        list.add("Geeks");
        list.add("for");
        list.add("Geeks");

          // Iterate through the list
        list.forEach(
            (element) -> { System.out.println(element); });
    }
}
```

**输出**

```java
Geeks
for
Geeks
```

## 使用迭代器迭代可迭代对象

我们可以通过使用 `iterator()` 方法从 `Iterable` 中获取迭代器来迭代它的元素。

使用迭代器遍历集合执行操作时使用的方法有：

*   `hasNext()`：如果已到达集合的末尾，则返回 false，否则返回 true。
*   `next()`：返回集合中的下一个元素。
*   `remove()`：从集合中移除迭代器返回的最后一个元素。
*   `forEachRemaining()`：按顺序对集合中剩余的每个元素执行给定的操作。

```java
// Java Program to demonstrate iterate
// an Iterable using an Iterator

import java.io.*;
import java.util.*;

class IterateUsingIterator {
    public static void main(String[] args)
    {
        List<String> list = new ArrayList<>();

        list.add("Geeks");
        list.add("for");
        list.add("Geeks");

        Iterator<String> iterator = list.iterator();

        while (iterator.hasNext()) {
            String element = iterator.next();
            System.out.println(element);
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

### 可迭代的方法

| 方法 | 描述 |
| --- | --- |
| `forEach(Consumer<? super T> action)` | 对 `Iterable` 的每个元素执行给定的操作，直到所有元素都已处理或操作抛出异常。 |
| `iterator()` | 返回一个类型为 `T` 的元素的迭代器。 |
| `spliterator()` | 在此 `Iterable` 描述的元素上创建一个 `Spliterator`。 |

## 必须阅读

*   在 Java 中[实现 Iterator 和 Iterable 接口](https://www.geeksforgeeks.org/java-implementing-iterator-and-iterable-interface/)
*   [Iterator](https://www.geeksforgeeks.org/iterators-in-java/)

参考：[https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/lang/Iterable.html](https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/lang/Iterable.html)