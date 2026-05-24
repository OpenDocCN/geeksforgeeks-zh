# Java 中的 `Random` 类

> 原文: [https://www.geeksforgeeks.org/java-util-random-class-java/](https://www.geeksforgeeks.org/java-util-random-class-java/)

在 Java 中，`Random` 类用于生成伪随机数。这个类的一个实例是线程安全的。然而，这个类的实例在加密上是不安全的。此类提供各种方法调用来生成不同的随机数据类型，如 `float`、`double`、`int`。

## 构造函数

*   `Random()`: 创建一个新的随机数生成器。
*   `Random(long seed)`: 使用单个 `long` 种子创建一个新的随机数生成器。

## 声明

```java
public class Random
               extends Object
               implements Serializable
```

## 方法

### 1. `doubles()`
返回一个实际上无限的伪随机 `double` 值流，每个值介于零（包含）和一（排除）之间。

**语法:**
```java
public DoubleStream doubles()
```
**返回:**
一个伪随机 `double` 值的流。

### 2. `ints()`
返回一个实际上无限的伪随机 `int` 值流。

**语法:**
```java
public IntStream ints()
```
**返回:**
一个伪随机 `int` 值的流。

### 3. `longs()`
返回一个实际上无限的伪随机 `long` 值流。

**语法:**
```java
public LongStream longs()
```
**返回:**
一个伪随机 `long` 值的流。

### 4. `next(int bits)`
生成下一个伪随机数。

**语法:**
```java
protected int next(int bits)
```
**参数:**
`bits` - 随机位。
**返回:**
来自此随机数生成器序列的下一个伪随机值。

### 5. `nextBoolean()`
从这个随机数生成器的序列中返回下一个伪随机的、均匀分布的 `boolean` 值。

**语法:**
```java
public boolean nextBoolean()
```
**返回:**
来自此随机数生成器序列的下一个伪随机、均匀分布的 `boolean` 值。

### 6. `nextBytes(byte[] bytes)`
生成随机字节并将其放入用户提供的字节数组中。

**语法:**
```java
public void nextBytes(byte[] bytes)
```
**参数:**
`bytes` - 要用随机字节填充的字节数组。
**抛出:**
`NullPointerException` - 如果字节数组为 `null`。

### 7. `nextDouble()`
从这个随机数生成器的序列中返回下一个 0.0 到 1.0 之间的伪随机、均匀分布的 `double` 值。

**语法:**
```java
public double nextDouble()
```
**返回:**
来自此随机数生成器序列的下一个伪随机、均匀分布在 0.0 和 1.0 之间的 `double` 值。

### 8. `nextFloat()`
从这个随机数生成器的序列中返回下一个 0.0 到 1.0 之间的伪随机、均匀分布的 `float` 值。

**语法:**
```java
public float nextFloat()
```
**返回:**
来自此随机数生成器序列的下一个伪随机、均匀分布在 0.0 和 1.0 之间的 `float` 值。

### 9. `nextGaussian()`
返回下一个伪随机、高斯（“正态”）分布的 `double` 值，其平均值为 0.0，标准偏差为 1.0，来自此随机数生成器的序列。

**语法:**
```java
public double nextGaussian()
```
**返回:**
来自此随机数生成器序列的下一个伪随机、高斯（“正态”）分布的 `double` 值，平均值为 0.0，标准差为 1.0。

### 10. `nextInt()`
从这个随机数生成器的序列中返回下一个伪随机的、均匀分布的 `int` 值。

**语法:**
```java
public int nextInt()
```
**返回:**
来自此随机数生成器序列的下一个伪随机、均匀分布的 `int` 值。

### 11. `nextInt(int bound)`
返回一个伪随机的、均匀分布的 `int` 值，介于 0（包括 0）和指定值（不包括）之间，从这个随机数生成器的序列中提取。

**语法:**
```java
public int nextInt(int bound)
```
**参数:**
`bound` - 上界（不包括）。必须是正数。
**返回:**
来自此随机数生成器序列的下一个伪随机、均匀分布在零（包含）和 `bound`（不包括）之间的 `int` 值。
**抛出:**
`IllegalArgumentException` - 如果 `bound` 不是正数。

### 12. `nextLong()`
从这个随机数生成器的序列中返回下一个伪随机的、均匀分布的 `long` 值。

**语法:**
```java
public long nextLong()
```
**返回:**
来自此随机数生成器序列的下一个伪随机、均匀分布的 `long` 值。

### 13. `setSeed(long seed)`
使用单个 `long` 种子设置该随机数生成器的种子。

**语法:**
```java
public void setSeed(long seed)
```
**参数:**
`seed` - 初始种子。

## 从 `java.lang.Object` 类继承的方法

*   `clone()`
*   `equals()`
*   `finalize()`
*   `getClass()`
*   `hashCode()`
*   `notify()`
*   `notifyAll()`
*   `toString()`
*   `wait()`

## 演示 `Random` 类用法的 Java 程序

```java
// Java program to demonstrate
// method calls of Random class
import java.util.Random;

public class Test
{
    public static void main(String[] args)
    {
        Random random = new Random();
        System.out.println(random.nextInt(10));
        System.out.println(random.nextBoolean());
        System.out.println(random.nextDouble());
        System.out.println(random.nextFloat());
        System.out.println(random.nextGaussian());
        byte[] bytes = new byte[10];
        random.nextBytes(bytes);
        System.out.printf("[");
        for(int i = 0; i< bytes.length; i++)
        {
            System.out.printf("%d ", bytes[i]);
        }
        System.out.printf("]\n");

        System.out.println(random.nextLong());
        System.out.println(random.nextInt());

        long seed = 95;
        random.setSeed(seed);

        // Note: Running any of the code lines below
        // will keep the program running as each of the
        // methods below produce an unlimited random
        // values of the corresponding type

        /* System.out.println("Sum of all the elements in the IntStream returned = " +
                random.ints().count());
        System.out.println("Count of all the elements in the DoubleStream returned = " +
                random.doubles().count());
        System.out.println("Count of all the elements in the LongStream returned = " +
                random.longs().count());
        */
    }
}
```

**输出:**

```
true
0.19674934340402916
0.7372021
1.4877581394085997
[-44 75 68 89 81 -72 -1 -66 -64 117 ]
```

**参考:**

*   Oracle

本文由 **Mayank Kumar** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。