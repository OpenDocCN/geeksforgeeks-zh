# Scala 单例对象和伴随对象

> 原文:[https://www . geesforgeks . org/Scala-singleton-and-companion-objects/](https://www.geeksforgeeks.org/scala-singleton-and-companion-objects/)

#### 单例对象

Scala 是比 Java 更面向对象的语言，所以 Scala 不**不**包含任何**静态**关键字的概念。Scala 没有静态关键字，而是有**单例对象**。单例对象是定义一个类的单个对象的对象。单例对象为程序执行提供了入口点。如果你没有在你的程序中创建一个单独的对象，那么你的代码编译成功但是没有输出。所以你需要一个单独的对象来获得你的程序的输出。使用**对象**关键字创建单例对象。
**语法:**

```scala
object Name{
// code...
}
```

**关于单例对象的要点**

*   单例对象中的方法是全局可访问的。
*   不允许创建单例对象的实例。
*   不允许在单例对象的主构造函数中传递参数。
*   在 Scala 中，单例对象可以扩展类和特征。
*   在 Scala 中，一个主方法总是出现在单例对象中。
*   singleton 对象中的方法是用对象的名称来访问的(就像在 Java 中调用静态方法一样)，所以不需要创建一个对象来访问这个方法。

**例 1:**

## 斯卡拉

```scala
// A simple Scala program to illustrate
// the concept of singleton object

class AreaOfRectangle
{

    // Variables
    var length = 20;
    var height = 40;

    // Method which gives the area of the rectangle
    def area()
    {
        var ar = length * height;
        println("Height of the rectangle is:" + height);
        println("Length of the rectangle is:" + length);
        println("Area of the rectangle is :" + ar);
    }
}

// singleton object
object Main
{
    def main(args: Array[String])
    {

        // Creating object of AreaOfRectangle class
        var obj = new AreaOfRectangle();
        obj.area();
    }
}
```

**输出:**

```scala
Height of the rectangle is:40
Length of the rectangle is:20
Area of the rectangle is :800
```

**例 2:**

## 斯卡拉

```scala
// A Scala program to illustrate
// how to call method inside singleton object

// Singleton object with named
// as Exampleofsingleton
object Exampleofsingleton
{

    // Variables of singleton object
    var str1 = "Welcome ! GeeksforGeeks";
    var str2 = "This is Scala language tutorial";

    // Method of singleton object
    def display()
    {
        println(str1);
        println(str2);
    }
}

// Singleton object with named as Main
object Main
{
    def main(args: Array[String])
    {

        // Calling method of singleton object
        Exampleofsingleton.display();
    }
}
```

**输出:**

```scala
Welcome ! GeeksforGeeks
This is Scala language tutorial
```

**说明:**在上面的例子中，我们有两个单例对象，即 Exampleofsingleton 和 Main。Exampleofsingleton 对象包含一个名为 display()的方法，现在我们在 Main 对象中调用这个方法。使用以下语句:exampleofsingleton . display()；我们调用 Exampleofsingleton 对象中存在的 display()方法并打印输出。

#### 伴随对象

**伴随对象**被称为名称与类名相同的对象。或者换句话说，当一个对象和一个类具有相同的名称**，那么这个对象被称为伴随对象，而这个类被称为伴随类。伴随对象在定义类的同一源文件中定义。伴随对象被允许访问类的私有方法和私有字段。
**例:**** 

## **斯卡拉**

```scala
// A Scala program to illustrate
// the concept of the Companion object

// Companion class
class ExampleofCompanion
{

    // Variables of Companion class
    var str1 = "GeeksforGeeks";
    var str2 = "Tutorial of Companion object";

    // Method of Companion class
    def show()
    {
        println(str1);
        println(str2);
    }
}

// Companion object
object ExampleofCompanion
{
    def main(args: Array[String])
    {
        var obj = new ExampleofCompanion();
        obj.show();
    }
}
```

****输出:**** 

```scala
GeeksforGeeks
Tutorial of Companion object
```