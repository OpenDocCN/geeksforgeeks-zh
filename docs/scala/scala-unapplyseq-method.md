# Scala | unappryseq()方法

> 原文:[https://www.geeksforgeeks.org/scala-unapplyseq-method/](https://www.geeksforgeeks.org/scala-unapplyseq-method/)

**unappriseq()**方法是一种*提取器*方法。它提取一个特定类型的对象，然后再次将其重构为一个提取值序列，并且该序列的长度在编译时没有指定。因此，为了重建包含序列的对象，您需要使用这个*不应用序列*方法。
**语法:**

```scala
def unapplySeq(object: X): Option[Seq[T]]
```

这里，我们有一个类型为 X 的对象，当该对象不匹配时，该方法要么返回 *None* ，要么返回包含在类 *Some* 中的类型为 T 的提取值序列。
现在，让我们通过一些例子来理解它。

**示例:**

```scala
// Scala program of unapplySeq
// method

// Creating object
object GfG
{

    // Defining unapplySeq method
    def unapplySeq(x:Any): Option[Product2[Int,Seq[String]]] = 
    {

        val y = x.asInstanceOf[Author] 

        if(x.isInstanceOf[Author]) 
        {
            Some(y.age, y.name)
        }     
        else
            None
    } 

    // Main method
    def main(args:Array[String]) = 
    {

        // Creating object for Author
        val x = new Author

        // Applying Pattern matching
        x match
        {
            case GfG(y:Int,_,z:String) =>

            // Displays output
            println("The age of "+z+" is: "+y)
        }

        // Assigning age and name
        x.age = 22
        x.name = List("Rahul","Nisha")

        // Again applying Pattern matching
        x match
        {                             
            case GfG(y:Int,_,z:String) => 

            //Displays output
            println("The age of "+z+" is: "+y)
        }
    }
}

// Creating class for author
class Author
{

    // Assigning age and name
    var age: Int = 24
    var name: Seq[String] = List("Rohit","Nidhi")
}
```

**Output:**

```scala
The age of Nidhi is: 24
The age of Nisha is: 22

```

这里，我们在*选项*中使用了一个特性*产品 2* ，以便向其传递两个参数。*产品 2* 是两个元素的笛卡尔乘积。
**例:**

```scala
// Scala program of using 
//'UnapplySeq' method of 
// Extractors

// Creating object
object GfG 
{

    // Main method
    def main(args: Array[String]) 
    {
        object SortedSeq
        {

            // Defining unapply method
            def unapplySeq(x: Seq[Int]) = 
            {
                if (x == x.sortWith(_ < _)) 

                {
                    Some(x) 
                }
                else None
            }
        }

        // Creating a List                     
        val x = List(1,2,3,4,5) 

        // Applying pattern matching
        x match 
        { 
            case SortedSeq(a, b, c, d,e) =>

        // Displays output
        println(List(a, c, e))
        } 
    }
}
```

**Output:**

```scala
List(1, 3, 5)

```

这里，我们使用了一个函数 *sortWith* ，它按照比较函数的指定对所述序列进行排序。