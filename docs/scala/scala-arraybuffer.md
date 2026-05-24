# 合并\阵列缓冲区

> 哎哎哎:# t0]https://www . geeksforgeeks . org/scale-array buffer/

scala 中的**数组**是*同构的*和*可变的*，即它包含相同数据类型的元素，其元素可以改变但数组大小的大小不能改变。创建一个可变的索引序列，它的大小可以改变**使用数组填充**类。使用时，导入 ArrayBuffer**Scala . collection . mutable . ArrayBuffer**类，创建一个 ArrayBuffer 实例。
在内部，ArrayBuffer 是元素的数组，以及存储区当前的数组大小。当一个元素被添加到数组缓冲区时，这个大小被检查。如果基础数组未满，则元素会直接添加到数组中。如果基础数组已满，则构建一个更大的数组，并将所有元素复制到新数组中。关键是新数组的构造大于当前添加所需的大小。

**示例:**

```scala
var name = new ArrayBuffer[datatype]()  // empty buffer is created

var name = new ArrayBuffer("chandan", "gfg", "geeksforgeeks")

```

在上面的例子中，首先，在这里创建一个空缓冲区，数据类型表示数据类型，如整数、字符串。然后用字符串类型的三个元素创建了缓冲区。

### 数组缓冲区上的操作

1.  **创建 ArrayBuffer 实例:**

    ```scala
    // Scala program to create an ArrayBuffer
    // ArrayBuffer class is imported
    import scala.collection.mutable.ArrayBuffer

    // Creating Object
    object GFG 
    {

    // Main Method
    def main(args: Array[String])
    {
        // Instance of ArrayBuffer is created
        var name = ArrayBuffer[String]() 
        name += "GeeksForGeeks"
        name += "gfg"
        name += "Chandan"
        println(name)
    }
    }
    ```

    **输出:**

    ```scala
    ArrayBuffer(GeeksForGeeks, gfg, Chandan)

    ```

2.  **从 ArrayBuffer 访问元素:**
    元素的访问与数组相同， **ArrayBuffer(i)** 用于访问数组的索引元素。

```scala
// Scala program to access element of ArrayBuffer
// ArrayBuffer class is imported
import scala.collection.mutable.ArrayBuffer

// Creating Object
object GFG 
{

// Main Method
def main(args: Array[String]) 
{
    // Instance of ArrayBuffer is created
    var name = ArrayBuffer[String]() 
    name += "GeeksForGeeks"
    name += "gfg"
    name += "Chandan"

    // accessing 1th index element of arraybuffer
    println(name(1)) 
}
}
```

**Output:**

```scala
gfg

```

*   **Adding elements in ArrayBuffer:**
    *   向缓冲区添加单个元素

        ```scala
        ArrayBuffer+=( element)
        ```

    *   添加两个或更多元素(方法有 varargs 参数)

        ```scala
        ArrayBuffer+= (element1, element2, ..., elementN )
        ```

    *   追加一个或多个元素(使用 varargs 参数)

        ```scala
        ArrayBuffer.append( elem1, elem2, ... elemN)
        ```

    **示例:**

    ```scala
    // Scala program to add element in ArrayBuffer
    // ArrayBuffer class is imported
    import scala.collection.mutable.ArrayBuffer

    // Creating Object
    object GFG
    {

    // Main Method
    def main(args: Array[String]) 
    {
        // Instance of ArrayBuffer is created
        var name = ArrayBuffer[String]() 

        // adding one element
        name += "GeeksForGeeks"

        // add two or more elements 
        name += ("gfg", "chandan")

        // adding one or more element using append method 
        name.append("S-series", "Ritesh") 

        // printing arraybuffer
        println(name) 
    }
    }
    ```

    **Output:**

    ```scala
    ArrayBuffer(GeeksForGeeks, gfg, chandan, S-series, Ritesh)

    ```

    *   **Deleting ArrayBuffer Elements:**
    *   移除一个元素

        ```scala
        ArrayBuffer-= (element)
        ```

    *   移除多个元素

        ```scala
        ArrayBuffer-= (elem1, elem2, ....., elemN)
        ```

    **示例:**

    ```scala
    // Scala program to delete element from ArrayBuffer
    // ArrayBuffer class is imported
    import scala.collection.mutable.ArrayBuffer

    // Creating Object
    object GFG 
    {

    // Main Method
    def main(args: Array[String]) 
    {
        // Instance of ArrayBuffer is created
        var name = ArrayBuffer( "GeeksForGeeks","gfg",
                                "chandan","S-series", 
                                "Ritesh" ) 

        // deletes one element
        name -= "GeeksForGeeks"

        // deletes two or more elements 
        name -= ("gfg", "chandan")

        // printing resultant arraybuffer
        println(name) 
    }
    }
    ```

    **Output:**

    ```scala
    ArrayBuffer(S-series, Ritesh)

    ```

    *   **Deleting ArrayBuffer Elements using **ArrayBuffer.remove()** :**

    **remove** 方法用于根据一个元素在数组缓冲区中的位置删除该元素，或者从起始位置开始删除一系列元素。

    **示例:**

    ```scala
    // Scala program for remove method, on ArrayBuffer
    // ArrayBuffer class is imported
    import scala.collection.mutable.ArrayBuffer

    // Creating Object
    object GFG 
    {

    // Main Method
    def main(args: Array[String]) 
    {
        // Instance of ArrayBuffer is created
        var name = ArrayBuffer( "GeeksForGeeks",
                                "gfg", "chandan",
                                "S-series", "Ritesh" ) 

        // removing 0th index element
        name.remove(0) 

        // printing resultant arraybuffer
        println(name)
        name.remove(1, 3)

        // printing resultant arraybuffer
        println(name) 
    }
    }
    ```

    **Output:**

    ```scala
    ArrayBuffer(gfg, chandan, S-series, Ritesh)
    ArrayBuffer(gfg)

    ```