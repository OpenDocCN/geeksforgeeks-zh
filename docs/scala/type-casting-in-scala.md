# Scala 型铸造

> 原文:[https://www.geeksforgeeks.org/type-casting-in-scala/](https://www.geeksforgeeks.org/type-casting-in-scala/)

类型转换基本上是从一种类型到另一种类型的转换。在像 Scala 这样的动态编程语言中，经常需要从一种类型转换成另一种类型。Scala 中的类型铸造是使用**作为[]** 方法的实例来完成的。

**Applications of asInstanceof method**

*   在应用程序上下文文件中显示 beans 时需要这个视角。
*   它也用于转换数值类型。
*   它甚至可以应用在复杂的代码中，比如与 Java 通信并向它发送一个对象实例数组。

> **语法:**
> obj 1 = obj . as instance of[class]；
> **其中，**
> obj1 是 obj 的铸造实例返回到的对象，
> obj 是要铸造的对象，
> class 是 obj 要铸造到的类的名称。

在这里，只有扩展(子)类的对象可以被转换为其父类的对象，但不能反过来。如果类 A 扩展了类 B，那么 A 的对象可以被转换成类 A 的对象。B and B 的对象不能被转换成类 A 的对象。这个方法通知编译器这个值是指定的类型。在运行时，如果提供的值/对象与指定的类型或类不兼容，则会引发异常。

**示例:**

## 斯卡拉

```scala
// Scala program of type casting
object GFG
{
    // Function to display name, value and
    // class-name of a variable
    def display[A](y:String, x:A)
    {
        println(y + " = " + x + " is of type " +
                            x.getClass.getName);
    }

    // Main method
    def main(args: Array[String])
    {
        var i:Int = 40;
        var f:Float = 6.0F;
        var d:Double = 85.2;
        var c:Char = 'c';

        display("i", i);
        display("f", f);
        display("d", d);
        display("c", c);

        var i1 = i.asInstanceOf[Char]; //Casting
        var f1 = f.asInstanceOf[Double]; //Casting
        var d1 = d.asInstanceOf[Float]; //Casting
        var c1 = c.asInstanceOf[Int]; //Casting

        display("i1", i1);
        display("f1", f1);
        display("d1", d1);
        display("c1", c1);
    }
}
```

**输出:**

```scala
i = 40 is of type java.lang.Integer
f = 6.0 is of type java.lang.Float
d = 85.2 is of type java.lang.Double
c = c is of type java.lang.Character
i1 = ( is of type java.lang.Character
f1 = 6.0 is of type java.lang.Double
d1 = 85.2 is of type java.lang.Float
c1 = 99 is of type java.lang.Integer
```

**示例:**

## 斯卡拉

```scala
// Scala program of type casting

// The parent class
class Parent
{
    var i: Int = 10;
    var j: Int = 5;

    // Function to display i and j values
    def display()
    {
        println("Value of i : " + i +
                "\nValue of j : " + j);
    }
}

// The child class
class Child extends Parent
{
    // Used to change i and j values
    def change()
    {
        i = 6;
        j = 12;
        println("Values Changed");
    }
}

// Creating object
object GFG
{
    // Main method
    def main(args: Array[String])
    {
        var c:Child = new Child();
        c.display();
        c.change();

        // Casting
        var p:Parent = c.asInstanceOf[Parent];
        p.display();

        /* p.change(); This will have raised an error
        as p is seen as an object of class Parent and
        Parent does not contain change() */
    }
}
```

**输出:**

```scala
Value of i : 10
Value of j : 5
Values Changed
Value of i : 6
Value of j : 12
```

在上例中**p . change()；将添加**，将出现以下错误:

```scala
error:value change is not a member of parent.
```

**示例:**

## 斯卡拉

```scala
// Scala program of type casting

class Parent
{
    // Member variables and functions.    
}

class Child extends Parent
{
    // Member variables and functions.    
}

class Unrelated
{
    // Member variables and functions.    
}

// Creating object
object GFG
{
    // Main method
    def main(args: Array[String])
    {
        var p:Parent = new Parent();
        try
        {
            p.asInstanceOf[Unrelated];
        }
        catch
        {
            // Used to print the thrown exception.
            case e: Exception => e.printStackTrace();
                        print(e);
        }
        try
        {
            p.asInstanceOf[Child];
        }
        catch
        {
            // Used to print the thrown exception.
            case e1: Exception => e1.printStackTrace();
                        print(e1);
        }
    }
}
```

**输出:**

```scala
java.lang.ClassCastException: Parent cannot be cast to Unrelated
java.lang.ClassCastException: Parent cannot be cast to Child
```