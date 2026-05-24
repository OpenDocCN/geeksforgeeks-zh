# Scala |有状态对象

> 原文:[https://www.geeksforgeeks.org/scala-stateful-object/](https://www.geeksforgeeks.org/scala-stateful-object/)

有状态对象是指具有可变成员或可变成员的对象，这些成员可以改变先前在对象上执行的事务或操作。对于多次执行的同一操作，输出的结果可能与以前的结果不同。将有状态对象与现实世界的对象进行比较是非常常见的，在现实世界中，对象的状态会随着时间的推移而变化。

**语法:**

```scala
class classname
{
     // declaring some states that are mutable
     var state1
     var state2
     def changestate
     {
          // some operation to change the states of the object
     }
}

```

当一个对象的成员随着时间的推移而改变其值时，就会对该对象执行某些操作。因此，对象的状态会根据之前执行的操作而改变。

下面是一些理解有状态对象的例子。
**示例#1:**

```scala
// A Scala program to illustrate 
// stateful objects

// creating a class
class waterbottle
{
    // creating states
    var water: Int = 0
    def drinkwater = { 
        if(water > 0)
        {
            water = water-1
            println("water left = "+water)
        }
        else
        {
            println("waterbottle empty fill water")
        }
    }

    // Defining method
    def fillwater (c: Int)=
    {
        if(water + c > 5)
        {
            water = 5
        }
        else
        { 
            water = water + c
        }
    }
    override def toString= "water in bottle = " + water
}

// Creating object
object GFG 
{
    // Main method 
    def main(args: Array[String]) 
    { 
        // waterbottle object
        var w = new waterbottle

        // calling 
        w.fillwater(3)
        println(w)

        // Changing state
        w.drinkwater
        w.drinkwater
        w.drinkwater
        w.drinkwater
    } 
}
```

**输出:**

```scala
water in bottle = 3
water left = 2
water left = 1
water left = 0
waterbottle empty fill water

```

从上面的例子中我们可以看到 **w 饮用水**的状态将其相同操作的结果更改为**“水床空注水”**，直到我们注水或更新水。可变状态取决于水，水是一个变量。因此我们可以说有状态对象是由 **vars** 而不是 **val** 构成的，但这不是真的，一个类可以在不包含任何 vars 的情况下改变它的状态。

对于将其状态改变为另一状态的对象，操作集或达到该特定状态所采用的路径可能不同，但最终达到的状态应该是相同的。这也被称为**操作等式**，其中 **x & y** 是不同的对象，但是在不同的操作集结束时具有相同的状态。

**示例#2:**

```scala
// A Scala program to illustrate 
// stateful objects

// creating player class
class player
{
    // creating states
    var health: Int = 10
    def punch(p: player)
    {
        if(p.health > 0)
        {
            p.health = p.health-2
            println(p + " health is " + p.health)
            if(p.health < 1)
            {
                // checking the state
                dead(p)
            }
        }
        else
        {
            dead(p)
        }
    }
    def kick(p: player)
    {
        if(p.health > 0)
        {
            p.health = p.health-3
            println(p + " health is " + p.health)
            if(p.health < 1)
            {
                // checking the state
                dead(p)
            }
        }
        else
        {
            dead(p)
        }
    }
    def superp(p: player)
    {
        if(p.health > 0)
        {
            p.health = p.health - 5
            println(p + " health is " + p.health)
            if(p.health < 1)
            {
                // checking the state
                dead(p)
            }
        }
        else
        {
            dead(p)
        }
    }
    def dead(p:player)
    {
        println("Game Over")
        println(p +" is dead " + this + " is winner")
    }
}

// Creating object
object GFG
{
    // Main method 
    def main(args: Array[String]) 
    { 
        // Creating objects for player
        var p1 = new player
        var p2 = new player
        p1.kick(p2)
        p1.punch(p2)
        p1.superp(p2)
        p1.punch(p2)

    } 
}
```

**输出:**

```scala
player@506e1b77 health is 7
player@506e1b77 health is 5
player@506e1b77 health is 0
Game Over
player@506e1b77 is dead player@4fca772d is winner
Game Over
player@506e1b77 is dead player@4fca772d is winner

```

类似地，在上面的例子中，我们可以不用看类的内部工作就知道玩家是一个**有状态对象**。因为生命值不能减少到负数，所以玩家有可变状态，因为相同的操作在不同或相同的输入下返回不同的输出。