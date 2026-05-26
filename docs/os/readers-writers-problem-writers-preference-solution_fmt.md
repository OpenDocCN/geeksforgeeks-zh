# 读者-作者问题：作者偏好解决方案

> 原文：[https://www.geeksforgeeks.org/readers-writers-problem-writers-preference-solution/](https://www.geeksforgeeks.org/readers-writers-problem-writers-preference-solution/)

## 先决条件
- [读者-作者问题 | 集合 1（介绍和读者偏好解决方案）](https://www.geeksforgeeks.org/readers-writers-problem-set-1-introduction-and-readers-preference-solution/)
- [进程同步中的信号量](https://www.geeksforgeeks.org/semaphores-in-process-synchronization/)

在进程同步中，有一个非常经典的同步问题，叫做读者-作者问题。这个问题有几个子问题或变体，都涉及优先级，其中一个在上面的文章中讨论过。第二个变化叫做**作者优先读者-作者问题**。

用于解决该问题的变量有：
1.  `readers`，记录一次有多少读者。
2.  `mutex`，保护共享变量。
3.  `idle`，用于表示临界区的线程数（读或写）。如果它们不是线程，那么应该是 1，否则是 0。

```
int readers = 0                //Keeps the count of readers
idle = Semaphore (1)           // 1 if no threads are present, else 0
mutex = Semaphore (1)          //Mutex protects the shared counter
```

对于信号量变量，`wait()` 表示“等到条件为真”，`signal()` 表示“条件为真的信号”。

```
readSwitch = Lightswitch ()
writeSwitch = Lightswitch ()
noReaders = Semaphore (1)
noWriters = Semaphore (1)
```

首先，我们来探讨一下**读者优先于作者**的场景。

## 问题陈述（读者优先）
说明一旦*读者*准备好了，那么读者就可以阅读文件。换句话说，如果读者可以访问该对象，任何读者都不应该等待，而*作者*要等到读者完成它。

### 读者优先于写入器时的解决方案

#### 作者解决方案
- 作者请求进入关键部分
- 如果允许的话，它保存 `noReaders`，并写入。否则它在队列中等待，直到 `wait()` 为真
- 它离开了临界区

这里是*作者*的代码：

```
idle.wait()               //Waits till the critical section is empty.
     //Critical Section for the Writer
idle.signal()            //Signals that the critical section is empty.
```

这里，当*写入器*处于临界区时，临界区中不存在其他线程（即读取器或写入器）。首先，*阅读器*检查临界区是否为空。如果是空的，它会继续前进并阻止*作者*进入。

#### 读者解决方案
- 读者要求进入关键部分。
- 如果允许，那么它持有 `noWriters`，因为它持有互斥体，任何后续的读者都在 `mutex` 上排队。后续读者仍可进入
- 读者退出关键部分。

以下是*阅读器代码*：

```
readSwitch.lock(noWriters)            //Locks the writer
    noReaders.wait()        signaling  // Waits till the  reader exits the critical section
           //critical section for readers
    noReaders.signal()        //Signals that reader has exited from the Critical section
readSwitch.unlock(noWriters)           // Unlocks the reader.
```

## 问题陈述（作者优先）
要求一旦*作者*准备好了，*作者*尽快进行写作。换句话说，如果一个*作者*正在等待访问该对象，则没有新的*读者*可以开始阅读。

### 当写入方优先于读取方时的解决方案

#### 读者解决方案
- *阅读器*请求进入临界区
- 如果允许的话，
    1.  它持有 `noWriters`，但不持有 `noReaders`。因此，如果一个作者到达，它可以锁定 `noReaders`，这将导致后续读者排队。
    2.  一旦最后一个*阅读器*退出，它会向 `noWriters` 发出信号，这将允许队列中的 *writers* 继续进行。

这里是*阅读器*代码：

```
noReaders.wait()
    readSwitch.lock(noWriters)   // Locks the writers when readers enter the critical section
noReaders.signal()                    //Signals that reader is in critical section
    //critical section for readers
readSwitch.unlock(noWriters)   //Once the reader exits the critical section, then the writer is unlocked.
```

#### 作者解决方案
- *写入器*请求进入临界区。
- 如果允许，那么
    1.  它既容纳了 `noReaders` 也容纳了 `noWriters`。这确保了没有*读者*和没有*作者*在临界区。
    2.  如果读者在关键部分，它持有 `noWriters`，但不持有 `noReaders`。因此，如果一个作者到达，它可以锁定 `noReaders`，这将导致后续读者排队。
    3.  此外，`writeSwitch` 允许多个*作者*在 `noWriters` 上排队，同时锁定 `noReaders`。因此，许多*编写者*甚至没有给 `noWriters` 发信号就通过了临界区。
- 一旦最后一个*作家*离开了临界区，那么只有*读者*才能进入临界区

这里是*作者*的代码：

```
writeSwitch.lock(noReaders)            //Locks the reader
    noWriters.wait()                        // Waits till the writer is complete.
        //critical section for writers
    noWriters.signal()                    //Signals that writer has exited from the Critical section
writeSwitch.unlock(noReaders)         // Unlocks the reader.
```

但是这种实现有一个缺点，即读者可能会挨饿或面临长时间的延迟。为了避免饥饿，使用了监视器。