# c# 中的自定义属性

> 原文:[https://www.geeksforgeeks.org/custom-attributes-in-c-sharp/](https://www.geeksforgeeks.org/custom-attributes-in-c-sharp/)

[属性](https://www.geeksforgeeks.org/attributes-in-c-sharp/)是元数据扩展，在运行时向编译器提供关于程序代码中元素的附加信息。属性用于强加条件或提高一段代码的效率。C# 中存在内置属性，但程序员可以创建自己的属性，这种属性称为**自定义属性**。要创建自定义属性，我们必须构建从*系统派生的类。属性*类。

### 创建自定义属性的步骤

**1。使用属性属性:**这个标签定义了我们正在构建的属性。它提供诸如属性目标是什么、它是否可以被继承或者这个属性的多个实例是否可以存在等信息。属性属性有**三个主要成员**，如下所示:

1.  **属性目标。所有**指定属性可以应用于程序的所有部分，而*属性。类*表示它可以应用于类和*属性目标。方法*来一个方法。

    ```cs
    [AttributeUsageAttribute( AttributeTargets.All )]

    ```

2.  继承成员指示属性是否可以继承。它采用布尔值(真/假)。如果未指定，则默认为真。

    ```cs
    [AttributeUsage(AttributeTargets.All, Inherited = false)]

    ```

3.  AllowMultiple 成员告诉我们该属性是否可以存在多个实例。它还需要一个布尔值。默认为假。

    ```cs
    [AttributeUsage(AttributeTargets.Method, AllowMultiple = true)]

    ```

    **2。定义属性类:**它的定义方式与普通类相同，类名通常以“属性”结尾。这个类必须直接或间接继承*系统。属性*类。

    ```cs
    [AttributeUsage(AttributeTargets.All, Inherited = true, AllowMultiple = false)]
    public class MyAttribute : Attribute
    {
        //Class Members
    }

    ```

    **3。定义构造函数和属性:**构造函数用于设置属性类的值，非常像典型的类。构造函数重载可用于处理不同的赋值，同时激发属性类对象。

    ```cs
    public MyAttribute(dataType value)
    {
        this.value = value;
    }

    ```

    **注意:**自定义属性也可以为其成员设置 get 和 set 等属性。

    ```cs
    public dataType MyProperty
    {
        get {return this.value;}
        set {this.value = newValue;}
    }

    ```

    **示例 1:** 下面给出的代码显示了一个名为 MyAttribute 的自定义属性的示例，它有两个私有成员，即名称和操作。“名称”用于定义属性可能应用到的任何程序元素的名称。“动作”描述了元素应该做什么。这里的属性应用于学生类的方法。

    ```cs
    // C# program to illustrate the 
    // use of custom attributes
    using System;

    // Creating Custom attribute MyAttribute

    [AttributeUsage(AttributeTargets.All)] public class MyAttribute : Attribute {

        // Provides name of the member
        private string name;

        // Provides description of the member
        private string action;

        // Constructor
        public MyAttribute(string name, string action)
        {
            this.name = name;
            this.action = action;
        }

        // property to get name
        public string Name
        {
            get { return name; }
        }

        // property to get description
        public string Action
        {
            get { return action; }
        }
    }

    class Student {

        // Private fields of class Student
        private int rollNo;
        private string stuName;
        private double marks;

        // The attribute MyAttribute is applied 
        // to methods of class Student
        // Providing details of their utility
        [MyAttribute("Modifier", "Assigns the Student Details")] public void setDetails(int r, 
                                                                          string sn, double m)
        {
            rollNo = r;
            stuName = sn;
            marks = m;
        }

        [MyAttribute("Accessor", "Returns Value of rollNo")] public int getRollNo()
        {
            return rollNo;
        }

        [MyAttribute("Accessor", "Returns Value of stuName")] public string getStuName()
        {
            return stuName;
        }

        [MyAttribute("Accessor", "Returns Value of marks")] public double getMarks()
        {
            return marks;
        }
    }

    class TestAttributes {

        // Main Method
        static void Main(string[] args)
        {
            Student s = new Student();
            s.setDetails(1, "Taylor", 92.5);

            Console.WriteLine("Student Details");
            Console.WriteLine("Roll Number : " + s.getRollNo());
            Console.WriteLine("Name : " + s.getStuName());
            Console.WriteLine("Marks : " + s.getMarks());
        }
    }
    ```

    **Output:**

    ```cs
    Student Details
    Roll Number : 1
    Name : Taylor
    Marks : 92.5

    ```

    **示例 2:** 在本例中，我们可以显示我们创建的自定义属性的内容。这里的 NewAttribute 是一个自定义属性，有两个字段，即标题和描述。图块存储标题，描述存储应用新属性的方法的功能。要将自定义属性应用于程序的任何部分，必须在定义之前调用其构造函数。NewAttribute 还包括一个参数化构造函数和一个显示属性内容的方法。主要是使用类名调用 AttributeDisplay 方法，因为它是一个静态方法，它显示关于应用了该属性的类的方法的信息。

    ```cs
    // C# program to display the custom attributes
    using System;
    using System.Reflection;
    using System.Collections.Generic;

    // Defining a Custom attribute class
    class NewAttribute : Attribute {

        // Private fields
        private string title;
        private string description;

        // Parameterised Constructor
        public NewAttribute(string t, string d)
        {
            title = t;
            description = d;
        }

        // Method to show the Fields 
        // of the NewAttribute
        // using reflection
        public static void AttributeDisplay(Type classType)
        {
            Console.WriteLine("Methods of class {0}", classType.Name);

            // Array to store all methods of a class
            // to which the attribute may be applied

            MethodInfo[] methods = classType.GetMethods();

            // for loop to read through all methods

            for (int i = 0; i < methods.GetLength(0); i++) {

                // Creating object array to receive 
                // method attributes returned
                // by the GetCustomAttributes method

                object[] attributesArray = methods[i].GetCustomAttributes(true);

                // foreach loop to read through 
                // all attributes of the method
                foreach(Attribute item in attributesArray)
                {
                    if (item is NewAttribute) {

                        // Display the fields of the NewAttribute
                        NewAttribute attributeObject = (NewAttribute)item;
                        Console.WriteLine("{0} - {1}, {2} ", methods[i].Name,
                         attributeObject.title, attributeObject.description);
                    }
                }
            }
        }
    }

    // Class Employer
    class Employer {

        // Fields of Employer
        int id;
        string name;

        // Constructor
        public Employer(int i, string n)
        {
            id = i;
            name = n;
        }

        // Applying the custom attribute 
        // NewAttribute to the getId method
        [NewAttribute("Accessor", "Gives value of Employer Id")] public int getId()
        {
            return id;
        }

        // Applying the custom attribute 
        // NewAttribute to the getName method
        [NewAttribute("Accessor", "Gives value of Employer Name")] public string getName()
        {
            return name;
        }
    }

    // Class Employee
    class Employee {

        // Fields of Employee
        int id;
        string name;

        public Employee(int i, string n)
        {
            id = i;
            name = n;
        }

        // Applying the custom 
        // attribute NewAttribute
        // to the getId method
        [NewAttribute("Accessor", "Gives value of Employee Id")] public int getId()
        {
            return id;
        }

        // Applying the custom attribute 
        // NewAttribute to the getName method
        [NewAttribute("Accessor", "Gives value of Employee Name")] public string getName()
        {
            return name;
        }
    }

    class Program {

        // Main Method
        static void Main(string[] args)
        {

            // Calling the AttributeDisplay
            // method using the class name
            // since it is a static method
            NewAttribute.AttributeDisplay(typeof(Employer));

            Console.WriteLine();

            NewAttribute.AttributeDisplay(typeof(Employee));
        }
    }
    ```

    **Output:**

    ```cs
    Methods of class Employer
    getId - Accessor, Gives value of Employer Id 
    getName - Accessor, Gives value of Employer Name 

    Methods of class Employee
    getId - Accessor, Gives value of Employee Id 
    getName - Accessor, Gives value of Employee Name

    ```