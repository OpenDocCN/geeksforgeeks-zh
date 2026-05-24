# 刻度|弦上下文

> 哎哎哎:# t0]https://www . geeksforgeeks . org/scale-string context/

**字符串上下文**是一个在[字符串插值](https://www.geeksforgeeks.org/scala-string-interpolation/)中使用的类，它允许最终用户在处理后的字符串文本中插入变量引用，而无需任何中介。默认情况下，这个类提供 raw、s 和 f 方法作为插值器。这里的线性超类型是 *Serializable* 、 *java.io.Serializable* 、 *Product* 、*等于*、 *AnyRef* 和 *Any* 。

*   An example of Using the available s-method as interpolator.
    **Example :**

    ## 斯卡拉

    ```scala
    // Scala program of the 
    // StringContext 

    // Creating object
    object Main 
    { 

        // Main method 
        def main(args: Array[String]) 
        { 

            // Assigning values
            val name = "GeeksforGeeks"
            val articles = 32

            // Applying StringContext with
            // s-method
            val result = StringContext("I have written ", 
                        " articles on ", ".").s(articles, name)

            // Displays output
            println(result)

        }
    }
    ```

    **Output :**

    ```scala
    I have written 32 articles on GeeksforGeeks.

    ```

    在这里，StringContext.s 方法用于提取常量部分，翻译包含的转义序列，并将它们与所述表达式参数的值相加。
    这里的输出返回如下:

    ```scala
    "I have written " + (articles) + " articles on " + (name) + "."
    ```

    其中，变量*文章*和*名称*由它们的值代替。

*   **Creating our own interpolator :** In order to supply our own String interpolator, We need to produce an implicit class that will attach a method to the StringContext class.
    **Example :**

    ## 斯卡拉

    ```scala
    // Scala program of StringContext 
    // for creating our own string
    // interpolator

    // Creating object
    object Main 
    { 

    // Main method 
    def main(args: Array[String]) 
    { 
        // Using implicit class with 
        // StringContext
        implicit class Reverse (val x : StringContext) 
        {

            // Defining a method
            def revrs (args : Any*) : String =
            {

                // Applying s-method
                val result = x.s(args : _*)

                // Applying reverse method
                result.reverse
            }
        }

        // Assigning values
        val value = "GeeksforGeeks"

        // Displays reverse of the
        // stated string
        println (revrs"$value")
    }
    } 
    ```

    **Output :**

    ```scala
    skeeGrofskeeG

    ```

    这里，定义的方法 *revrs* 将其每个参数传递给 s 方法，然后打印所述字符串的反串。
    **注意:** *反转*是这里为了反转给定字符串而使用的功能。