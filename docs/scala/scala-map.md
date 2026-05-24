# 斯卡拉地图

> 原文:[https://www.geeksforgeeks.org/scala-map/](https://www.geeksforgeeks.org/scala-map/)

**映射**是键值对的集合。换句话说，它类似于字典。键总是唯一的，而值不必是唯一的。键值对可以有任何数据类型。但是，一旦用于任何键和值，数据类型必须始终一致。地图分为两种类型:*可变*和*不可变*。默认情况下，Scala 使用不可变映射。为了使用可变映射，我们必须显式导入**Scala . collection . mutable . Map**类。

<center>**如何创建斯卡拉地图**</center>

地图可以根据我们的需求和地图的性质以不同的方式创建。根据映射是可变的还是不可变的，我们有不同的语法。

**语法:**

```scala
// Immutable
variable = Map(key_1 -> value_1, key_2 -> value_2,
 key_3 -> value_3, ....)

// Mutable
variable = scala.collection.mutable.Map(key_1 -> value_1, 
key_2 -> value_2, key_3 -> value_3, ....)
```

<center>**斯卡拉地图上的操作**</center>

我们可以在地图上执行三种基本操作:

1.  **键:**在 Scala 映射中，这个方法返回一个包含映射中每个键的 iterable。
2.  **值:** Value 方法返回一个包含 Scala 映射中每个值的 iterable。
3.  **isEmpty:** This Scala map method returns true if the map is empty otherwise this returns false.

    <center>**使用键访问值**</center>

    可以使用映射变量名和键来访问值。
    **例:**

    ```scala
    // Scala map program of 
    // Accessing Values Using Keys

    // Creating object 
    object GFG
    {
        // Main method
        def main(args:Array[String])
        {

            val mapIm = Map("Ajay" -> 30, 
                            "Bhavesh" -> 20,
                            "Charlie" -> 50)

            // Accessing score of Ajay
            val ajay = mapIm("Ajay") 
            println(ajay)
        }
    } 
    ```

    **输出:**

    ```scala
    30
    ```

    如果我们试图访问与关键字“John”相关联的值，我们将会得到一个错误，因为在地图中不存在这样的关键字。因此，在使用键访问任何值时，建议使用 **contains()** 函数。
    该功能检查地图中的钥匙。如果密钥存在，则返回真，否则返回假。

    ```scala
    // Scala map program of 
    // Accessing Values Using 
    // Keys by contains() function

    // Creating object
    object GFG
    {

        // Main methode
        def main(args:Array[String])
        {
            val mapIm = Map("Ajay" -> 30,
                            "Bhavesh" -> 20,
                            "Charlie" -> 50)

            // the key check in the Map
            val ajay = if(mapIm.contains("Ajay"))
                            mapIm("Ajay") else 0

            val john = if(mapIm.contains("John"))
                            mapIm("John") else 0

            println("Ajay:" + ajay)
            println("John:" + john)
        }
    } 
    ```

    **输出:**

    ```scala
    Ajay:30 
    John:0
    ```

    <center>**更新数值**</center>

    如果我们试图更新不可变映射的值，Scala 会输出一个错误。另一方面，在可变映射的情况下，任何键的值的任何改变都是可以接受的。
    **示例:**
    **更新不可变地图:**

    ```scala
    // Scala map program of 
    // Updating the values
    // in immutable map

    // Creating an object
    object GFG
    {
        // Main method
        def main(args:Array[String])
        {

            val mapIm = Map("Ajay" -> 30, 
                            "Bhavesh" -> 20, 
                            "Charlie" -> 50)

            println(mapIm)

            //Updating
            mapIm("Ajay") = 10 

            println(mapIm)

        }
    }
    ```

    **输出:**

    > 错误:值更新不是 scala.collection .不可变. Map[String，Int]的成员

    **更新可变地图:**

    ```scala
    // Scala map program of 
    // Updating the values
    // in mutable map

    // Creating Object
    object GFG
    {

        // Main method
        def main(args:Array[String])
        {

            val mapMut = scala.collection.mutable.Map("Ajay" -> 30,
                                                      "Bhavesh" -> 20, 
                                                      "Charlie" -> 50)
            println("Before Updating: " + mapMut)

            // Updating
            mapMut("Ajay") = 10 

            println("After Updating: " + mapMut)
        }
    }
    ```

    **输出:**

    > 更新前:地图(Ajay -> 30，Charlie -> 50，Bhavesh -> 20)
    > 更新后:地图(Ajay - > 10，Charlie - > 50，Bhavesh - > 20)

    <center>**添加新的键值对**</center>

    我们可以使用 **+=** 运算符在可变映射中插入新的键值对，然后添加或更新新的键值对。
    T3】例:

    ```scala
    // Scala map program of 
    // Adding new key-value pair

    // Creating object
    object GFG
    {

        // Main method
        def main(args:Array[String])
        {

            val mapMut = scala.collection.mutable.Map("Ajay" -> 30, 
                                                      "Bhavesh" -> 20,
                                                      "Charlie" -> 50)

            println("Before Adding: "+mapMut)

            // Adding a new key "Dinesh" and 
            // updating an existing key "Ajay"
            mapMut += ("Ajay" -> 10, "Dinesh" -> 60)

            println("After Adding: "+mapMut)
        }
    }
    ```

    **输出:**

    > 添加前:地图(Ajay -> 30，Charlie -> 50，Bhavesh -> 20)
    > 添加后:地图(Ajay - > 10，Dinesh - > 60，Charlie - > 50，Bhavesh - > 20)

    <center>**删除键值对:**</center>

    删除键值对类似于添加新条目。不同的是，我们不是使用 **+=** 而是使用 **-=** 运算符，后面跟着要删除的键。
    **例:**

    ```scala
    // Scala map program of 
    // Deleting new key-value pair

    // Creating object
    object GFG
    {

        // Main method
        def main(args:Array[String])
        {

            val mapMut = scala.collection.mutable.Map("Ajay" -> 30,
                                                      "Bhavesh" -> 20,
                                                      "Charlie" -> 50)

            println("Before Deleting: "+mapMut)

            // Deleting key-value pairs with
            // keys "Ajay" and "Charlie"
            mapMut -= ("Ajay", "Charlie")

            println("After Deleting: " + mapMut)
        }
    }
    ```

    **输出:**

    > 删除前:地图(Ajay -> 30，Charlie -> 50，Bhavesh -> 20)
    > 删除后:地图(Bhavesh - > 20)

    <center>**地图中的迭代**</center>

    键值对对应于包含两个元素的元组。因此，在执行迭代时循环变量需要是一对。
    要了解 Scala 中循环的语法和工作方式，请参考: [Loops|Scala](https://www.geeksforgeeks.org/scala-loopswhile-do-while-for-nested-loops/)
    **示例:**

    ```scala
    // Scala map program of 
    // Iteration in a Map

    // Creating object
    object GFG
    {

        // Main method
        def main(args:Array[String])
        {

            val mapMut = scala.collection.mutable.Map("Ajay" -> 30,
                                                      "Bhavesh" -> 20,
                                                      "Charlie" -> 50)

            // (k, v) is a tuple with two elements
            for((k, v) <- mapMut) 
            {    
                //where k is key and v is value
                print("Key:"+k+", ")
                println("Value:"+v)
            }
        }
    }
    ```

    **输出:**

    ```scala
    Key:Ajay, Value:30
    Key:Charlie, Value:50
    Key:Bhavesh, Value:20
    ```

    <center>**空图**</center>

    在 Scala Map 中，我们还可以创建一个空的 Map，然后在其中添加元素。
    **例:**

    ```scala
    // Scala map program of 
    // Empty Map

    // Creating object
    object GFG
    {

        // Main method
        def main(args:Array[String])
        {

            // Creation of Map having key-value
            // pairs of type (String, Int)
            val mapMut = scala.collection.mutable.Map[String, Int]()

            println("Empty Map: " + mapMut)

            // Adding new entry
            mapMut += ("Charlie" -> 50) 

             println("New Entry: " + mapMut)
        }
    }
    ```

    **输出:**

    ```scala
    Empty Map: Map()
    New Entry: Map(Charlie -> 50)
    ```