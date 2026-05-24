# Java 中的 `java.util.concurrent.RecursiveTask` 类，带示例

> 原文：[https://www.geeksforgeeks.org/java-util-concurrent-recursivetask-class-in-java-with-examples/](https://www.geeksforgeeks.org/java-util-concurrent-recursivetask-class-in-java-with-examples/)

`RecursiveTask` 是一个抽象类，封装了一个返回结果的任务。它是 `ForkJoinTask` 的一个子类。`RecursiveTask` 类被扩展以创建具有特定返回类型的任务。代表任务计算部分的代码保存在 `RecursiveTask` 的 `compute()` 方法中。

`RecursiveTask` 类多用于并行编程的上下文中。可以划分为独立子任务的任务，任务的最终结果可以从子任务的结果中获得，可以使用 `RecursiveTask` 更有效地实现。例如，在大数组中搜索元素。

## 类层次结构

```java
java.lang.Object
↳ java.util.concurrent.ForkJoinTask
  ↳ java.util.concurrent.RecursiveTask<V>
```

## 构造方法

1.  `RecursiveTask()` – 使用默认设置创建 `RecursiveTask` 对象。

```java
public RecursiveTask()
```

## 方法

1.  `compute()` – 定义任务的方法。

```java
protected abstract void compute()
```

2.  `exec()` – 此方法实现了执行任务所需的基本规则。

```java
protected final boolean exec()
```

3.  `getRawResult()` – 此函数返回任务完成后获得的值，即使任务异常完成。如果任务尚未完成，则返回 `null`。

```java
public final Void getRawResult()
```

4.  `setRawResult()` – 此函数将任务的返回值设置为参数中传递的值。

```java
protected final void setRawResult(Void mustBeNull)
```

## 示例：演示 `RecursiveTask`

```java
import java.util.concurrent.ForkJoinPool;
import java.util.concurrent.RecursiveTask;

public class RecursiveTaskDemo {
    public static void main(String[] args)
    {
        ForkJoinPool fjp = new ForkJoinPool();

        double[] nums = new double[5000];
        for (int i = 0; i < nums.length; i++) {
            nums[i] = (double)(((i % 2) == 0) ? i : -1);
        }
        Sum task = new Sum(nums, 0, nums.length);
        double summation = fjp.invoke(task);
        System.out.println("Summation " + summation);
    }
}

class Sum extends RecursiveTask<Double> {
    final int seqThreshold = 500;
    double[] data;
    int start, end;

    Sum(double[] data, int start, int end)
    {
        this.data = data;
        this.start = start;
        this.end = end;
    }

    @Override
    protected Double compute()
    {
        double sum = 0;
        if ((end - start) < seqThreshold) {
            for (int i = start; i < end; i++)
                sum += data[i];
        }
        else {
            int middle = (start + end) / 2;

            Sum subtaskA = new Sum(data, start, middle);
            Sum subtaskB = new Sum(data, middle, end);

            subtaskA.fork();
            subtaskB.fork();

            sum += subtaskA.join() + subtaskB.join();
        }
        return sum;
    }
}
```

**输出：**

```java
Summation 6245000.0
```

**参考：** [https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/RecursiveTask.html](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/RecursiveTask.html)