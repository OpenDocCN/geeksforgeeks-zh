# 编译器设计中的循环优化

> 原文: [https://www.geeksforgeeks.org/loop-optimization-in-compiler-design/](https://www.geeksforgeeks.org/loop-optimization-in-compiler-design/)

**循环优化**是提高执行速度和减少与循环相关的开销的过程。它在提高缓存性能和有效利用并行处理能力方面发挥着重要作用。科学程序的大部分执行时间都花在循环上。

> 循环优化是独立于机器的优化。

减少内部循环中的指令数量可以提高程序的运行时间，即使该循环之外的代码量增加了。

## 循环优化技术

### 1. 频率降低（代码移动）

在频率降低中，循环内的代码量被减少。可以将语句或表达式移动到循环体外而不影响程序语义的，就会被移出循环。

**示例:**

```
初始代码：

while(i<100)
{
    a = Sin(x)/Cos(x) + i;
    i++;
}

优化后代码：

t = Sin(x)/Cos(x);
while(i<100)
{
    a = t + i;
    i++;
}
```

### 2. 循环展开

循环展开是一种循环转换技术，有助于优化程序的执行时间。我们基本上是移除或减少迭代次数。循环展开通过消除循环控制指令和循环测试指令来提高程序速度。

**示例:**

```
初始代码：

for (int i=0; i<5; i++)
    printf("Pankaj\n");

优化后代码：

printf("Pankaj\n");
printf("Pankaj\n");
printf("Pankaj\n");
printf("Pankaj\n");
printf("Pankaj\n");
```

### 3. 循环合并

循环合并是将两个或多个循环组合成一个循环。它减少了编译多个循环所需的时间。

**示例:**

```
初始代码：

for(int i=0; i<5; i++)
    a = i + 5;
for(int i=0; i<5; i++)
    b = i + 10;

优化后代码：

for(int i=0; i<5; i++)
{
    a = i + 5;
    b = i + 10;
}
```