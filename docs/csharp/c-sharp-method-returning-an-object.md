# C# |返回对象的方法

> 原文:[https://www . geeksforgeeks . org/c-sharp-method-returning-a-object/](https://www.geeksforgeeks.org/c-sharp-method-returning-an-object/)

在 C# 中，方法可以返回任何类型的数据，包括对象。换句话说，允许方法返回对象而没有任何编译时错误。

**例 1:**

```cs
// C# program to illustrate the concept
// of the method returning an object
using System;

class Example {

    // Private data member
    private string str;

    // Method to set the value of str
    public void setdata(string s)
    {
        str = s;
    }

    // Method to display the value of str
    public void Display()
    {
        Console.WriteLine("String is: " + str);
    }

    // Method that return object
    public Example Astr(Example ex)
    {

        // Creating object of Example
        Example obj = new Example();

        // Adding the value of passed 
        // an object in the current object
        // and adding the sum in another object
        obj.str = str + ex.str;

        // Returning the object
        return obj;
    }
}

// Driver Class
class GFG {

    // Main method
    static void Main()
    {

        // Declaring objects of Example
        Example o1 = new Example();
        Example o2 = new Example();

        // Initialize the values to the objects
        o1.setdata("Geeks");
        o2.setdata("forGeeks");

        // Adding value of both objects
        // and the result will be
        // assigned into third object
        Example o3 = o1.Astr(o2);

        // Display the data
        o1.Display();
        o2.Display();
        o3.Display();
    }
}
```

**输出:**

```cs
String is: Geeks
String is: forGeeks
String is: GeeksforGeeks

```

**说明:**在上例中，我们有一个类名为*例*。*示例*类包含 *setdata()* 方法，用于设置 *str* 的值， *Display()* 方法用于显示 *str* 的值， *Astr()* 用于将当前对象中传递的对象的值相加，并将另一个对象中的和相加。在 Main 方法中，创建了*示例*类的三个对象 *o1* 、 *o2* 和 *o3* 。在本陈述中，*示例 o3 = o1。astr(O2)；*将 *o1* 和 *o2* 对象的值相加，结果赋入 *o3* 对象。

**例 2:**

```cs
// C# program to illustrate the 
// concept that how method returns 
// an object
using System;

class Triangle {

    // Data member of class
    int Base;
    int Height;

    // Constructor of class
    public Triangle(int b, int h)
    {
        Base = b;
        Height = h;
    }

    // Method return area of triangle
    public int Area()
    {
        return ((Base * Height) / 2);
    }

    // Method display the dimension of triangle
    public void Display()
    {
        Console.WriteLine("\nBase of the triangle is: " 
              + Base + "\nHeight of the triangle is:  " 
                                             + Height);
    }

    public Triangle newdimension(int d)
    {
        return new Triangle(Base * d, Height * d);
    }
}

class GFG {

    // Main method
    public static void Main()
    {

        // Creating and initializing object
        Triangle t1 = new Triangle(2, 8);

        // Display the dimensions and area of triangle
        Console.Write("Dimensions of Triangle is: ");
        t1.Display();
        Console.Write("Area of Triangle is: {0}", t1.Area());

        Console.WriteLine();
        Console.WriteLine();

        Triangle t2 = t1.newdimension(2);

        Console.Write("New Dimensions of Triangle is: ");
        t2.Display();
        Console.Write("New area of Triangle is: {0}", t2.Area());
    }
}
```

**输出:**

```cs
Dimensions of Triangle is: 
Base of the triangle is: 2
Height of the triangle is:  8
Area of Triangle is: 8

New Dimensions of Triangle is: 
Base of the triangle is: 4
Height of the triangle is:  16
New area of Triangle is: 32

```

**说明:**在上例中，我们有一个类被命名为*三角*。三角形类包含构造函数*三角形()*，方法*面积()*求三角形面积，方法*显示()*显示三角形尺寸，方法 *newdimension()* 提供三角形新尺寸。维度的值由对象返回。现在在 Main 方法中有两个对象名为 *t1* 和 *t2* 。在本陈述中*三角形 T2 = t1 . new dimension(2)；*，将上一个维度，即三角形的 2 和 8 放大 2，结果赋给 *t2* 对象。