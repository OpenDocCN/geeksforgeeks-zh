# Java中的委托与继承

> 原文: [https://www.geeksforgeeks.org/delegation-vs-inheritance-java/](https://www.geeksforgeeks.org/delegation-vs-inheritance-java/)

## 继承

在Java中，[继承](https://www.geeksforgeeks.org/inheritance-in-java/)是一个类获取另一个类属性的过程。也就是说，称为派生类或子类的新类接管了称为基类、超类或父类的现有类的属性和行为。

## 委托

**委托**意味着简单地将责任转移给他人/其他事物。

*   委托可以替代继承。
*   委托意味着使用另一个类的对象作为实例变量，并将消息转发给该实例。
*   在许多情况下，它比继承更好，因为它允许你考虑转发的每一条消息，因为实例属于已知类，而不是新类，并且因为它不会强迫你接受超类的所有方法：你只提供真正有意义的方法。
*   委托可以被视为对象之间的一种关系，其中一个对象将一些方法调用转发给另一个对象，后者被称为其委托。
*   委托的主要优势是运行时的灵活性——委托可以在运行时轻松更改。但与继承不同，大多数流行的面向对象语言并不直接支持委托，并且它对于[动态多态](https://www.geeksforgeeks.org/dynamic-method-dispatch-runtime-polymorphism-java/)来说并不方便。

```java
// Java program to illustrate
// delegation
class RealPrinter {
    // the "delegate"
    void print()
    {
        System.out.println("The Delegate");
    }
}

class Printer {
    // the "delegator"
    RealPrinter p = new RealPrinter(); // create the delegate

    void print()
    {
        p.print(); // delegation
    }
}

public class Tester {
    // To the outside world it looks like Printer actually prints.
    public static void main(String[] args)
    {
        Printer printer = new Printer();
        printer.print();
    }
}
```

输出：

```java
The Delegate
```

当你委托时，你只是调用一个知道该做什么的类。你并不真正关心它是如何完成的，你关心的是你调用的类知道需要做什么。

## 使用相同的继承代码

```java
// Java program to illustrate
// Inheritance
class RealPrinter {
    // base class implements method
    void print()
    {
        System.out.println("Printing Data");
    }
}

// Printer Inheriting functionality of real printer
class Printer extends RealPrinter {
    void print()
    {
        super.print(); // inside calling method of parent
    }
}

public class Tester {
    // To the outside world it looks like Printer actually prints.
    public static void main(String[] args)
    {
        Printer printer = new Printer();
        printer.print();
    }
}
```

输出：

```java
Printing Data
```

## 何时以及使用什么？

以下是一些使用继承或委托的例子：
假设你的类被称为B，而类的派生/委托被称为A，那么：

*   如果你想表达“是一个”的关系，那么你想使用继承。
*   如果你想能够将你的类传递给一个期望A的现有API，那么你需要使用继承。
*   你想增强A，但A是`final`的，不能进一步细分，所以你需要使用[组合](https://www.geeksforgeeks.org/association-composition-aggregation-java/)和委托。

本文由 **Abu Shek Gupta** 投稿。如果你喜欢GeeksforGeeks并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 撰写文章或将你的文章邮寄至 contribute@geeksforgeeks.org。让你的文章出现在Geek博客的主页上，以帮助其他Geek。

如果你发现任何错误，或者你想分享更多关于上述讨论主题的信息，请写评论。