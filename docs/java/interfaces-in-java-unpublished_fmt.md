# Java 中的接口

> 原文：[https://www.geeksforgeeks.org/interfaces-in-java-unpublished/](https://www.geeksforgeeks.org/interfaces-in-java-unpublished/)

像类一样，Java 中的接口可以有方法和变量，但是接口中声明的方法默认是抽象的（只有方法签名，没有主体）。

- 接口指定类必须做什么，而不是如何做。它是类的蓝图。
- 接口是关于功能的，比如 `Player` 可以是一个接口，任何实现 `Player` 的类都必须能够（或者必须实现）`move()`。所以它指定了类必须实现的一组方法。
- 如果一个类实现了一个接口，并且没有为接口中指定的所有函数提供方法体，那么这个类必须被声明为抽象的。
- 一个 Java 库的例子是 [`Comparator` 接口](https://www.geeksforgeeks.org/comparator-interface-java/)。如果一个类实现了这个接口，那么它可以用来对集合进行排序。

## 语法

```java
interface <interface_name>{

// declare constant fields
    // declare methods that abstract 
    // by default.
}
```

要声明接口，使用 `interface` 关键字。它用于提供全面的抽象。这意味着接口中的所有方法都是用空体声明的，并且是公共的，默认情况下，所有字段都是公共的、静态的和最终的。实现接口的类必须实现接口中声明的所有方法。要实现接口，使用 `implements` 关键字。

## 我们为什么要用接口？

- 它用于实现完全抽象。
- 因为 java 不支持类的多重继承，但是通过使用接口可以实现多重继承。
- 它也用于实现松耦合。
- 接口用于实现抽象。那么问题来了，当我们有抽象类时，为什么还要使用接口？

原因是，抽象类可能包含非最终变量，而接口中的变量是最终的、公共的和静态的。

```java
    // A simple interface
    interface Player
    {
        final int id = 10;
        int move();
    }
```

为了实现一个接口，我们使用关键字：`implements`

```java
// Java program to demonstrate working of 
// interface.
import java.io.*;

// A simple interface
interface in1
{
    // public, static and final
    final int a = 10;

    // public and abstract 
    void display();
}

// A class that implements interface.
class testClass implements in1
{
    // Implementing the capabilities of
    // interface.
    public void display()
    {
        System.out.println("Geek");
    }

    // Driver Code
    public static void main (String[] args)
    {
        testClass t = new testClass();
        t.display();
        System.out.println(a);
    }
}
```

输出：

```java
Geek
```

## 一个真实世界的例子

让我们考虑像自行车、汽车、摩托车这样的交通工具的例子……它们有共同的功能。所以我们做了一个接口，把所有这些共同的功能。让 `Bicycle`，`Bike`，`Car` 等以自己的方式在自己的类中实现所有这些功能。

```java
import java.io.*;

interface Vehicle {

    // all are the abstract methods.
    void changeGear(int a);
    void speedUp(int a);
    void applyBrakes(int a);
}

class Bicycle implements Vehicle{

    int speed;
    int gear;

    // to change gear
    @Override
    public void changeGear(int newGear){

        gear = newGear;
    }

    // to increase speed
    @Override
    public void speedUp(int increment){

        speed = speed + increment;
    }

    // to decrease speed
    @Override
    public void applyBrakes(int decrement){

        speed = speed - decrement;
    }

    public void printStates() {
         System.out.println("speed: " + speed
              + " gear: " + gear);
    }
}

class Bike implements Vehicle {

    int speed;
    int gear;

    // to change gear
    @Override
    public void changeGear(int newGear){

        gear = newGear;
    }

    // to increase speed
    @Override
    public void speedUp(int increment){

        speed = speed + increment;
    }

    // to decrease speed
    @Override
    public void applyBrakes(int decrement){

        speed = speed - decrement;
    }

    public void printStates() {
         System.out.println("speed: " + speed
             + " gear: " + gear);
    }

}

class GFG {

    public static void main (String[] args) {

        // creating an instance of Bicycle 
        // doing some operations 
        Bicycle bicycle = new Bicycle();
        bicycle.changeGear(2);
        bicycle.speedUp(3);
        bicycle.applyBrakes(1);

        System.out.println("Bicycle present state :");
        bicycle.printStates();

        // creating instance of bike.
        Bike bike = new Bike();
        bike.changeGear(1);
        bike.speedUp(4);
        bike.applyBrakes(3);

        System.out.println("Bike present state :");
        bike.printStates();
    }
}
```

输出：

```java
Bicycle present state :
speed: 2 gear: 2
Bike present state :
speed: 1 gear: 1
```

## JDK 8 接口新增功能

1.  在 JDK 8 之前，接口不能定义实现。我们现在可以为接口方法添加默认实现。这个默认实现有特殊用途，不影响接口的意图。

假设我们需要在现有的接口中添加一个新的函数。显然，旧代码将无法工作，因为类没有实现那些新功能。因此，在默认实现的帮助下，我们将为新添加的函数提供一个默认主体。那么旧的代码仍然有效。

```java
    // An example to show that interfaces can
    // have methods from JDK 1.8 onwards
    interface in1
    {
        final int a = 10;
        default void display()
        {
            System.out.println("hello");
        }
    }

    // A class that implements interface.
    class testClass implements in1
    {
        // Driver Code
        public static void main (String[] args)
        {
            testClass t = new testClass();
            t.display();
        }
    }
```

输出：

```java
    hello
```

2.  JDK 8 中添加的另一个特性是，我们现在可以在接口中定义静态方法，这些方法可以独立调用而不需要对象。注意：这些方法不会被继承。

```java
    // An example to show that interfaces can
    // have methods from JDK 1.8 onwards
    interface in1
    {
        final int a = 10;
        static void display()
        {
            System.out.println("hello");
        }
    }

    // A class that implements interface.
    class testClass implements in1
    {
        // Driver Code
        public static void main (String[] args)
        {
            in1.display();
        }
    }
```

输出：

```java
    hello
```

## 关于接口或文章摘要的要点

- 我们不能创建接口的实例（接口不能被实例化），但是我们可以引用它来引用它的实现类的对象。
- 一个类可以实现多个接口。
- 一个接口可以扩展另一个接口（但只能扩展一个接口）。
- 实现接口的类必须实现接口中的所有方法。
- 所有的方法都是公开的、抽象的。所有字段都是公共的、静态的和最终的。
- 用于实现多重继承。
- 用于实现松耦合。

## 相关文章

- [接口中方法的访问说明符](https://www.geeksforgeeks.org/g-fact-73/)
- [Java 中类或接口的访问说明符](https://www.geeksforgeeks.org/g-fact-81/)
- [Java 中的抽象类](https://www.geeksforgeeks.org/abstract-classes-in-java/)
- [Java 中的比较器接口](https://www.geeksforgeeks.org/comparator-interface-java/)
- [Java 接口方法](https://www.geeksforgeeks.org/g-fact-47-java-interface-methods/)
- [Java 中的嵌套接口](https://www.geeksforgeeks.org/interface-nested-class-another-interface/)

本文由 **Mahak Kumar** 和 **Nitsdheerendra** 供稿。如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论。