# vector::crend()&vector::crbegin()带示例

> 哎哎哎:# t0]https://www . geeksforgeeks . org/vector nd-vector crbegin-examples/

这些函数返回有用的迭代器，以逆序(从头到尾)访问向量元素

**使用向量::crend()**

它是一个公共成员函数，返回指向第一个元素前面的元素的 const_reverse_iterator。
**返回值**

```cpp
A const_reverse_iterator to the reverse 
end of the sequence.
```

**语法:**

```cpp
const_reverse_iterator crend() const noexcept;
```

**使用向量::crbegin()**

它返回一个 const_reverse_iterator，指向容器中的最后一个元素(即它的反向开头)..
**返回值**

```cpp
A const_reverse_iterator to the reverse 
beginning of the sequence.
```

**语法:**

```cpp
const_reverse_iterator crbegin() const noexcept;
```

```cpp
// CPP program to illustrate working of crbegin() 
// crend()
#include <iostream>
#include <vector>
using namespace std;

int main ()
{
  // initializing vector with values
  vector<int> vect = {10, 20, 30, 40, 50};

  // for loop with crbegin and crend
  for (auto i = vect.crbegin(); i != vect.crend(); i++)
    cout << ' ' << *i;  //printing results

  cout << '\n';
  return 0;
}
```

**输出:**

```cpp
50 40 30 20 10

```

**应用程序**
**垛口:**
返回一个反向迭代器到反向容器最后一个元素之后的元素。它对应于非反转容器的第一个元素之前的元素。此元素充当占位符，试图访问它会导致未定义的行为
**crbegin :**
返回反向容器的第一个元素的反向迭代器。它对应于非反转容器的最后一个元素。
两者都用于**去重操作**，同时访问或修改不同的元素是安全的。
返回迭代器的复制构造或赋值也保证永远不会抛出异常。