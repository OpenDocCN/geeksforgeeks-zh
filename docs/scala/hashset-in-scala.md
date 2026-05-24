# 比例哈希集

> 原文:[https://www.geeksforgeeks.org/hashset-in-scala/](https://www.geeksforgeeks.org/hashset-in-scala/)

**HashSet** 为封存类。它扩展了不可变集和抽象集的特征。哈希代码用于存储元素。它既不排序元素，也不保持插入顺序。由 HashSet 类实现的 Set 接口，由哈希表支持。在 Scala 中，集合语义的一个具体实现被称为 HashSet。
**语法:**

```scala
var HashsetName = HashSet(element1, element2, element3, ....)  
```

#### 使用哈希集执行操作

*   **Initialize a HashSet :** Below is the example to create or initialize HashSet.
    **Example :**

    ```scala
    // Scala program of Initializing HashSet
    import scala.collection.immutable.HashSet

    // Creating object
    object GFG
    { 
        // Main method
        def main(args:Array[String])
        { 
            println("Initialize a HashSet")

            // Creating HashSet
            val hashSet: HashSet[String] = HashSet("Geeks",
                                        "GeeksForGeeks", "Author")
            println(s"Elements are = $hashSet")
        }
    } 
    ```

    **输出:**

    ```scala
    Initialize a HashSet
    Elements are = Set(Geeks, Author, GeeksForGeeks)
    ```

*   **Check specific elements in HashSet :**
    **Example :**

    ```scala
    // Scala program of Check specific elements in HashSet
    import scala.collection.immutable.HashSet

    // Creating object
    object GFG
    { 
        // Main method
        def main(args:Array[String])
        { 
            println("Initialize a HashSet")

            // Creating HashSet
            val hashSet: HashSet[String] = HashSet("Geeks",
                                    "GeeksForGeeks", "Author")
            println(s"Elements are = $hashSet")

            // Checking
            println(s"Element Geeks = ${hashSet("Geeks")}")
            println(s"Element Student = ${hashSet("Student")}")
        }
    } 
    ```

    **输出:**

    ```scala
    Initialize a HashSet
    Elements are = Set(Geeks, Author, GeeksForGeeks)
    Element Geeks = true
    Element Student = false

    ```

*   **Adding an elements in HashSet :** We can add an element in HashSet by using + sign. below is the example of adding an element in HashSet.
    **Example :**

    ```scala
    // Scala program of adding an element in HashSet
    import scala.collection.immutable.HashSet

    // Creating object
    object GFG
    { 
        // Main method
        def main(args:Array[String])
        { 
            println("Initialize a HashSet")

            // Creating HashSet
            val hs: HashSet[String] = HashSet("Geeks",
                                "GeeksForGeeks", "Author")
            println(s"Elements are = $hs")

            // Adding an element in HashSet
            val hs1: HashSet[String] = hs + "GeeksClasses"
            println(s"Adding elements to HashSet = $hs1")
        }
    }
    ```

    **输出:**

    ```scala
    Initialize a HashSet
    Elements are = Set(Geeks, Author, GeeksForGeeks)
    Adding elements to HashSet = Set(GeeksClasses, Geeks, Author, GeeksForGeeks)

    ```

*   **Adding more than one element in HashSet :** We can add more than one element in HashSet by using ++ sign. below is the example of adding more than one elements in HashSet.
    **Example :**

    ```scala
    // Scala program of adding more elements in HashSet
    import scala.collection.immutable.HashSet

    // Creating object
    object GFG
    { 
        // Main method
        def main(args:Array[String])
        { 
            println("Initialize a HashSet")

            // Creating HashSet
            val hs: HashSet[String] = HashSet("Geeks",
                                    "GeeksForGeeks", "Author")
            println(s"Elements are = $hs")

            // Adding elements in HashSet
            val hs1: HashSet[String] = hs ++ HashSet[String]("Java", "Scala")
            println(s"Add more than one HashSets = $hs1")
        }
    }
    ```

    **输出:**

    ```scala
    Initialize a HashSet
    Elements are = Set(Geeks, Author, GeeksForGeeks)
    Add more than one HashSets = Set(Scala, Geeks, Author, Java, GeeksForGeeks)

    ```

*   **Remove element in HashSet :** We can remove an element in HashSet by using – sign. below is the example of removing an element in HashSet.
    **Example :**

    ```scala
    // Scala program of removing element in HashSet
    import scala.collection.immutable.HashSet

    // Creating object
    object GFG
    { 
        // Main method
        def main(args:Array[String])
        { 
            println("Initialize a HashSet")

            // Creating HashSet
            val hs: HashSet[String] = HashSet("Geeks",
                                    "GeeksForGeeks", "Author")
            println(s"Elements are = $hs")

            // removing elements in HashSet
            val hs1: HashSet[String] = hs - "Geeks"
            println(s"remove element from hashset = $hs1")
        }
    }
    ```

    **输出:**

    ```scala
    Initialize a HashSet
    Elements are = Set(Geeks, Author, GeeksForGeeks)
    remove element from hashset = Set(Author, GeeksForGeeks)
    ```

*   **Find the intersection between two HashSets :** We can find intersection between two HashSets by using & sign. below is the example of finding intersection between two HashSets.
    **Example :**

    ```scala
    // Scala program of finding the intersection between two HashSets
    import scala.collection.immutable.HashSet

    // Creating object
    object GFG
    { 
        // Main method
        def main(args:Array[String])
        { 
            println("Initialize two HashSets")

            // Creating two HashSet
            val hs: HashSet[String] = HashSet("Geeks",
                                "GeeksForGeeks", "Author")
            println(s"Elements of hashset1 are = $hs")

            val hs1: HashSet[String] = HashSet("Java", 
                                        "Geeks", "Scala")
            println(s"Elements of hashset2 are = $hs1")

            // finding the intersection between two HashSets
            println(s"Intersection of hashSet1 and hashSet2 = ${hs & hs1}")
        }
    }
    ```

    **输出:**

    ```scala
    Initialize two HashSets
    Elements of hashset1  are = Set(Geeks, Author, GeeksForGeeks)
    Elements of hashset2 are = Set(Scala, Geeks, Java)
    Intersection of hashSet1 and hashSet2 = Set(Geeks)

    ```

*   **Initializing an empty HashSet :**
    **Example :**

    ```scala
    // Scala program of  Initializing an empty HashSet
    import scala.collection.immutable.HashSet

    // Creating object
    object GFG
    { 
        // Main method
        def main(args:Array[String])
        { 
            // Initializing an empty HashSet
            val emptyHashSet: HashSet[String] = HashSet.empty[String]
            println(s"Empty HashSet = $emptyHashSet")
        }
    }
    ```

    **输出:**

    ```scala
    Empty HashSet = Set()
    ```