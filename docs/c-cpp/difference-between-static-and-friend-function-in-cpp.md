# c++ 中静态函数和友元函数的区别

> 原文:[https://www . geesforgeks . org/static-and-friend-function-in-CPP/](https://www.geeksforgeeks.org/difference-between-static-and-friend-function-in-cpp/)

[**静态函数**](https://www.geeksforgeeks.org/what-are-static-functions-in-c/) **:** 它基本上是一个[成员函数](https://www.geeksforgeeks.org/const-member-functions-c/)，即使类的对象没有初始化也可以调用。这些函数与任何对象相关联，用于在类的不同对象之间维护类成员函数的单一副本。这个函数用 static 关键字表示。

[**好友功能**](https://www.geeksforgeeks.org/friend-class-function-cpp/) **:** 基本上是访问类的非公开成员特别需要的功能。它有权访问该类的所有私有和受保护成员。它通常提供一些通常不被类使用的附加功能，并允许共享由非成员函数提供的类信息。

**<u>静态函数与友元函数</u>:**

<figure class="table">

| 

**静态函数**

 | 

**友元函数**

 |
| --- | --- |
| It is a member function of a class, even if the object of the class is not initialized. | Is a function declared outside the class scope. |
| In this case, it can't access any variables of its class except static variables. | In this case, it can access the private and public members of the class. |
| By placing a static keyword in front of the function name. | It is indicated by placing the friend keyword in front of the function name. |
| This function is generally used to make function members independent of any specific object of the class. | This function is generally used to access non-public members of the class. |
| These functions are usually used when you want a function that is the same for every instance of a class. | These functions are usually used to share information of previously hidden classes. |
| It can access the members of a class. | Members of several classes can be accessed. |
| Can not be used when overload operation is required. | It can be used when overloading operations are needed, because overloading operators can only be done by friends or non-static members. |
| You can also use a function if it does not need to read, change or modify the state of a specific instance of a class, or if you need to use a function pointer to a member function of a class. | You can also use it when you want to create code that is not and should not be a member of this class. |
| This function can be hidden behind privileges. | This function cannot be hidden, and anyone can call the friend function. |
| It is associated with a class, not an object. | Declared in a class but not belonging to a class. |

</figure>