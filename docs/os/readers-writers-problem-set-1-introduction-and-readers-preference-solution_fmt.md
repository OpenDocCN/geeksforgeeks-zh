# 读者-作者问题 | 第 1 集（介绍和读者偏好解决方案）

> 原文：[https://www.geeksforgeeks.org/readers-writers-problem-set-1-introduction-and-readers-preference-solution/](https://www.geeksforgeeks.org/readers-writers-problem-set-1-introduction-and-readers-preference-solution/)

考虑一种情况，我们有一个文件在许多人之间共享。

*   如果其中一人尝试编辑文件，则其他人不应同时读取或写入，否则他/她将看不到更改。
*   然而，如果有人正在读取文件，其他人可以同时读取。

准确地说，在操作系统中，我们称这种情况为**读者-作者问题**。

问题参数：

*   一组数据由多个进程共享。
*   一旦写入者准备好，它就会写入。一次只能有一个写入者写入。
*   如果一个进程正在写入，其他进程不能读取。
*   如果至少有一个读者正在读取，其他进程不能写入。
*   读者不能写入，只能读取。

## 当读者优先于作者时的解决方案

这里的优先级是指，如果共享当前已打开进行读取，则不应有任何读取器等待。

使用三个变量：`mutex`、`wrt`、`readcnt` 实现解。

1.  `mutex` 是互斥量，`wrt` 是信号量。信号量 `mutex` 用于确保在更新 `readcnt` 时互斥，即当任何读者进入或退出临界区时。信号量 `wrt` 被读者和写者共同使用。
2.  `int readcnt`。`readcnt` 表示在临界区内执行读取的进程数量，初始为 0。

信号量的功能：

*   `wait()`：递减信号量值。
*   `signal()`：递增信号量值。

### 写者流程

1.  写者请求进入临界区。
2.  如果允许，即 `wait()` 返回 true，则进入并写入。否则，它将继续等待。
3.  退出临界区。

```
do {
    // writer requests for critical section
    wait(wrt);

    // performs the write

    // leaves the critical section
    signal(wrt);

} while(true);
```

### 读者流程

1.  读者请求进入临界区。
2.  如果允许：
    *   它将增加临界区中的读者数量。如果该读者是第一个进入的读者，它将锁定 `wrt` 信号量以限制写者的进入（如果临界区内有任何读者）。
    *   然后，当其他读者已经在读取时，它发出互斥信号允许任何其他读者进入。
    *   读取后，退出临界区。退出时，它检查是否没有更多读者在内，然后它发出信号量 `wrt`，这样写者就可以进入临界区了。
3.  如果不允许，则继续等待。

```
do {

    // Reader wants to enter the critical section
    wait(mutex);

    // The number of readers has now increased by 1
    readcnt++;

    // there is atleast one reader in the critical section
    // this ensure no writer can enter if there is even one reader
    // thus we give preference to readers here
    if (readcnt == 1)
        wait(wrt);

    // other readers can enter while this current reader is inside
    // the critical section
    signal(mutex);

    // current reader performs reading here

    // a reader wants to leave
    wait(mutex);

    readcnt--;

    // that is, no reader is left in the critical section,
    if (readcnt == 0)
        signal(wrt);        // writers can enter

    signal(mutex); // reader leaves

} while(true);
```

因此，信号量 `wrt` 在读取器和写入器上排队，使得如果写入器也在等待，则优先考虑读取器。因此，没有读者仅仅因为作者请求进入关键部分而等待。

[Ekta Goel](https://www.linkedin.com/pub/ekta-goel/75/12a/3a6) 投稿文章。如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论。