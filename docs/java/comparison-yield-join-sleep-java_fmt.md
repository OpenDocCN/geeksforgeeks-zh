# Java 中 `yield()`、`join()` 和 `sleep()` 的比较

> 原文：[https://www.geeksforgeeks.org/comparison-yield-join-sleep-java/](https://www.geeksforgeeks.org/comparison-yield-join-sleep-java/)

## 比较表

| 属性 | `yield()` | `join()` | `sleep()` |
| :--- | :--- | :--- | :--- |
| **目的** | 如果一个线程想要给其他具有相同优先级的线程一个执行机会，那么我们应该选择 `yield()`。 | 如果一个线程想要等待直到其他线程完成，那么我们应该选择 `join()`。 | 如果一个线程不希望在指定时间内执行，那么我们应该选择 `sleep()`。 |
| **是否为 final 方法？** | 否 | 是 | 否 |
| **是否抛出异常？** | 否 | 是 (`InterruptedException`) | 是 (`InterruptedException`) |
| **是否为本地方法？** | 是 | 否 | `sleep(long ms)` -> 是；`sleep(long ms, int ns)` -> 否 |
| **是否响应中断？** | 否 | 是 | 是 |