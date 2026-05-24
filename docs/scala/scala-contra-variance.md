# 标量–反向方差

> 原文:[https://www.geeksforgeeks.org/scala-contra-variance/](https://www.geeksforgeeks.org/scala-contra-variance/)

反向方差正好与协方差相反。反向差异在类和类型参数之间创建类似的子类型关系。所以，反方差说，如果有两个参数化的类型，S 是 T 的一个子类型，那么列表[T]就是列表[S]的一个子类型。我们可以通过使用符号[-S]来创建一个泛型类反变型。每当类型(泛型)参数“消耗”类型 S 或接受的类型时，我们可以使用反向方差。我们也可以将 contra-variant 用作方法参数类型，但不能用作方法返回类型，因为它会生成编译错误。

**语法:**

```scala
List[-T]
```

这里，T 是类型参数，而–是逆变的符号。

**示例 1:** 让我们考虑一个例子，其中打印机是打印某种类型的类。我们将在这里为类型定义子类:

```scala
// Scala program to illustrate contra-variance 

abstract class Printer[-S] 
{  
    // Here -S denotes Contra-Variant 
    // type S
    def print(value: S): Unit
} 

abstract class Flower
{
    def name: String
}

// Create subclass of Flower
case class Lily(name: String) extends Flower

class FlowerPrinter extends Printer[Flower] 
{
    def print(flower: Flower): Unit =

    // Display name of flower
    println("The flower's name is: " + flower.name)
}

class LilyPrinter extends Printer[Lily] 
{
    def print(lily: Lily): Unit =
    println("Lily's name is: " + lily.name)
}

// Inherit the main method
object Contravariance extends App
{

    // Assign value    
    val lily : Lily = Lily("White Lily") 

    // Define method to print the name
    def printMyLily(printer: Printer[Lily]): Unit =
    {
        printer.print(lily)
    }

    // Create objects
    val lilyPrinter: Printer[Lily] = new LilyPrinter
    val flowerPrinter: Printer[Flower] = new FlowerPrinter

    printMyLily(lilyPrinter)
    printMyLily(flowerPrinter)
}
```

**输出:**

```scala
Lily's name is: White Lily
The flower's name is: White Lily

```

**说明:**在此代码中，如果打印机[Lily]可以打印任意一朵百合，打印机[Flower]可以打印一朵花，那么打印机[Flower]也可以打印百合。但是反过来不行，因为打印机[莉莉]不知道怎么打印任何花。因此，我们可以使用 Print[Flower]作为 Printer[Lily]的替代品，我们可以通过制造 Printer[S]反向变体来做到这一点。

**示例 2:** 考虑该示例通用级车辆:

```scala
// Scala program to illustrate contra-variance 

abstract class GetVehicleName[-S] 
{  
    // Here -S denotes Contra-Variant
    // type S
    def print(value: S): Unit
}

abstract class Vehicle
{
    def name: String
}

// Create subclass of Flower
case class Bike(name: String) extends Vehicle

class VehicleName extends GetVehicleName[Vehicle]
{
    def print(vehicle: Vehicle): Unit =
    println("The vehicle's name is: " + vehicle.name)
}

class BikeName extends GetVehicleName[Bike] 
{
    def print(bike: Bike): Unit =
    println("Bike's name is: " + bike.name)
}

// Inherit the main method
object Contravariance extends App
{

    // Assign value    
    val bike : Bike = Bike("Yamaha Fazer") 

    // Define method to print the name
    def printMyBike(getVehicleName: GetVehicleName[Bike]): Unit =
    {
        getVehicleName.print(bike)
    }

    // Create objects
    val bikeName: GetVehicleName[Bike] = new BikeName
    val vehicleName: GetVehicleName[Vehicle] = new VehicleName

    printMyBike(bikeName)
    printMyBike(vehicleName)
}
```

**输出:**

```scala
Bike's name is: Yamaha Fazer
The vehicle's name is: Yamaha Fazer

```

**解释:**在这个例子中，由于反向方差，我们得到了两者相同的输出。由于抽象类 Get_vehicle_name 是反变的，我们可以用 Get_vehicle_name[Vehicle]替换 Get _ Vehicle _ name[Vehicle]，但不允许反变。