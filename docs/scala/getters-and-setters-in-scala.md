# Scala 中的吸气剂和沉降剂

> 原文:[https://www.geeksforgeeks.org/getters-and-setters-in-scala/](https://www.geeksforgeeks.org/getters-and-setters-in-scala/)

Scala 中的 **Getter** 和 **Setter** 是分别帮助我们获取变量的值和实例化类/特征的变量的方法。Scala 为 JVM 生成了一个带有私有变量字段以及 getter 和 setter 方法的类。在 Scala 中，getters 和 setters 没有被命名为 getXxx 和 setXxx，但是它们被用于相同的目的。在任何时候，我们都可以自己重新定义 getter 和 setter 方法。

#### 安装员

Setter 是一种技术，通过它我们可以设置一个类的变量值。设置类的变量很简单，可以通过两种方式完成

*   First if the members of a class are accessible from anywhere. i.e no access modifier specified.
    **Example:**

    ```scala
    // A Scala program to illustrate 
    // Setting the variable of a class

    // Name of the class is Student
    class Student 
    {
        // Class variables
        var student_name: String= " "
        var student_age: Int= 0
        var student_rollno= 0
    } 

    // Creating object
    object Main 
    {
        // Main method 
        def main(args: Array[String]) 
        {
            // Class object 
            var obj = new Student() 
            obj.student_name= "Yash"
            obj.student_age= 22
            obj.student_rollno= 59
            println("Student Name: " + obj.student_name) 
            println("Student Age: " + obj.student_age) 
            println("Student Rollno: " + obj.student_rollno) 

        } 
    }
    ```

    **输出:**

    ```scala
    Student Name: Yash
    Student Age: 22
    Student Rollno: 59
    ```

    出于安全原因，不建议这样做。因为直接访问类的成员并不是一个好的方法来初始化和改变值，因为这将允许其他人识别变量。

*   第二，如果一个类的成员被定义为私有。变量的初始化是通过使用类的对象将变量传递给该类的公共方法来完成的。
    **例:**

    ```scala
    // A Scala program to illustrate 
    // Setting the private variable of a class

    // Name of the class is Student
    class Student 
    {
        // Class variables
        var student_name: String= " "
        var student_age: Int= 0
        private var student_rollno= 0

        // Class method 
        def set_roll_no(x: Int)
        {
            student_rollno= x
        }
    } 

    // Creating object
    object GFG
    {
        // Main method 
        def main(args: Array[String]) 
        { 

            // Class object 
            var obj = new Student() 
            obj.student_name= "Yash"
            obj.student_age= 22

            //error: variable student_rollno in class 
            // Student cannot be accessed in Student
            //obj.student_rollno= 59 
            obj.set_roll_no(59)

            // Directly getting the value of variable
            println("Student Name: "+ obj.student_name) 

            // Directly getting the value of variable
            println("Student Age: "+obj.student_age) 

            // Through method calling
            println("Student Rollno: "+obj.student_rollno) 

        } 
    }
    ```

#### 吸气剂

Getters 是一种技术，通过它我们可以得到一个类的变量值。

*   直接获取全局变量的值。其中我们调用用对象指定变量的名称。
*   Getting the value of a variable through method calling using the object. This technique is good when we don’t have accessibility to class variables but methods are available public.
    **Example:**

    ```scala
    // A Scala program to illustrate 
    // Getting the value of members of a class

    // Name of the class is Student
    class Student 
    {
        // Class variables
        var student_name: String= " "
        var student_age: Int= 0

        // Getter
        private var student_rollno= 0

        // Class method 
        def set_rollno(x: Int){
            student_rollno= x
        }
        def get_rollno(): Int ={
            return student_rollno
        }

    } 

    // Creating object
    object Main 
    {
        // Main method 
        def main(args: Array[String]) 
        { 

            // Class object 
            var obj = new Student() 
            obj.student_name= "Yash"
            obj.student_age= 22
            obj.set_rollno(59)

            // Directly getting the value of variable
            println("Student Name: " + obj.student_name) 

            // Directly getting the value of variable
            println("Student Age: " + obj.student_age) 

            // Through method calling
            println("Student Rollno: " + obj.get_rollno) 
        } 
    }
    ```

    **输出:**

    ```scala
    Student Name: Yash
    Student Age: 22
    Student Rollno: 59

    ```