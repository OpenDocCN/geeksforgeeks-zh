# Python 中的 Barrier 对象

> 原文: [https://www.geeksforgeeks.org/barrier-objects-python/](https://www.geeksforgeeks.org/barrier-objects-python/)

Python 中的 `Barrier` 对象用于等待固定数量的线程完成执行，然后任何特定的线程才能继续执行程序。每个线程到达障碍时都会调用 `wait()` 函数。屏障负责跟踪 `wait()` 调用的数量。如果这个数字超过了屏障初始化时使用的线程数，那么屏障会让等待的线程继续执行。在这个执行点的所有线程都被同时释放。

障碍甚至可以用来同步线程之间的访问。但是，通常使用一个屏障来组合线程的输出。一个 `barrier` 对象可以被重复使用多次，重复使用的线程数与其最初初始化的线程数完全相同。

## 初始化屏障

可以使用线程初始化屏障。屏障类如下图所示。括号内的数字表示屏障应该等待的线程数。

**语法:**

```py
barrier = threading.Barrier(number_of_threads, action = None, timeout = None)
```

为线程数创建一个屏障对象。如果提供了操作，则该操作是一个可调用的，当线程被释放时，将由其中一个线程调用。如果没有为 `wait()` 方法指定超时值，则 `timeout` 是默认超时值。

```py
import threading

barrier = threading.Barrier(3)

class thread(threading.Thread):
    def __init__(self, thread_ID):
        threading.Thread.__init__(self)
        self.thread_ID = thread_ID
    def run(self):
        print(str(self.thread_ID) + "\n")
        barrier.wait()

thread1 = thread(100)
thread2 = thread(101)

thread1.start()
thread2.start()
barrier.wait()

print("Exit\n")
```

**输出:**

```py
Exit
```

与线程相关的一些常见函数调用。障碍等级有:

1.  **检查屏障状态:**
    `broken`: 一个布尔值，如果屏障处于断开状态则为 `True`。
    **语法:**

    ```py
    barrier.broken
    ```

2.  **parties**: 通过障碍所需的线程数。
    **语法:**

    ```py
    barrier.parties
    ```

6.  **中止屏障:**
    `abort`: 将屏障置于断开状态。这会导致任何活动或未来的 `wait()` 调用失败并引发 `BrokenBarrierError`。

    屏障上的异常终止函数调用通常需要在程序执行期间跳过死锁条件。
    **语法:**

    ```py
    barrier.abort()
    ```

7.  **重置屏障:**
    `reset`: 将屏障返回到默认的空状态。任何等待它的线程都将收到 `BrokenBarrierError` 异常。

    **语法:**

    ```py
    barrier.reset()
    ```

8.  **wait**: 通过屏障。当所有参与屏障的线程都调用了此函数时，它们将同时被释放。如果提供了超时参数，它将优先于提供给类构造函数的任何超时值。

    返回值是一个 0 到 1 之间的整数，每个线程都不相同。如果调用超时，屏障将进入断开状态。如果在线程等待时屏障被破坏或重置，此方法可能会引发 `BrokenBarrierError` 异常。

    **语法:**

    ```py
    barrier.wait(timeout = None)
    ```

9.  **n_waiting**: 当前在屏障中等待的线程数。
    **语法:**

    ```py
    barrier.n_waiting
    ```

通常，当屏障对象被重置或损坏时，就会引发 `BrokenBarrierError` 异常。

## 示例程序

这里有一个示例程序来显示屏障在 Python 中是如何使用的。

```py
# program to demonstrate
# barriers in python

import threading

barrier = threading.Barrier(3)

class thread(threading.Thread):
    def __init__(self, thread_ID):
        threading.Thread.__init__(self)
        self.thread_ID = thread_ID
    def run(self):
        print(str(self.thread_ID) + "\n")
        print("Parties = " + str(barrier.parties) + "\n")
        print("n_waiting = " + str(barrier.n_waiting) + "\n")
        barrier.wait()

thread1 = thread(100)
thread2 = thread(101)

thread1.start()
thread2.start()

barrier.wait()

print(str(barrier.broken) + "\n")
barrier.reset()
print("n_waiting after reset = " + str(barrier.n_waiting))
barrier.abort()
print("End")
```

**输出:**

```py
Parties = 3
Parties = 3
n_waiting = 1
n_waiting = 1
False
n_waiting after reset = 0
End
```

本文由 [**Mayank Kumar**](https://www.linkedin.com/in/mayank-kumar-a9058b137/) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。