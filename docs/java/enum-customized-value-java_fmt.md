# Java 中带有自定义值的枚举

> 原文：[https://www.geeksforgeeks.org/enum-customized-value-java/](https://www.geeksforgeeks.org/enum-customized-value-java/)

## 先决条件
Java 中的[枚举](https://www.geeksforgeeks.org/enum-in-java/)

默认情况下，枚举有自己的字符串值，我们也可以给枚举分配一些自定义值。考虑下面的例子。

## 示例
```java
enum Fruits
{
    APPLE(“RED”), BANANA(“YELLOW”), GRAPES(“GREEN”);
}
```

在上面的例子中，我们可以看到水果枚举有三个成员，即苹果、香蕉和葡萄，它们分别有自己不同的自定义值红色、黄色和绿色。

## 在代码中使用自定义枚举
现在要在代码中使用这个枚举，我们必须遵循以下几点：

1.  我们必须为这个枚举类创建一个带参数的构造函数。为什么？因为我们知道枚举类对象不能显式创建，我们在初始化时使用带参数的构造函数。构造函数不能是 `public` 或 `protected`，它必须具有 `private` 或默认修饰符。为什么？如果我们创建 `public` 或 `protected`，它将允许多个对象被初始化。这完全违反了枚举的概念。
2.  我们必须创建一个 `getter` 方法来获取枚举的值。

```java
// Java program to demonstrate how values can
// be assigned to enums.
enum TrafficSignal
{
    // This will call enum constructor with one
    // String argument
    RED("STOP"), GREEN("GO"), ORANGE("SLOW DOWN");

    // declaring private variable for getting values
    private String action;

    // getter method
    public String getAction()
    {
        return this.action;
    }

    // enum constructor - cannot be public or protected
    private TrafficSignal(String action)
    {
        this.action = action;
    }
}

// Driver code
public class EnumConstructorExample
{
    public static void main(String args[])
    {
        // let's print name of each enum and there action
        // - Enum values() examples
        TrafficSignal[] signals = TrafficSignal.values();

        for (TrafficSignal signal : signals)
        {
            // use getter method to get the value
            System.out.println("name : " + signal.name() +
                        " action: " + signal.getAction() );
        }
    }
}
```

## 输出
```java
name : RED action: STOP
name : GREEN action: GO 
name : ORANGE action: SLOW DOWN
```

本文由 **[维杭沙阿](https://www.linkedin.com/in/vihangshah1/)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。