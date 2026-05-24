# c++ 中构造函数和析构函数的区别

> 原文:[https://www . geesforgeks . org/c 中构造函数和析构函数的区别/](https://www.geeksforgeeks.org/difference-between-constructor-and-destructor-in-c/)

[**构造函数**](https://www.geeksforgeeks.org/constructors-c/) **:**
构造函数是与类名同名的类的成员函数。它有助于初始化类的对象。它可以接受这些论点，也可以不接受。它用于将内存分配给类的对象。每当创建类的实例时都会调用它。它可以用参数手动定义，也可以不用参数。类中可以有很多构造函数。它可以重载，但不能被继承或虚拟化。有一个复制构造函数的概念，用于从另一个对象初始化一个对象。

**语法:**

```cpp
  ClassName()
   {
     //Constructor's Body 
   } 
```

[**【析构函数】**](https://www.geeksforgeeks.org/destructors-c/)【T4:
与构造函数一样，析构函数也是类的成员函数，该类的名称与前面带有颚化符(~)运算符的类名相同。它有助于释放对象的内存。当类的对象被释放或删除时调用它。在一个类中，总是有一个没有任何参数的析构函数，所以它不能被重载。它总是以构造函数的相反顺序调用。如果一个类被另一个类继承，并且两个类都有析构函数，那么首先调用子类的析构函数，然后调用父类或基类的析构函数。

**语法:**

```cpp
  ~ClassName()
   { 
   }
```

注意:如果我们没有为类内部的成员指定任何访问修饰符，那么默认情况下，成员的访问修饰符将是私有的。

**构造函数和析构函数的示例/实现:**

```cpp
class Z
{
public:
    // constructor
    Z()
    {
        cout<<"Constructor called"<<endl;
    }

    // destructor
    ~Z()
    {
        cout<<"Destructor called"<<endl;
    }
};

int main()
{
    Z z1;   // Constructor Called
    int a = 1;
    if(a==1)
    {
        Z z2;  // Constructor Called
    }  // Destructor Called for z2
} //  Destructor called for z1 
```

**输出:**

```cpp
Constructor called
Constructor called
Destructor called
Destructor called 
```

**c++ 中构造函数和析构函数的区别:**

<figure class="table">

| s。不 | Constructor | destructor |
| --- | --- | --- |
| 1。 | Constructors help initialize objects of the class. | And destructors are used to destroy instances. |
| 2。 | Declared as **class name (parameters, if any) {constructor body}** . | And declared as **~ class name (no parameter) {}** . |
| 3。 | Constructors may or may not accept parameters. | Although there can be no argument. |
| 4。 | The constructor is called when an instance or object of the class is created. | Called when the object of the class is released or deleted. |
| 5。 | Constructors are used to allocate memory for instances or objects. | When it is used to free the memory of an object of a class. |
| 6。 | Constructors can be overloaded. | While it can't be overloaded. |
| 7。 | The name of the constructor is the same as the class name. | Here, its name is the same as the class name preceded by the tile (~) operator. |
| 8。 | There can be multiple constructors in a class. | There is always a destructor in a class. |
| 9。 | There is a concept of copy constructor, which is used to initialize an object from another object. | Although there is no concept of copy constructor here. |

</figure>