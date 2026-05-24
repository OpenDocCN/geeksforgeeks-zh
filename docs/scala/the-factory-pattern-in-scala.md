# 斯卡拉工厂模式

> 原文:[https://www.geeksforgeeks.org/the-factory-pattern-in-scala/](https://www.geeksforgeeks.org/the-factory-pattern-in-scala/)

**工厂方法**用于提供单个接口来实例化多个类中的一个。在[工厂模式](https://www.geeksforgeeks.org/design-patterns-set-2-factory-method/)中，目标是使对象不暴露给客户端的创建逻辑，并且总是可以借助公共接口引用新创建的对象。

让我们试着用一个例子来理解它。

假设我们需要为汽车购买应用程序创建一个库。图书馆应该提供三种汽车类型的选择。

我们遵循面向对象的设计，因此我们决定创建三个不同的类。每种车型一个。我们还希望提供获得预订价格、品牌和可用性的方法。所有三个类都将单独实现它们的方法，但是我们必须决定一个简单的方法来创建一个 Car 对象。这样所有的车都可以用同样的方法购买。这是一个我们想如何预订汽车的例子。第一个语句返回一个标准汽车的实例。第二个语句返回一辆豪华轿车，第三个语句给出一辆豪华轿车。在这种情况下，我们提供了一种创建各种对象的方法。这里的方法汽车是一家汽车工厂。我们可以预订我们需要的任何类型的汽车，想要多少就预订多少。这种类型的对象创建使得编程非常容易，并且代码紧凑。人们不必担心不同种类的汽车有不同的等级。这就是工厂方法的意义所在。

```scala
// Scala program of Design factory pattern

// creating abstract class for the car
abstract class Car{

        // Creating four abstract methods
        def bookingPrice : Double
        def Brands : List[String]
        def availability : Int
        def book(noOfCars:Int)
    }

    // Creating an object
    object Car{
        val STANDARD = 0
        val DELUXE = 1
        val LUXURY = 2

        // Creating private class
        private class standardCar extends Car{
            private var _availability = 100
            override def bookingPrice = 200000
            override def Brands = List("Maruti", "Tata", "Hyundai")
            override def availability = _availability
            override def book(noOfCars:Int) = {
                _availability = _availability - noOfCars
            }
        }

        // Creating private class
        private class DeluxeCar extends Car{
            private var _availability = 50
            override def bookingPrice = 500000
            override def Brands = List("Honda", "Mahindra", "Chevrolet")
            override def availability = _availability
            override def book(noOfCars:Int) = {
                _availability = _availability - noOfCars
            }
        }

        // Creating private class
        private class LuxuryCar extends Car{
            private var _availability = 5
            override def bookingPrice = 900000
            override def Brands = List("Audi","BMW", "Mercedes")
            override def availability = _availability
            override def book(noOfCars:Int) = {
                _availability = _availability - noOfCars
            }
        }

        // create the apply method
        // single method to create a variety of objects
        def apply(carType:Int):Car = {
            carType match {
                case LUXURY => new LuxuryCar()
                case DELUXE => new DeluxeCar()
                case STANDARD => new standardCar()
                case _ => new standardCar()
            }
        }
         // Main method 
        def main(args: Array[String])  
        { 
            val s = Car(STANDARD)   
            println(s.bookingPrice)
            println(s.availability) 
        }        
    }
```

**输出:**

```scala
200000.0
100

```

因此，工厂方法有助于简化编程概念。通过这种方式，如果声明多个相同类型但有些不同的对象，我们总是可以节省代码空间和类的数量。