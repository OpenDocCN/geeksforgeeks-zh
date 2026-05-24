# Scala |抽象类型成员

> 原文:[https://www.geeksforgeeks.org/scala-abstract-type-members/](https://www.geeksforgeeks.org/scala-abstract-type-members/)

如果一个特定的成员在类中没有一个完整的定义，那么这个成员被称为 ***抽象的*** 。这些抽象成员总是在定义它的类的任何子类中实现。这些类型的声明在许多编程语言中都是允许的，并且是面向对象编程语言的关键特性之一。Scala 还允许声明如下例所示的方法:

```scala
abstract class Sample{
  def contents: Array[String]
  def width: Int = a
  def height: Int = b
}

```

因此，在上面的类 Sample 中，我们已经声明了三个方法:内容、宽度和高度。后两种方法的实现已经定义，而在第一种方法 contents 中，没有提到任何类型的实现。因此，该方法是样本类的抽象成员。需要注意的是，具有抽象成员的类本身必须声明为抽象的。类前面的这个**抽象**关键字表示该类肯定会有一个没有实现的抽象成员。
如何编写类内抽象成员的另一个例子:

```scala
abstract class Example{
   type T
   def transform(x: T): T
   val initial: T
   var current: T
}

```

在上面的例子中，抽象类被声明，它定义了一个抽象类型 T、一个抽象方法转换、一个抽象初始值和一个抽象当前值。

下面是抽象类型成员的示例:

**示例:**

```scala
// Scala program of abstract type member 

// Declaring an abstract class
abstract class vehicle (name:String) 
{    
    // This is an abstract member 
    // with undefined implementation 
    val category: String     

    // A function that is used to print 
    // the value of the abstract member
    def car_type{ println(category) }  
    override def toString = s" The vehicle type is $category"
}

// Now extend the classes bike, car, 
// truck and bus and provide values 
// for the variable type

class car (name:String) extends vehicle (name)
{
    // assigning the value of 
    // the abstract member as car
    val category = "car"             
}
class bike (name:String) extends vehicle (name)
{
    // assigning the value of 
    // the abstract member as bike
    val category = "bike"         
}
class bus (name:String) extends vehicle (name)
{
    // assigning the value of 
    // the abstract member as bus
    val category = "bus"             
}
class truck (name:String) extends vehicle (name)
{
    // assigning the value of 
    // the abstract member as truck
    val category = "truck"         
}

object AbstractFieldsDemo extends App
{
    // assigning the name as Honda in the abstract
    // class where the category value is car
    val car = new car("Honda") 

    // assigning the name as Yamaha in the abstract 
    // class where the category value is bike
    val bike = new bike("Yamaha") 

    // assigning the name as Tata in the abstract 
    // class where the category value is bus
    val bus = new bus("Tata")     

    // assigning the name as Ashok_Leyland in the
    // abstract class where the category value is truck
    val truck = new truck("Ashok_Leyland") 

     // implementing the function 
     // car_type for the object car
    car.car_type

    // implementing the function 
    // car_type for the object bus
    bus.car_type

    // implementing the function 
    // car_type for the object truck
    truck.car_type     

    // implementing the function 
    // car_type for the object bus
    bike.car_type     
    println(car)
    println(bus)
    println(truck)
    println(bike)
}
```

**输出**

```scala
car
bus
truck
bike
The vehicle type is car
The vehicle type is bus
The vehicle type is truck
The vehicle type is bike

```

在上面的例子中，特征车辆有一个抽象的 val **类别**以及一个简单的名为 ***car_type*** 的具体方法和一个 toString 方法的覆盖。然后*车*、*车*、*车*、*车*类扩展**车**类，为字段*类*提供值。
我们在上面的代码中看到了抽象成员的未定义实现是如何被用来赋值和改变不同类型的每个对象的赋值的。就像在这个例子中，我们为不同类型的车辆存储了多个类别值。

因此，作为结论，抽象数据成员是那些具有未知实现的成员。