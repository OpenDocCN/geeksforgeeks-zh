# C# |如何使用接口引用

> 原文:[https://www . geesforgeks . org/c-sharp-使用方法-界面-参考资料/](https://www.geeksforgeeks.org/c-sharp-how-to-use-interface-references/)

在 C# 中，您可以创建一个接口类型的引用变量，或者换句话说，您可以创建一个接口引用变量。这类变量可以引用任何实现其接口的对象。接口引用变量只知道由其接口声明声明的方法。**它不允许访问对象**可能支持的任何其他变量或方法。当您使用父类引用来访问子类对象时，这个概念是相似的。

以下是说明接口引用概念的示例:

**例 1:**

```cs
// C# program to illustrate the 
// concept of Interface References
using System;

// interface declaration
public interface Race {

    // declaration of abstract methods of
    // interface that will be implemented 
    // by the class which inherits the interface
    void Speed(int s);
    void Distance(int d);
}

// class implementing interface
public class Person1 : Race {

    int sp1, di1;

    // abstract method of 
    // Race interface
    public void Speed(int p1s) {

        sp1 = p1s;
        Console.WriteLine("Speed Method implemented by Person1");

    }

    // abstract method of 
    // Race interface
    public void Distance(int p1d) {

        di1 = p1d;
        Console.WriteLine("Distance Method implemented by Person1");

    }

    // method of class Person1
    public void display1() {

        Console.WriteLine("The Speed of 1st person is: "+sp1);
        Console.WriteLine("The distance covered by 1st person is: "+di1);

    }

}

// class implementing interface
public class Person2 : Race {

    int sp2, di2;

    // abstract method of 
    // Race interface
    public void Speed(int p2s) {

        sp2 = p2s;
        Console.WriteLine("Speed Method implemented by Person2");

    }

    // abstract method of 
    // Race interface
    public void Distance(int p2d) {

        di2 = p2d;
        Console.WriteLine("Distance Method implemented by Person2");

    }

    // method of class Person2
    public void display2() {

        Console.WriteLine("The Speed of 2nd person is: "+sp2);
        Console.WriteLine("The distance covered by 2nd person is: "+di2);

    }

}

// Driver Class
public class GFG {

    // Main method
    public static void Main(String []args) {

        // creating an instance of Person1 class
        Person1 obj1 = new Person1();

        // creating an instance of Person2 class
        Person2 obj2 = new Person2();

        // creating an Reference 
        // of interface Race
        Race r;

        // ----- For Person1 Class ----------

        // assigning Person1 object 'obj1'
        // to interface Reference 'r'
        r = obj1;

        // Now you can access the abstract method
        // of Race interface which are implemented
        // by class Person1
        r.Speed(10);
        r.Distance(50);

        // if you will try to call display1() 
        // method using 'r' it will give error
        //r.display1();

        // calling the display1() 
        // method of Person1 Class
        obj1.display1();

        // ----- For Person2 Class ----------

        // assigning Person2 object 'obj2'
        // to interface Reference 'r'
        r = obj2;

        // Now you can access the abstract method
        // of Race interface which are implemented
        // by class Person2
        r.Speed(15);
        r.Distance(45);

        // if you will try to call display2() 
        // method using 'r' it will give error
        //r.display2();

        // calling the display1() 
        // method of Person1 Class
        obj2.display2();

    }

}
```

**输出:**

```cs
Speed Method implemented by Person1
Distance Method implemented by Person1
The Speed of 1st person is: 10
The distance covered by 1st person is: 50
Speed Method implemented by Person2
Distance Method implemented by Person2
The Speed of 2nd person is: 15
The distance covered by 2nd person is: 45

```

**说明:**在上面的例子中，我们有一个名为 *Race* 的接口，以及两个类 *Person1* 和 *Person2* ，它们实现了接口的方法。 *Person1* 类有自己的方法名为 *display1()* ，类似的 *Person2* 类有自己的方法 *display2()* ，不能使用接口引用调用。为了调用使用接口引用的方法(这里 *r* 是接口引用)，你必须给它分配一个类对象。例如，如果您将 Person1 的对象 *obj1* 分配给 *r* ，即*r = obj 1；*然后调用 *Person1* 类实现的 *Speed()* 和 *Distance()* 方法。要调用 *display1()* 方法，必须使用 obj1。同样使用*r = obj 2；*我们正在调用 *Person2* 类的方法。

**例 2:**

```cs
// C# program to illustrate the 
// concept of Interface References
using System;

// interface declaration
interface Vehicle {

    // all are the abstract methods.
    void changeGear(int a);
    void speedUp(int a);
    void applyBrakes(int a);
    void printStates();
}

// class implements interface
class Bicycle : Vehicle {

    int speed;
    int gear;

    // to change gear
    public void changeGear(int newGear)
    {

        gear = newGear;
    }

    // to increase speed
    public void speedUp(int increment)
    {

        speed = speed + increment;
    }

    // to decrease speed
    public void applyBrakes(int decrement)
    {

        speed = speed - decrement;
    }

    public void printStates()
    {
        Console.WriteLine("speed: " + speed + " gear: " + gear);
    }
}

// Driver Class
class GFG {

    // Main Method
    public static void Main(String[] args)
    {

        // creating an instance of Bicycle
        Bicycle bicycle = new Bicycle();

        // Creating interface references
        Vehicle obj;

        // assigning Bicycle object 'bicycle'
        // to interface Reference 'obj'
        obj = bicycle;

        // calling the abstract methods 
        // implemented by class Bicycle
        obj.changeGear(4);
        obj.speedUp(5);
        obj.applyBrakes(2);

        Console.WriteLine("Bicycle Present State:");

        // calling the method of class Bicycle 
        obj.printStates();
    }
}
```

**输出:**

```cs
Bicycle Present State:
speed: 3 gear: 4

```

**说明:**在上例中，Vehicle 是一个接口，Bicycle 类实现了这个接口。这里 *obj* 被声明为 Main()方法中对 Vehicle 接口的引用。现在这个 *obj* 用来指代自行车类的目标自行车。