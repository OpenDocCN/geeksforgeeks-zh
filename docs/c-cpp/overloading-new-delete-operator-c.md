# 在 c++ 中重载 New 和 Delete 运算符

> 原文:[https://www . geesforgeks . org/overloading-new-delete-operator-c/](https://www.geeksforgeeks.org/overloading-new-delete-operator-c/)

新的和删除操作符也可以像 C++ 中的其他操作符一样重载。New 和 Delete 运算符可以全局重载，也可以针对特定的类重载。

*   如果这些操作符是使用某个类的成员函数重载的，这意味着这些操作符只是为该特定类重载**。**
*   如果重载是在类之外完成的(即它不是类的成员函数)，重载的“new”和“delete”将在您使用这些操作符的任何时候被调用(在类内或类外)。这是**全局重载**。

**重载新运算符的语法:**

```cpp
void* operator new(size_t size);
```

重载的新运算符接收 size_t 类型的大小，它指定要分配的内存字节数。重载 new 的返回类型必须是 void*。重载函数返回一个指向已分配内存块开始的指针。
**重载删除运算符的语法:**

```cpp
void operator delete(void*);
```

该函数接收到 void*类型的参数，必须将其删除。函数不应该返回任何东西。
**注意:**重载的新增和删除操作符函数默认都是**静态成员**。因此，他们无法访问**这个指针**。
**重载特定类的新建和删除运算符:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to demonstrate
// Overloading new and delete operator
// for a specific class
#include<iostream>
#include<stdlib.h>

using namespace std;
class student
{
    string name;
    int age;
public:
    student()
    {
        cout<< "Constructor is called\n" ;
    }
    student(string name, int age)
    {
        this->name = name;
        this->age = age;
    }
    void display()
    {
        cout<< "Name:" << name << endl;
        cout<< "Age:" << age << endl;
    }
    void * operator new(size_t size)
    {
        cout<< "Overloading new operator with size: " << size << endl;
        void * p = ::operator new(size);
        //void * p = malloc(size); will also work fine

        return p;
    }

    void operator delete(void * p)
    {
        cout<< "Overloading delete operator " << endl;
        free(p);
    }
};

int main()
{
    student * p = new student("Yash", 24);

    p->display();
    delete p;
}
```

```cpp
Overloading new operator with size: 16
Constructor is called
Name:Yash
Age:24
Overloading delete operator 
```

**注意:**在上面新的重载函数中，我们已经通过 new 运算符分配了动态内存，但应该是全局 new 运算符，否则会进入递归
void * p = new student()；//这将在递归中进行，因为 **new** 将一次又一次重载
void * p =::new student()；//这是正确的

**新增和删除运算符的全局重载**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to demonstrate
// Global overloading of
// new and delete operator
#include<iostream>
#include<stdlib.h>

using namespace std;
void * operator new(size_t size)
{
    cout << "New operator overloading " << endl;
    void * p = malloc(size);
    return p;
}

void operator delete(void * p)
{
    cout << "Delete operator overloading " << endl;
    free(p);
}

int main()
{
    int n = 5, i;
    int * p = new int[3];

    for (i = 0; i<n; i++)
    p[i]= i;

    cout << "Array: ";
    for(i = 0; i<n; i++)
        cout << p[i] << " ";

    cout << endl;

    delete p;
}
```

**输出:**

```cpp
New operator overloading 
Array: 0 1 2 3 4 
Delete operator overloading 
```

**注意:**在上面的代码中，在新的重载函数中，我们不能使用**:new int[5]**来分配内存，因为它将进行递归。我们只需要使用 malloc 来分配内存。

**为什么要重载新建和删除？**

1.重载的新运算符函数可以接受参数；因此，一个类可以有**多个重载的新运算符**函数。这使得程序员在定制对象的内存分配时更加灵活。例如:

## C

```cpp
void *operator new(size_t size, char c)
{
   void *ptr;
   ptr = malloc(size);
   if (ptr!=NULL)
      *ptr = c;
return ptr;
}
main()
{
   char *ch = new('#') char;
}
```

**2。注意:**代码不仅会为单个字符分配内存，还会用 **#字符**初始化分配的内存。

3.重载的新建或删除操作符也为类的对象提供**垃圾收集**。

**4。可以在重载的新运算符函数中添加异常处理例程**。

5.有时你希望操作符 new 和 delete 做一些编译器提供的版本没有提供的**定制的事情。例如，您可以编写一个自定义运算符 delete，用零覆盖解除分配的内存，以提高应用程序数据的安全性。**

6.我们可以在新函数中使用 **realloc()函数**动态重新分配内存。

7.重载的新操作符也使程序员能够从他们的程序中挤出一些额外的性能。例如，在一个类中，为了加快新节点的分配，会维护一个已删除节点的列表，以便在分配新节点时可以重用它们的内存。在这种情况下，重载的删除操作符会将节点添加到已删除节点的列表中，重载的新操作符会从该列表而不是从堆中分配内存，以加速内存分配。当删除的节点列表为空时，可以使用堆中的内存。

本文由**雅什辛拉**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。