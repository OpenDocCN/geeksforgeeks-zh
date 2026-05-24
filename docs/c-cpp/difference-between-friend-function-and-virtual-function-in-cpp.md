# c++ 中朋友函数和虚函数的区别

> 原文:[https://www . geesforgeks . org/friend-function-and-virtual-function-in-CPP/](https://www.geeksforgeeks.org/difference-between-friend-function-and-virtual-function-in-cpp/)

一个[朋友类](https://www.geeksforgeeks.org/friend-class-function-cpp/)可以访问它被声明为朋友的其他类的私有和受保护成员。允许特定类访问其他类的私有成员有时很有用。很可能，[友元函数](https://www.geeksforgeeks.org/friend-class-function-cpp/)是一个声明在类范围之外的函数。这个函数可以像普通函数一样调用，并包含对象作为参数。主要用于 I/O 重载<<>>，一般可以访问其为好友的类的任意成员。

**插图:**

```cpp
class GFG  
{ 
 private: 
 {  
 Public: 
 {  
 friend void check();  
 }

void check();  
```

现在进入第二个函数是一个虚函数。所以一个[虚函数](https://www.geeksforgeeks.org/virtual-function-cpp/)基本上是一个在基类中声明的类的成员函数。在这种情况下，使用一个虚拟关键字来使基类的成员函数虚拟化。它还支持编译时和运行时的多态性。它还允许派生类简单地替换基类提供或给定的实现。

**插图:**

```cpp
class GFG  
{  
Public:  
          Virtual return_type function_name(arguments)  
         {  
         …..  
         }  
}:  
   class A  
  {  
```

到目前为止，我们已经清楚地讨论了朋友功能和虚拟功能，现在让我们看看它们之间的主要区别，甚至把握好它。

<figure class="table">

| 

Friend Function

 | 

虚函数

 |
| --- | --- |
| Generally, a class that can be accessed privately represents a non-member function. | Is a base class function that can be overridden by derived classes. |
| Used to access private and protected classes. | Used to ensure that no matter what expression is used as a function class, the correct function is called to an object. |
| Outside the scope of the declaration class. It is declared with the keyword " *friend"* . | Declared inside a base class, usually redefined by a derived class. Declare with the " *virtual* keyword. |
| Generally used to give non-member functions access to hidden members of a class. | Generally, it is required to tell the compiler to perform dynamic linkage of late binding on functions. |
| They support sharing the information of previously hidden classes, provide the method of escaping data hiding restrictions of C++, and access members without inheriting classes. | They support object-oriented programming, ensure that functions are covered, and can be friends of other functions. |
| It can access the private members of the class, even if it is not a member of the class. | It is used for polymorphism to work. |

</figure>