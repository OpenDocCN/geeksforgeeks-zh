# 作为可堆叠修改的特性

> 原文:[https://www . geesforgeks . org/traits-as-staggable-modifications/](https://www.geeksforgeeks.org/traits-as-stackable-modifications/)

[](https://www.geeksforgeeks.org/scala-traits/)**的特性类似于 Java 的接口。类和对象可以扩展特征，但是特征不能被实例化，因此没有参数。它还 支持多个继承。性状是使用*性状*关键字创建的。**

****语法:****

```scala
trait Trait_Name {
// Fields..
// Methods..
} 
```

****super 关键字:**每当一个基类和子类有同名的方法时都会用到它，所以为了解决歧义，我们使用 super 关键字来调用基类方法。**

### ****具有特性的可堆叠修改****

**在此之前，首先我们应该借助一个例子来理解什么是**可堆叠修改**。考虑一位客户付费给手机充值，使用语音通话、互联网等移动服务。根据特定用户的使用情况，这些服务可以分为不同的包。如果我们想要实现这项服务，我们需要有客户为某个特定套餐付费的套餐名称，比如说*数据包*。所以我们可以这样说。**

```scala
new Recharge with DataPack 
```

**假设我们在充值类中有特定的价值，该类在某个包中列出了服务列表。如果消费者想再充值一个包，而我们不想有一个机制来为我们显式修改服务列表，但这应该是默认发生的。这就像是一种行为，随着我们不断添加不同的包而被修改。这种情况让我们了解了可堆叠修改的概念。随着客户添加新包装，列表将不断更新。**

```scala
new Recharge with DataPack with FullTalkTime 
```

**Scala 支持使用类或特征对任何方法进行堆叠式修改，这意味着您可以通过将类和特征混合在一起来堆叠它们，从而选择非常具体的行为。当你通过一遍又一遍地覆盖相同的方法来叠加一个新特性时，那么你的方法会有一个不同的或附加的行为。**

**下面的例子说明了特征是如何叠加的。**

****例 1:****

**在这个例子中，我们使用特性来修改类的方法，方法是以可堆叠的方式使用特性。这里，我们使用 super 关键字在两个特征中调用 dot()方法。这样，我们实现了可堆叠的修改。在可堆叠修改的情况下，方法调用顺序由线性化规则确定。**

## **斯卡拉**

```scala
// Scala program to illustrate traits 
// in stackable fashion

// Defining class shape
class Shape
{
  def dot(shape : String) = println("Dotted : " + shape)
}

// Using trait keyword
// Using super keyword
trait Square extends Shape 
{
  override def dot(shape : String) = super.dot("Square-" + shape)
}

// Using trait keyword
// Using super keyword
trait Circle extends Shape 
{
  override def dot(shape : String) = super.dot("Circle-" + shape)
}

// Using trait keyword
// Using super keyword
trait Sharp extends Shape
{
  override def dot(shape : String) = super.dot("Sharp-" + shape)
}

// Defining main
object Shapes 
{
  def main(args: Array[String]) 
  {
    val shape1 = new Shape with Sharp with Square
    shape1.dot("Shape-1") 

    val shape2 = new Shape with Circle with Sharp
    shape2.dot("Shape-2") 
}
}
```

****输出:****

```scala
Dotted : Sharp-Square-Shape-1
Dotted : Circle-Sharp-Shape-2 
```

****例 2:****

## **斯卡拉**

```scala
// Scala program to illustrate traits 
// in stackable fashion

// Defining class Ball
class Ball 
{
  def spin(ball : String) = println("Spinning : " + ball)
}

// Using trait keyword
// Using super keyword
trait Yellow extends Ball
{
  override def spin(ball : String) = super.spin("Yellow-" + ball)
}

// Using trait keyword
// Using super keyword
trait Blue extends Ball 
{
  override def spin(ball : String) = super.spin("Blue-" + ball)
}

// Using trait keyword
// Using super keyword
trait Shiny extends Ball 
{
  override def spin(ball : String) = super.spin("Shiny-" + ball)
}

// Defining main
object Balls
{
  def main(args: Array[String])
  {
    val ball1 = new Ball with Shiny with Yellow
    ball1.spin("Ball-1") 

    val ball2 = new Ball with Blue with Shiny
    ball2.spin("Ball-2") 
}
}
```

****输出:****

```scala
Spinning : Shiny-Yellow-Ball-1
Spinning: Blue-Shiny-Ball-2 
```