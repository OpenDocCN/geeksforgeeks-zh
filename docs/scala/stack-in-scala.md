# Scala 中的堆栈

> 原文:[https://www.geeksforgeeks.org/stack-in-scala/](https://www.geeksforgeeks.org/stack-in-scala/)

一个**栈**是一个遵循*后进先出*(后进先出)原则的数据结构。我们只能从称为*顶端*的一端添加或移除元素。Scala 有可变和不可变版本的堆栈。
**语法:**

```scala
import scala.collection.mutable.Stack
var s = Stack[type]()

// OR
var s = Stack(val1, val2, val3, ...)

```

**Operations on Stack**

一旦堆栈被创建，我们可以将**元素推到堆栈中，或者**将**元素弹出堆栈。**

*   **Push**: We can push element of any type to the stack using **push()** function. All elements must have same data type.
    **Example :**

    ```scala
    // Scala program to
    // push element
    // to the stack

    import scala.collection.mutable.Stack

    // Creating object
    object GfG
    {

        // Main method
        def main(args:Array[String])
        {

            var s = Stack[Int]()

            // pushing values
            // one at a time
            s.push(5)
            s.push(1)
            s.push(2)
            println("s:" + s)

            var s2 = Stack[Int]()

            // pushing multiple values
            s2.push(5,1,2)
            println("s2:" + s2)

        }
    }
    ```

    **输出**:

    ```scala
    s:Stack(2, 1, 5)
    s2:Stack(2, 1, 5)
    ```

*   **弹出**:我们可以使用**弹出**功能从栈顶弹出元素。该函数返回的类型与堆栈元素的类型相同。
    **例:**

```scala
// Scala program to
// pop element from
// top of the stack

import scala.collection.mutable.Stack

// Creating object
object GfG
{

    // Main method
    def main(args:Array[String])
    {

        var s = Stack[Int]()

        s.push(5)
        s.push(1)
        s.push(2)
        println(s)

        // pop element from
        // top of the stack

        println("Popped:" + s.pop)
        println("Popped:" + s.pop)
        println("Popped:" + s.pop)
    }
}
```

**输出**:

```scala
Stack(2, 1, 5)
Popped:2
Popped:1
Popped:5
```

**Other Functions**

**其他函数:**
我们再用例子讨论一些函数。

*   **isEmpty**: To check whether the stack is empty. Returns *true* if it is empty.
    **Example :**

    ```scala
    // Scala program to
    // check if the stack
    // is empty

    import scala.collection.mutable.Stack

    // Creating object
    object GfG
    {

        // Main method
        def main(args:Array[String])
        {

            var s = Stack[Int]()

            s.push(5)
            s.push(1)
            s.push(2)
            println(s)

            // pop element from
            // top of the stack

            println("Popped:" + s.pop)
            println("Popped:" + s.pop)
            println("Empty:" + s.isEmpty)
            println("Popped:" + s.pop)

            // all three elements popped
            println("Empty:" + s.isEmpty)
        }
    }
    ```

    **输出**:

    ```scala
    Stack(2, 1, 5)
    Popped:2
    Popped:1
    Empty:false
    Popped:5
    Empty:true
    ```

*   **top**: Returns the element that is currently at the top of the stack.
    **Example :**

    ```scala
    // Scala program to
    // print top of stack

    import scala.collection.mutable.Stack

    // Creating object
    object GfG
    {

        // Main method
        def main(args:Array[String])
        {

            var s = Stack[Int]()

            s.push(5)
            s.push(1)
            s.push(2)
            println(s)
            println("Top: " + s.top)
            println("Popped:" + s.pop)
            println("Top: " + s.top)
        }
    }
    ```

    **输出**:

    ```scala
    Stack(2, 1, 5)
    Top: 2
    Popped:2
    Top: 1
    ```

*   **size**:Returns the number of elements present in the stack.
    **Example :**

    ```scala
    // Scala program to
    // print size of the stack

    import scala.collection.mutable.Stack

    // Creating object
    object GfG
    {

        // Main method
        def main(args:Array[String])
        {

            var s = Stack[Int]()

            s.push(5)
            s.push(1)
            s.push(2)
            println(s)
            println("Size: " + s.size)
            println("Popped:" + s.pop)
            println("Size: " + s.size)
        }
    }
    ```

    **输出**:

    ```scala
    Stack(2, 1, 5)
    Size: 3
    Popped:2
    Size: 2
    ```