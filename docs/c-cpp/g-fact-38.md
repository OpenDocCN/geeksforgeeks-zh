# 分配操作员中的自我分配检查

> 原文:[https://www.geeksforgeeks.org/g-fact-38/](https://www.geeksforgeeks.org/g-fact-38/)

在 C++ 中，赋值运算符应该重载自赋值检查。

例如，考虑下面的类*数组*和重载赋值运算符函数，无需自我赋值检查。

```cpp
// A sample class
class Array {
 private:
   int *ptr;
   int size;
 public:
   Array& operator = (const Array &rhs);
   // constructors and other functions of class........
};

// Overloaded assignment operator for class Array (without self 
// assignment check)
Array& Array::operator = (const Array &rhs)
{
  // Deallocate old memory
  delete [] ptr;

  // allocate new space
  ptr = new int [rhs.size];

  // copy values
  size = rhs.size;
  for(int i = 0; i < size; i++)
    ptr[i] = rhs.ptr[i];

  return *this; 
}
```

*如果我们有一个对象，比如说数组类型的 *a1* ，如果我们有一条类似 *a1 = a1* 的线，程序会导致不可预测的行为，因为在上面的代码中没有自我赋值检查。为了避免上述问题，重载赋值运算符时必须进行自我赋值检查。例如，下面的代码执行自我赋值检查。*

```cpp
// Overloaded assignment operator for class Array (with self 
// assignment check)
Array& Array::operator = (const Array &rhs)
{
  /* SELF ASSIGNMENT CHECK */
  if(this != &rhs)
  {
    // Deallocate old memory
    delete [] ptr;

    // allocate new space
    ptr = new int [rhs.size];

    // copy values
    size = rhs.size;
    for(int i = 0; i < size; i++)
      ptr[i] = rhs.ptr[i];    
  }  

  return *this; 
}
```

参考文献:
[http://www . cs . Caltech . edu/courses/cs11/material/CPP/donnie/CPP-ops . html](http://www.cs.caltech.edu/courses/cs11/material/cpp/donnie/cpp-ops.html)

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论