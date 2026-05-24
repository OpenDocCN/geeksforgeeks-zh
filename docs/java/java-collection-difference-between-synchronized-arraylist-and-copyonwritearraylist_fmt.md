# Java 集合：同步数组列表和 CopyOnWriteArrayList 的区别

> 原文：`https://www.geeksforgeeks.org/java-collection-difference-between-synchronized-arraylist-and-copyonwritearraylist/`

由于`ArrayList`不同步，如果多个线程试图同时修改一个数组列表，那么最终的结果将是不确定的。因此，为了在多线程环境中实现线程安全，必须同步数组列表。

数组列表的同步可以通过两种方式完成：
1.  使用`Collections.synchronizedList()`
2.  使用`CopyOnWriteArrayList(COWAL)`。

由于两者都用于实现`ArrayList`中的线程安全，因此出现了一个问题，即何时使用`COWAL`以及何时使用`Collections.synchronizedList()`。这可以通过理解它们之间的差异来理解。同步数组列表和`CopyOnWriteArrayList`之间的主要区别来自于它们的性能、可伸缩性以及它们如何实现线程安全。

## 为什么当 `Collections.synchronizedList()` 已经存在时，`CopyOnWriteArrayList` 才出现

最初，`SynchronizedList`用于多线程环境，但它有一些限制。它的所有读写方法都是在列表对象本身上同步的，也就是说，如果一个线程正在执行`add()`方法，它会阻止其他想要让迭代器访问列表中元素的线程。此外，一次只允许一个线程迭代列表元素，这是低效的。那是相当僵硬的。

因此，需要一个更灵活的集合，它允许：
1.  多个线程同时执行读操作。
2.  一个线程并发执行读操作，另一个线程并发执行写操作。
3.  只允许一个线程写入，其他线程可以同时读取。

为了克服这些问题，最终在`Java 5`中，引入了一组名为**并发集合**的新集合类，其中包含`CopyOnWriteArrayList`。`CopyOnWriteArrayList`类旨在启用这种顺序写入和并发读取功能。

## 它们之间的主要区别是：

### 1. 线程锁定
`Synchronized List`锁定整个列表以在读或写操作期间提供同步和线程安全，而`CopyOnWriteArrayList`在这些操作期间不会锁定整个列表。

`CopyOnWriteArrayList`类根据其名称工作，即*写时复制*，它对读写操作执行不同的操作。对于每个写操作（添加、设置、删除等），它都会生成列表中元素的新副本。对于读取操作（`get`、迭代器、`listIterator`等），它在不同的副本上工作。因此在读操作期间没有额外的开销，并且它的读操作比`Collections.synchronizedList()`更快。因此，`COWAL`比同步列表更适合读取操作。

### 2. 写操作
对于数组列表中的写操作，`COWAL`写操作比`Collections.synchronizedList()`慢，因为它使用`ReentrantLock`。写方法将始终创建现有数组的副本，修改副本，最后更新数组的易失性引用以指向这个新数组。因此，它在写操作期间有很多开销。这就是为什么`CopyOnWriteArrayList`的写操作比`Collections.synchronizedList()`慢。

### 3. 修改时的行为
`Synchronized list`是**快速失败迭代器**，也就是说，当一个线程在迭代列表时修改它，它将抛出`ConcurrentModificationException`。而`CopyOnWriteArrayList`是**故障安全迭代器**，也就是说，当一个线程在迭代列表时修改它，它不会抛出`ConcurrentModificationException`。

### 4. 工作线程数量
通过锁定完整的列表对象会影响其性能，只允许一个线程在同步列表上操作，因为其他线程都在等待，而在`COWAL`的情况下，允许多个线程在数组列表上操作，因为它工作在单独的克隆副本上，该副本用于更新/修改操作，以使其性能更快。

### 5. 在块内迭代
当迭代同步列表时，确保它在同步块内部迭代，而在`CopyOnWriteArrayList`中，我们可以在同步块外部安全地迭代。

## 何时使用 `SynchronizedList`？

1.  因为在`CopyOnWriteArrayList`中，每次更新/修改操作都会创建一个新的独立克隆副本，并且在JVM上有内存分配开销以及将克隆副本与原始副本合并的开销。因此，在这种情况下，同步列表是更好的选择。
2.  当`ArrayList`很大时。

## 何时使用 `CopyOnWriteArrayList`？

## 同步列表 vs CopyOnWriteArrayList

| 同步列表 | CopyOnWriteArrayList |
| :--- | :--- |
| 它在读或写操作期间锁定整个列表，以确保线程安全。 | 只在写操作时锁定列表，所以在读操作时不锁定。因此，多个线程同时执行读取操作。 |
| 它是一个快速失败迭代器。 | 它是一个故障安全迭代器。 |
| 它是在`Java 1.2`版本中引入的。 | 是在`Java 5`版本中引入的。 |
| 列表的迭代应该在同步块内部，否则会面临不确定行为。 | 它可以安全地在同步块外迭代。 |
| 当一个线程遍历列表时，如果有其他线程试图修改列表，它将抛出`ConcurrentModificationException`。 | 遍历时不允许修改列表。如果列表在遍历过程中被其他线程修改，则不会引发`ConcurrentModificationException`。 |
| 最好在数组列表较大且列表中的写操作大于读操作时使用。 | 最好在`ArrayList`小或者读操作大于写操作时使用。 |

1.  `CopyOnWriteArrayList`提供无锁读取，这意味着如果有更多的读线程，并且写入发生得相当慢，性能会好得多。
2.  当数组列表的大小很小时。