# 横向线刻度| Set-1

> 哎哎哎:# t0]https://www . geeksforgeeks . org/scale-traversal-set-1/

**简介:**
斯卡拉系列的一个根本特征是**可穿越特征**。它位于集合层次结构的最高位置。它有一个唯一的抽象操作，那就是 **foreach** 。这里，每个操作都保证以单线程方式执行。
**语法:**

```scala
def foreach[U](f: Elem => U)
```

这里，操作 **f** 涉及集合的所有元素， **Elem = > U** 是操作的类型，其中“Elem”是 Scala 集合中元素的类型，“U”是不一致的结果类型。

**一些要点:**

*   可遍历性是由 Scala 的集合类实现的。
*   Traversable 必须只为每个方法定义*，因为 Traversable 可以继承所有其他方法。*
*   方法可以遍历 Scala 集合类的所有元素。
*   Traversables 定义了许多具体的方法。
*   列表、数组、映射、集合等等都是可遍历的子类。

**Operations performed by the Class Traversable are as follows:**

1.  **抽象方法:**
    这里唯一的抽象方法是 *foreach* ，可以遍历集合的所有元素。
    **示例:**

    ```scala
    //Scala program of abstract method

    //Creating object 
    object CS 
    {
        //Main method
        def main(args: Array[String]) 
        {
            //Creating an Array of elements
            val x = Array("GEEKS", "FOR", "GEEKS")

            //Calling foreach method
            x.foreach { E =>
            val y = E.toLowerCase

            //Display strings
            println(y)
            }
        }
    }
    ```

    **输出:**

```scala
geeks
for
geeks

```