# C# |界面

> 原文:[https://www.geeksforgeeks.org/c-sharp-interface/](https://www.geeksforgeeks.org/c-sharp-interface/)

像类一样， ***接口*** 可以有方法、属性、事件和索引器作为其成员。但是接口将只包含成员的声明。接口成员的实现将由隐式或显式实现接口的类给出。

*   接口指定类必须做什么，而不是如何做。
*   接口不能有私有成员。
*   默认情况下，接口的所有成员都是公共的和抽象的。
*   该界面将始终借助关键字“*进行定义。*
*   *接口不能包含字段，因为它们代表数据的特定实现。*
*   **多重继承*在接口的帮助下是可能的，但在类的帮助下是不可能的。*

***接口声明语法:***

```cs
*interface  <interface_name >
{
    // declare Events
    // declare indexers
    // declare methods 
    // declare properties
}* 
```

***实现接口的语法:***

```cs
*class class_name : interface_name* 
```

*要声明接口，使用*接口*关键字。它用于提供全面的抽象。这意味着接口中的所有成员都是用空体声明的，默认情况下是公共的和抽象的。实现接口的类必须实现接口中声明的所有方法。*

*   ***例 1:**

    ```cs
    // C# program to demonstrate working of 
    // interface
    using System;

    // A simple interface
    interface inter1
    {
        // method having only declaration 
        // not definition
        void display();
    }

    // A class that implements interface.
    class testClass : inter1
    {

        // providing the body part of function
        public void display()
        {
            Console.WriteLine("Sudo Placement GeeksforGeeks");
        }

        // Main Method
        public static void Main (String []args)
        {

            // Creating object
            testClass t = new testClass();

            // calling method
            t.display();
        }
    }
    ```

    **输出:**

    ```cs
    Sudo Placement GeeksforGeeks

    ```* 
*   ***例 2:**

    ```cs
    // C# program to illustrate the interface
    using System;

    // interface declaration
    interface Vehicle {

        // all are the abstract methods.
        void changeGear(int a);
        void speedUp(int a);
        void applyBrakes(int a);
    }

    // class implements interface
    class Bicycle : Vehicle{

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
            Console.WriteLine("speed: " + speed + 
                              " gear: " + gear);
        }
    }

    // class implements interface
    class Bike : Vehicle {

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
        public void applyBrakes(int decrement){

            speed = speed - decrement;
        }

        public void printStates() 
        {
            Console.WriteLine("speed: " + speed + 
                              " gear: " + gear);
        }

    }

    class GFG {

        // Main Method
        public static void Main(String []args) 
        {

            // creating an instance of Bicycle 
            // doing some operations 
            Bicycle bicycle = new Bicycle();
            bicycle.changeGear(2);
            bicycle.speedUp(3);
            bicycle.applyBrakes(1);

            Console.WriteLine("Bicycle present state :");
            bicycle.printStates();

            // creating instance of bike.
            Bike bike = new Bike();
            bike.changeGear(1);
            bike.speedUp(4);
            bike.applyBrakes(3);

            Console.WriteLine("Bike present state :");
            bike.printStates();
        }
    }
    ```

    **输出:**

    ```cs
    Bicycle present state :
    speed: 2 gear: 2
    Bike present state :
    speed: 1 gear: 1

    ```* 

***接口优势:***

*   *用于实现松耦合。**   *它用于实现完全抽象。**   *为了实现基于组件的编程**   *实现多重继承和抽象。**   *接口将即插即用式架构添加到应用程序中。*