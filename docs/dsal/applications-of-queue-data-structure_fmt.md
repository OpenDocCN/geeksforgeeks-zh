# 队列数据结构的应用

> 原文：[https://www.geeksforgeeks.org/applications-of-queue-data-structure/](https://www.geeksforgeeks.org/applications-of-queue-data-structure/)

[队列](http://en.wikipedia.org/wiki/Queue_%28data_structure%29)用于当事情不必立即处理，而是必须在 **F**irst **I**n **F**irst **O**ut（FIFO）的顺序处理时，例如[广度优先搜索](http://en.wikipedia.org/wiki/Breadth-first_search)。队列的这个属性使得它在以下场景中也很有用。

1.  当一个资源在多个消费者之间共享时。例如[中央处理器调度](https://www.geeksforgeeks.org/cpu-scheduling-in-operating-systems/)、[磁盘调度](https://www.geeksforgeeks.org/disk-scheduling-algorithms/)。
2.  当数据在两个进程之间异步传输时（数据接收的速率不一定与发送的速率相同）。例子包括输入输出缓冲区、管道、文件输入输出等。
3.  在操作系统中：
    *   [信号量](https://en.wikipedia.org/wiki/Semaphore_(programming)#:~:text=In%20computer%20science%2C%20a%20semaphore,as%20a%20multitasking%20operating%20system.)
    *   `FCFS`（先到先得）调度，例如：`FIFO`队列
    *   在打印机中假脱机
    *   为键盘
4.  在网络中：
    *   （此处原文内容不完整）

有关队列和堆栈的更多详细应用，请参见本[资料](http://introcs.cs.princeton.edu/43stack/)。

**参考文献：**
[http://introcs.cs.princeton.edu/43stack/](http://introcs.cs.princeton.edu/43stack/)