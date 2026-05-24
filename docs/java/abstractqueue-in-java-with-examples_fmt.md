# Java 中的抽象队列，示例

> 原文: [https://www.geeksforgeeks.org/abstractqueue-in-java-with-examples/](https://www.geeksforgeeks.org/abstractqueue-in-java-with-examples/)

Java 中的 `AbstractQueue` 类是 [Java 集合框架](https://www.geeksforgeeks.org/collections-in-java-2/)的一部分，实现了 `Collection` 接口和 [`AbstractCollection`](https://www.geeksforgeeks.org/abstractcollection-in-java-with-examples/#:~:text=The%20AbstractCollection%20class%20in%20Java,iterator%20and%20the%20size%20methods.) 类。它提供了一些 `Queue` 操作的框架实现。当基本实现不允许空元素时，此类中的实现是合适的。方法 `add`、`remove` 和 `element` 分别基于 `offer`、`poll` 和 `peek`，但是抛出异常，而不是通过 `false` 或 `null` 返回来指示失败。

**继承等级:**

```java
java.lang.Object
 ↳ java.util.AbstractCollection<E>
    ↳ Class AbstractQueue<E>
```

![AbstractQueue in Java](img/9232b044a49d8dd24479ec58e80c87bd.png)

该类实现了 `Iterable<E>`、`Collection<E>`、`Queue<E>` 接口，扩展了 [`AbstractCollection`](https://www.geeksforgeeks.org/abstractcollection-in-java-with-examples/#:~:text=The%20AbstractCollection%20class%20in%20Java,iterator%20and%20the%20size%20methods)。

**声明:**

```java
public abstract class AbstractQueue<E> extends AbstractCollection<E> implements Queue<E>
```

`E` – 集合框架类或接口维护的元素类型。

## Java 抽象队列中的构造函数

由于 `AbstractQueue` 是一个抽象类，它的实现是由其子类提供的。下面显示了可以提供实现的类的列表。要创建它，我们需要从 `java.util.AbstractQueue` 开始创建。

**`protected AbstractQueue()`**: 默认构造函数，但由于抽象，不允许创建 `AbstractQueue` 对象。实现应该由它的一个子类提供，如 [`ArrayBlockingQueue`](https://www.geeksforgeeks.org/arrayblockingqueue-class-in-java/#:~:text=ArrayBlockingQueue%20class%20is%20a%20bounded,result%20in%20the%20operation%20blocking.)、[`ConcurrentLinkedQueue`](https://www.geeksforgeeks.org/concurrentlinkedqueue-in-java-with-examples/)、[`DelayQueue`](https://www.geeksforgeeks.org/delayqueue-class-in-java-with-example/#:~:text=DelayQueue%20is%20a%20specialized%20Priority,queue%20whose%20time%20has%20expired.)、[`LinkedBlockingDeque`](https://www.geeksforgeeks.org/linkedblockingdeque-in-java-with-examples/)、[`LinkedBlockingQueue`](https://www.geeksforgeeks.org/linkedblockingqueue-class-in-java/#:~:text=LinkedBlockingQueue%20is%20an%20optionally%2Dbounded,the%20LinkedBlockingQueue%20will%20be%20unbounded.&text=It%20means%20that%20the%20head,elements%20present%20in%20this%20queue.)、[`LinkedTransferQueue`](https://www.geeksforgeeks.org/linkedtransferqueue-in-java-with-examples/#:~:text=The%20LinkedTransferQueue%20class%20in%20Java,functionality%20based%20on%20linked%20nodes.)、[`PriorityBlockingQueue`](https://www.geeksforgeeks.org/priorityblockingqueue-class-in-java/#:~:text=PriorityBlockingQueue%20is%20an%20unbounded%20blocking,resource%20exhaustion%20resulting%20in%20OutOfMemoryError.)、[`PriorityQueue`](https://www.geeksforgeeks.org/priority-queue-class-in-java-2/)、`SynchronousQueue`。

```java
AbstractQueue<E> objName = new ArrayBlockingQueue<E>();
```

下面是一个用 Java 说明抽象队列的示例程序:

## 示例

```java
// Java code to illustrate AbstractQueue
import java.util.*;
import java.util.concurrent.LinkedBlockingQueue;

public class AbstractQueueExample {
    public static void main(String[] argv) throws Exception {
        // Creating object of AbstractQueue<Integer>
        AbstractQueue<Integer> AQ = new LinkedBlockingQueue<Integer>();

        // Adding elements to the Queue
        AQ.add(10);
        AQ.add(20);
        AQ.add(30);
        AQ.add(40);
        AQ.add(50);

        // print the queue contents to the console
        System.out.println("AbstractQueue contains: " + AQ);
    }
}
```

**Output:**

```java
AbstractQueue contains: [10, 20, 30, 40, 50]
```

## 基本操作

### 1. 添加元素

为了将元素添加到抽象队列中，它提供了两种方法。 [`add(E e)`](https://www.geeksforgeeks.org/abstractqueue-add-method-in-java-with-examples/) 方法在不违反容量限制的情况下，将指定的元素插入该队列。成功后返回真，如果当前没有可用空间，则抛出 `IllegalStateException`。 [`addAll(Collection<? extends E> c)`](https://www.geeksforgeeks.org/abstractqueue-addall-method-in-java-with-examples/) 方法将指定集合中的所有元素添加到该队列中。

```java
// Java program to illustrate the
// adding elements to the AbstractQueue
import java.util.*;
import java.util.concurrent.LinkedBlockingQueue;

public class AddingElementsExample {
    public static void main(String[] argv) throws Exception {
        // Since AbstractQueue is an abstract class
        // create object using LinkedBlockingQueue
        AbstractQueue<Integer> AQ1 = new LinkedBlockingQueue<Integer>();

        // Populating AQ
        AQ1.add(10);
        AQ1.add(20);
        AQ1.add(30);
        AQ1.add(40);
        AQ1.add(50);

        // print AQ
        System.out.println("AbstractQueue contains : " + AQ1);

        // Since AbstractQueue is an abstract class
        // create object using LinkedBlockingQueue
        AbstractQueue<Integer> AQ2 = new LinkedBlockingQueue<Integer>();

        // print AQ2 initially
        System.out.println("AbstractQueue2 initially contains : " + AQ2);

        // adds elements of AQ1 in AQ2
        AQ2.addAll(AQ1);

        System.out.println("AbstractQueue1 after addition contains : " + AQ2);
    }
}
```

**Output**

```java
AbstractQueue contains : [10, 20, 30, 40, 50]
AbstractQueue2 initially contains : []
AbstractQueue1 after addition contains : [10, 20, 30, 40, 50]
```

### 2. 移除元素

为了从抽象队列中移除元素，它提供了 `remove()` 和 `clear()` 方法。

*   [`remove()`](https://www.geeksforgeeks.org/abstractqueue-remove-method-in-java-with-examples/) 方法返回并移除该队列的头部。
*   [`clear()`](https://www.geeksforgeeks.org/abstractqueue-remove-method-in-java-with-examples/) 方法从该队列中移除所有元素。该调用返回后，队列将为空。

```java
// Java program to illustrate the
// removal of elements from AbstractQueue
import java.util.*;
import java.util.concurrent.LinkedBlockingQueue;

public class RemovingElementsExample {
    public static void main(String[] argv) throws Exception {
        // Since AbstractQueue is an abstract class
        // create object using LinkedBlockingQueue
        AbstractQueue<Integer> AQ1 = new LinkedBlockingQueue<Integer>();

        // Add elements using add method
        AQ1.add(10);
        AQ1.add(20);
        AQ1.add(30);
        AQ1.add(40);
        AQ1.add(50);

        // print the queue contents to the console
        System.out.println("AbstractQueue1 contains : " + AQ1);

        // Retrieves the head
        int head = AQ1.remove();

        // print the head element to the console
        System.out.println("head : " + head);

        // print the modified queue
        System.out.println("AbstractQueue1 after removal of head : " + AQ1);

        // remove all the elements
        AQ1.clear();

        // print the modified queue
        System.out.println("AbstractQueue1 : " + AQ1);
    }
}
```

**Output**

```java
AbstractQueue1 contains : [10, 20, 30, 40, 50]
head : 10
AbstractQueue1 after removal of head : [20, 30, 40, 50]
AbstractQueue1 : []
```

### 3. 访问元素

抽象队列的 [`element()`](https://www.geeksforgeeks.org/abstractqueue-element-method-in-java-with-examples/) 方法检索但不移除该队列的头。

```java
// Java program to illustrate the
// accessing element from AbstractQueue
import java.util.*;
import java.util.concurrent.LinkedBlockingQueue;

public class AccessingElementExample {
    public static void main(String[] argv) throws Exception {
        // Since AbstractQueue is an abstract class
        // create object using LinkedBlockingQueue
        AbstractQueue<Integer> AQ1 = new LinkedBlockingQueue<Integer>();

        // Populating AQ1 using add method
        AQ1.add(10);
        AQ1.add(20);
        AQ1.add(30);
        AQ1.add(40);
        AQ1.add(50);

        // print AQ to the console
        System.out.println("AbstractQueue1 contains : " + AQ1);

        // access the head element
        System.out.println("head : " + AQ1.element());
    }
}
```

**Output**

```java
AbstractQueue1 contains : [10, 20, 30, 40, 50]
head : 10
```

### 抽象队列的方法

| 方法 | 描述 |
| --- | --- |
| `add(E e)` | 如果可以在不违反容量限制的情况下立即将指定的元素插入到该队列中，成功时返回 `true`，如果当前没有可用空间，则抛出 `IllegalStateException`。 |
| `addAll(Collection<? extends E> c)` | 将指定集合中的所有元素添加到该队列中。 |
| `clear()` | 从此队列中移除所有元素。 |
| `element()` | 检索但不移除该队列的头。 |
| `remove()` | 检索并删除该队列的头。 |

### `java.util.AbstractCollection` 类中声明的方法

| 方法 | 描述 |
| --- | --- |
| `contains(Object o)` | 如果此集合包含指定的元素，则返回 `true`。 |
| `containsAll(Collection<?> c)` | 如果此集合包含指定集合中的所有元素，则返回 `true`。 |
| `isEmpty()` | 如果此集合不包含元素，则返回 `true`。 |
| `iterator()` | 返回此集合中包含的元素的迭代器。 |
| `remove(Object o)` | 从该集合中移除指定元素的单个实例(如果存在)(可选操作)。 |
| `removeAll(Collection<?> c)` | 移除此集合中也包含在指定集合中的所有元素(可选操作)。 |
| `retainAll(Collection<?> c)` | 仅保留此集合中包含在指定集合中的元素(可选操作)。 |
| `toArray()` | 返回包含此集合中所有元素的数组。 |
| `toArray(T[] a)` | 返回包含此集合中所有元素的数组；返回数组的运行时类型是指定数组的运行时类型。 |
| `toString()` | 返回此集合的字符串表示形式。 |

### 接口 `java.util.Collection` 中声明的方法

| 方法 | 描述 |
| --- | --- |
| `contains(Object o)` | 如果此集合包含指定的元素，则返回 `true`。 |
| `containsAll(Collection<?> c)` | 如果此集合包含指定集合中的所有元素，则返回 `true`。 |
| `equals(Object o)` | 将指定的对象与此集合进行比较，看是否相等。 |
| `hashCode()` | 返回此集合的哈希代码值。 |
| `isEmpty()` | 如果此集合不包含元素，则返回 `true`。 |
| `iterator()` | 返回集合中元素的迭代器。 |
| `parallelStream()` | 以此集合为源返回一个可能并行的流。 |
| `remove(Object o)` | 从该集合中移除指定元素的单个实例(如果存在)(可选操作)。 |
| `removeAll(Collection<?> c)` | 移除此集合中也包含在指定集合中的所有元素(可选操作)。 |
| `removeIf(Predicate<? super E> filter)` | 移除此集合中满足给定谓词的所有元素。 |
| `retainAll(Collection<?> c)` | 仅保留此集合中包含在指定集合中的元素(可选操作)。 |
| `size()` | 返回此集合中的元素数量。 |
| `spliterator()` | 在此集合中的元素上创建拆分器。 |
| `stream()` | 返回以此集合为源的顺序流。 |
| `toArray()` | 返回包含此集合中所有元素的数组。 |
| `toArray(IntFunction<T[]> generator)` | 使用提供的生成器函数分配返回的数组，返回包含此集合中所有元素的数组。 |
| `toArray(T[] a)` | 返回包含此集合中所有元素的数组；返回数组的运行时类型是指定数组的运行时类型。 |

### 在接口 `java.lang.Iterable` 中声明的方法

| 方法 | 描述 |
| --- | --- |
| `forEach(Consumer<? super T> action)` | 对 `Iterable` 的每个元素执行给定的操作，直到所有元素都被处理完或者该操作引发异常。 |

### 接口 `java.util.Queue` 中声明的方法

| 方法 | 描述 |
| --- | --- |
| `offer(E e)` | 如果可以在不违反容量限制的情况下立即将指定的元素插入到该队列中。 |
| `peek()` | 检索但不移除该队列的头，如果该队列为空，则返回 `null`。 |
| `poll()` | 检索并删除该队列的头，如果该队列为空，则返回 `null`。 |

**参考:** [https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/util/AbstractQueue.html](https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/util/AbstractQueue.html)