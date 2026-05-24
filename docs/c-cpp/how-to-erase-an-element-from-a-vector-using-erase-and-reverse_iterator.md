# 如何使用 erase()和 reverse_iterator 从向量中擦除元素？

> 原文:[https://www . geesforgeks . org/如何使用擦除和反转迭代器从向量中擦除元素/](https://www.geeksforgeeks.org/how-to-erase-an-element-from-a-vector-using-erase-and-reverse_iterator/)

给定一个[向量](https://www.geeksforgeeks.org/vector-in-cpp-stl/)，任务是使用 [erase()](https://www.geeksforgeeks.org/vector-erase-and-clear-in-cpp/) 和 [reverse_iterator](https://www.geeksforgeeks.org/vector-rbegin-and-rend-function-in-c-stl/) 从这个向量中删除一个元素。

**示例:**

```cpp
Input: vector = {1, 4, 7, 10, 13, 16, 19}, element = 16
Output: 1 4 7 10 13 19

Input: vector = {99, 89, 79, 69, 59}, element = 89
Output: 99 79 69 59

```

**进场:**

*   获取要删除的向量和元素
*   初始化向量的反向迭代器
*   Erase the required element with the help of base() and erase()

    **使用 base():的原因:** erase()返回一个有效的迭代器到元素的新位置，该元素位于刚刚被擦除的元素之后，向前。因此，当使用反向迭代器时，我们不能使用相同的过程，因为我们希望反向而不是正向。我们也不能将反向迭代器作为参数传递给 erase()函数，否则会产生编译错误。

    reverse_iterator 只是一个迭代器适配器，它反转给定迭代器的方向。reverse_iterator 上的所有操作实际上都发生在底层迭代器上。我们可以使用 reverse_iterator::base()函数获取该迭代器。事实上，itr.base()和 itr 之间的关系是:

    ```cpp
    &*(reverse_iterator(itr))==&*(itr-1)
    ```

下面是上述方法的实现:

```cpp
// C++ program to delete an element of a vector
// using erase() and reverse iterator.

#include <iostream>
#include <vector>

using namespace std;

// Function to delete element
// 'num' from vector 'vec'
vector<int> delete_ele(vector<int> vec, int num)
{
    // initializing a reverse iterator
    vector<int>::reverse_iterator itr1;

    for (itr1 = vec.rbegin(); itr1 < vec.rend(); itr1++) {

        if (*itr1 == num) {

            // erasing element = 16
            vec.erase((itr1 + 1).base());
        }
    }

    return vec;
}

// Driver code
int main()
{
    vector<int> vec = { 1, 4, 7, 10, 13, 16, 19 };

    // we want to delete element = 16
    int num = 16;

    vector<int>::iterator itr1;

    cout << "Vector originally: \n";
    for (itr1 = vec.begin(); itr1 < vec.end(); itr1++) {

        // printing the original elements of vector
        cout << *itr1 << " ";
    }

    cout << "\n\nElement to be deleted: "
         << num << "\n\n";

    // reinitializing vector 'vec'
    // after deleting 'num'
    // from the vector
    // and keeping other remaining
    // elements as they are
    vec = delete_ele(vec, num);

    vector<int>::iterator itr2;

    cout << "Vector after deletion: \n";
    for (itr2 = vec.begin(); itr2 < vec.end(); itr2++) {

        // printing the remaining elements of vector
        cout << *itr2 << " ";
    }

    return 0;
}
// This code is contributed by supratik_mitra
```

**Output:**

```cpp
Vector originally: 
1 4 7 10 13 16 19 

Element to be deleted: 16

Vector after deletion: 
1 4 7 10 13 19

```