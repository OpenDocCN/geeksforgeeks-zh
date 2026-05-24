# Scala App 特性

## 概述

`App` 是一个[特性](https://www.geeksforgeeks.org/scala-traits/)，用来快速将对象变成可行的程序。这是通过应用 `DelayedInit` 函数来实现的，继承特性 `App` 的对象使用这个函数来执行程序的整个主体，作为继承的主方法的一部分。

**注：**

```scala
trait App extends DelayedInit
```

- 这里的线性超类型是：
```scala
DelayedInit, AnyRef, Any
```
- 值成员有：
```scala
val executionStart: Long
```
```scala
def main(args: Array[String]): Unit
```

## 示例

现在，让我们看一些例子。

### 示例 1

```scala
// Scala program of a trait
// App

// Applying the trait App
object GfG extends App
{
    // Displays output
    println("GeeksforGeeks")
}
```

**输出：**

```scala
GeeksforGeeks
```

这里，对象 `GfG` 继承了 `App` 的主方法并打印输出，所以我们不需要手动创建主方法。

### 示例 2

```scala
// Scala program of trait
// App
object GfG extends App
{
    // conditions stated
    if (args.length == 1)
    {
        // Displays this as output if
        // the command line arguments
        // are equal to one
        println("Student: ${args(0)}")
    }
    else
    {
        // Displays this if no arguments
        // are given in the command line
        println("There are no students.")
    }
}
```

**输出：**

```scala
There are no students.
```

## 命令行参数

注意：这里，`args` 用于命令行参数，它将像数组一样返回即时命令行参数。
这里获得的输出是上面在 `else` 部分陈述的字符串，因为没有提供命令行参数。如果我们提供如下的命令行参数，那么输出将是：

```scala
// command line argument
$ scala GfG Nidhi

// Output
Student: Nidhi
```

这里给出了一个参数，所以只返回那个。