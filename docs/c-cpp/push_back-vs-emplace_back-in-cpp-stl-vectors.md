# c++ STL 向量中的推回()与定位回()

> 原文:[https://www . geesforgeks . org/push _ back-vs-retain _ back-in-CPP-STL-vectors/](https://www.geeksforgeeks.org/push_back-vs-emplace_back-in-cpp-stl-vectors/)

在 [C++ ](https://www.geeksforgeeks.org/c-plus-plus/) 、[向量](https://www.geeksforgeeks.org/vector-in-cpp-stl/)是[动态数组](https://www.geeksforgeeks.org/dynamically-allocate-2d-array-c/)，可以增长或收缩，它们的存储由[容器](https://www.geeksforgeeks.org/containers-cpp-stl/)本身处理。有两种方式[在向量](https://www.geeksforgeeks.org/vector-insert-function-in-c-stl/)中插入元素。分别是 [**推 _ 回()**](https://www.geeksforgeeks.org/vectorpush_back-vectorpop_back-c-stl/) 和 [**侵位 _ 回()**](https://www.geeksforgeeks.org/vectoremplace_back-c-stl/) 。在本文中，我们将讨论它们之间的区别。

### [**<u>推 _ 回()</u>**](https://www.geeksforgeeks.org/vectorpush_back-vectorpop_back-c-stl/) :

此方法用于从容器的末尾插入向量中的元素。由于向量的[大小的灵活性是动态的，所以在插入任何新元素后，容器的大小也增加了 1。](https://www.geeksforgeeks.org/vectorempty-vectorsize-c-stl/)

**程序 1:**

## c++

```cpp
// C++ program to demonstrate the
// push_back() method

#include <iostream>
#include <vector>

using namespace std;

// Class
class GFG {

public:
    float x, y;

    // Parameterized Constructor
    GFG(float x, float y)
        : x(x), y(y)
    {
    }

    // Copy Constructor
    GFG(const GFG& GFG)
        : x(GFG.x), y(GFG.y)
    {
        cout << "Copied" << endl;
    }
};

// Driver Code
int main()
{
    // Vector of object of GFG class
    // is created
    vector<GFG> vertices;

    // Inserting elements in the object
    // created using push_back() method

    // Custom input entries
    vertices.push_back(GFG(1, 2));
    cout << endl;

    vertices.push_back(GFG(4, 5));
    cout << endl;

    vertices.push_back(GFG(7, 8));
    cout << endl;

    return 0;
}
```

**输出:**

```cpp
Copied

Copied
Copied

Copied
Copied
Copied
```