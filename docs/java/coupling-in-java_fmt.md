# Java 中的耦合

> 原文: [https://www.geeksforgeeks.org/coupling-in-java/](https://www.geeksforgeeks.org/coupling-in-java/)

在面向对象设计中，耦合指的是一个元素对另一个元素的直接了解程度。换句话说，A 类力的变化与 b 类力的变化有多频繁。

## 耦合有两种类型:

### 1. 紧耦合

紧耦合意味着两个类经常一起变化。换句话说，如果 A 类对 B 类的实现方式了解得过多，那么 A 和 B 就是紧耦合的。

**示例：** 如果你想更换皮肤，你也必须改变身体的设计，因为两者是连接在一起的——它们是紧耦合的。紧耦合最好的例子是 RMI（远程方法调用）。

```java
// Java program to illustrate
// tight coupling concept
class Subject {
    Topic t = new Topic();
    public void startReading()
    {
        t.understand();
    }
}
class Topic {
    public void understand()
    {
        System.out.println("Tight coupling concept");
    }
}
```

**说明：** 在上面的程序中，`Subject` 类依赖于 `Topic` 类。`Subject` 类与 `Topic` 类紧密耦合，这意味着如果 `Topic` 类中的任何变化都需要 `Subject` 类的变化。例如，如果 `Topic` 类的 `understand()` 方法更改为 `gotit()` 方法，那么你必须更改 `startReading()` 方法，将调用 `gotit()` 方法，而不是调用 `understand()` 方法。

```java
// Java program to illustrate
// tight coupling concept
class Volume 
{
     public static void main(String args[]) 
     {
         Box b = new Box(5,5,5);
         System.out.println(b.volume);
     }
}
class Box 
{
     public int volume;
     Box(int length, int width, int height) 
     {
         this.volume = length * width * height;
     }
}
```

**说明：** 在上面的例子中，两个类之间有很强的相互依赖性。如果 `Box` 类有任何变化，则反映在 `Volume` 类的结果中。

### 2. 松耦合

简单来说，松耦合意味着它们大多是独立的。如果 A 类对 B 类的唯一了解是通过 B 类的接口暴露的内容，那么 A 类和 B 类被称为松耦合。为了克服对象间紧耦合的问题，Spring 框架使用依赖注入机制，借助 POJO/POJI 模型，通过依赖注入可以实现松耦合。

**示例：** 如果你更换衬衫，你不会被迫更换身体——当你能做到这一点时，你就拥有了松耦合。当你不能这样做时，你就拥有了紧耦合。松耦合的例子有接口、JMS。

```java
// Java program to illustrate 
// loose coupling concept
public interface Topic
{
    void understand();
}
class Topic1 implements Topic {
    public void understand()
    {
        System.out.println("Got it");
    }
}
class Topic2 implements Topic {
    public void understand()
    {
        System.out.println("understand");
    }
}
public class Subject {
    public static void main(String[] args)
    {
        Topic t = new Topic1();
        t.understand();
    }
}
```

**说明：** 在上例中，`Topic1` 和 `Topic2` 对象是松散耦合的。这意味着 `Topic` 是一个接口，我们可以在运行时注入任何实现的类，并且我们可以向最终用户提供服务。

```java
// Java program to illustrate
// loose coupling concept
class Volume 
{
     public static void main(String args[]) 
     {
         Box b = new Box(5,5,5);
         System.out.println(b.getVolume());
     }
}
final class Box 
{
     private int volume;
     Box(int length, int width, int height) 
     {
         this.volume = length * width * height;
     }
     public int getVolume() 
     { 
         return volume;
     }
}
```

**说明：** 在上面的程序中，两个类之间没有依赖关系。如果我们改变 `Box` 类中的任何东西，那么我们就不必改变 `Volume` 类中的任何东西。

## 紧耦合和松耦合哪个更好？

总的来说，紧密耦合在大多数情况下是不好的，因为它降低了代码的灵活性和可重用性，使更改变得更加困难，阻碍了测试能力等。松耦合是更好的选择，因为当您的应用程序需要更改或增长时，松耦合会帮助您。如果您使用松散耦合的体系结构进行设计，那么当需求发生变化时，应用程序中只有少数部分会受到影响。

**我们来看看紧耦合和松耦合的示意图:**
![Coupling in Java](img/63b8a141c236bed510420094d65acba2.png)

## 紧耦合和松耦合的区别

*   紧耦合不擅长测试能力。但是松耦合提高了测试能力。
*   紧密耦合不提供接口的概念。但是松散耦合帮助我们遵循编程到接口的 GOF 原理，而不是实现。
*   在紧耦合中，在两个类之间交换代码并不容易。但是在松散耦合中交换其他代码/模块/对象/组件要容易得多。
*   紧耦合不具备变化能力。但是松耦合是高度可变的。

本文由 **比沙尔·库马尔·杜贝** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。