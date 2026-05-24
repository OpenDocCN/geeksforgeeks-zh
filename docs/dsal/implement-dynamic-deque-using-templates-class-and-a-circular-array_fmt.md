# 使用模板类和循环数组

## 实现动态去重

> 原文：[https://www.geeksforgeeks.org/implement-dynamic-deque-using-templates-class-and-a-circular-array/](https://www.geeksforgeeks.org/implement-dynamic-deque-using-templates-class-and-a-circular-array/)

任务是使用模板类和循环数组实现动态双端队列，具有以下功能：

*   `front()`: 从双端队列获取前置项。
*   `back()`: 从双端队列中获取最后一项。
*   `push_back(X)`: 在双端队列结束时推入 `X`。
*   `push_front(X)`: 在双端队列开始时推入 `X`。
*   `pop_front()`: 从双端队列的开始处删除一个元素。
*   `pop_back()`: 从双端队列末尾删除一个元素。
*   `empty()`: 检查双端队列是否为空。
*   `capacity()`: 当前双端队列可以存储的最大元素数量。
*   `size()`: 双端队列中的元素数量。

下面是一步一步的图解：

*   最初，双端队列是空的。

![](img/032bae7517540691022a348529c5a88b.png)

*   在双端队列后面插入 1。

![](img/8e171adf5e5ffb3c2f62b8c635ce986b.png)

*   将元素 2、3 插入到双端队列的后面。

![](img/7a5c7c9e2a5df63017740ba9a92c9cc1.png)

*   在双端队列的前面插入 4。

![](img/5546ffe710a58346aa83a8552b40a0e9.png)

*   在双端队列后面插入 5。

![](img/5ce4f79c7fe2ba08952fcac3f473fd15.png)

*   从正面弹出 2 个元素，从背面弹出 2 个元素。

![](img/3a712c8b41d78371d3a19e66c4e8aeca.png)

*   从双端队列前面弹出 1 个元素。

![](img/81686d76c76375129caa1236c5bfc366.png)

**方法：** 想法是将每次数组容量满时使用的数组大小加倍，并将之前数组的元素复制到新数组中。按照以下步骤解决问题：

*   初始化 4 个变量 `frontIndex`、`backIndex`、`sizeVar` 和 `capacityVar`，一个数组 `arr[]` 来实现双端队列。
*   定义一个函数，比如 `capacity()` 来查找当前数组的大小，并返回变量 `capacityVar` 的值。
*   定义一个函数，比如说 `size()` 来计算元素的数量并返回变量 `sizeVar` 的值。
*   定义一个函数，说 `full()` 来查找双端队列是否已满，如果 `sizeVar` 等于 `capacityVar` 则返回 `true`。否则，返回 `false`。
*   定义一个函数，说 `empty()` 来查找双端队列是否为空，如果 `frontIndex` 和 `backIndex` 等于 `-1` 则返回 `true`。否则，返回 `false`。
*   定义一个函数，比如 `Front()` 来打印双端队列的 front 元素。如果双端队列不为空，打印 `arr[frontIndex]` 元素。
*   定义一个函数说 `Back()` 打印出双端队列的最后一个元素。如果双端队列不为空，打印 `arr[backIndex]` 元素。
*   定义一个函数，比如 `push_back(X)` 在双端队列末尾插入一个元素：
    *   如果双端队列已满，则将当前数组的大小加倍，并将前一个数组的元素复制到新数组中。
    *   如果双端队列为 `empty()`，则分配 `frontIndex = backIndex = 0`，然后将 `X` 分配给 `arr[frontIndex]` 和 `arr[backIndex]`，然后将 `sizeVar` 递增 1。
    *   否则，将 `backIndex` 更新为 `backIndex = (backIndex + 1) % capacityVar`，然后将 `X` 分配给 `arr[backIndex]` 并将 `sizeVar` 递增 1。
*   定义一个函数，比如 `push_front(X)` 在开始的地方插入一个元素：
    *   如果双端队列已满，则将当前数组的大小加倍，并将前一个数组的元素复制到新数组中。
    *   如果双端队列为 `empty()`，则分配 `frontIndex = backIndex = 0`，然后将 `X` 分配给 `arr[frontIndex]` 和 `arr[backIndex]`，然后将 `sizeVar` 递增 1。
    *   否则，将 `frontIndex` 更新为 `frontIndex = (frontIndex - 1 + capacityVar) % capacityVar`，然后将 `X` 分配给 `arr[frontIndex]` 并将 `sizeVar` 递增 1。
*   定义一个函数，比如 `pop_front()` 来删除一个元素：
    *   如果双端队列为空，打印 `"下溢"`。
    *   否则如果 `sizeVar` 等于 1，则将 `-1` 分配给 `frontIndex` 和 `backIndex`，然后将 `sizeVar` 减 1。
    *   否则，将 `frontIndex` 更新为 `frontIndex = (frontIndex + 1) % capacityVar`，并将 `sizeVar` 减 1。
*   定义一个函数，比如 `pop_back()` 来删除双端队列前面的元素：
    *   如果双端队列为空，打印 `"下溢"`。
    *   否则如果 `sizeVar` 等于 1，则将 `-1` 分配给 `frontIndex` 和 `backIndex`，然后将 `sizeVar` 减 1。
    *   否则，将 `backIndex` 更新为 `backIndex = (backIndex - 1 + capacityVar) % capacityVar`。

下面是上述方法的实现：

## C++

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;

// Class definition of the deque
template <class X>
class Deque {

private:
    // Stores the frontIndex
    int frontIndex;

    // Stores the backIndex
    int backIndex;

    // Stores the array
    X* arr;

    // Stores the size of deque
    int sizeVar;

    // Stores the size of array
    int capacityVar = 4;

public:
    // Deque class constructor
    Deque()
    {
        arr = new X[capacityVar];
        frontIndex = backIndex = -1;
        sizeVar = 0;
    }

    // Function methods
    bool empty();
    bool full();
    void push_back(X x);
    void push_front(X x);
    void pop_front();
    void pop_back();
    X front();
    X back();
    int capacity();
    int size();
};

// Function to find the capacity of the deque
template <class X>
int Deque<X>::capacity()
{
    return capacityVar;
}

// Function to find the number of elements
// present in deque
template <class X>
int Deque<X>::size() { return sizeVar; }

// Function to check if deque is empty or not
template <class X>
bool Deque<X>::empty()
{
    if (frontIndex == -1 && backIndex == -1)
        return true;
    else
        return false;
}

// Function to check if deque is full or not
template <class X>
bool Deque<X>::full()
{
    if (sizeVar == capacityVar)
        return true;
    else
        return false;
}

// Function to find the front element of the deque
template <class X>
X Deque<X>::front()
{
    // If deque is empty
    if (empty()) {
        cout << "Deque underflow" << endl;
        abort();
    }
    return arr[frontIndex];
}

// Function to find the last element of the deque
template <class X>
X Deque<X>::back()
{
    // If deque is empty
    if (empty()) {
        cout << "Deque underflow" << endl;
        abort();
    }
    return arr[backIndex];
}

// Function to insert the element
// to the back of the deque
template <class X>
void Deque<X>::push_back(X x)
{
    if (full()) {

        // If the deque is full, then
        // double the capacity
        capacityVar = capacityVar * 2;

        // Initialize new array of
        // double size
        X* temp = new X[capacityVar];

        // Copy the elements of the
        // previous array
        int i = frontIndex;
        int j = 0;
        while (i != backIndex) {
            temp[j] = arr[i];
            i = (i + 1) % sizeVar;
            j++;
        }
        temp[j] = arr[i];

        frontIndex = 0;
        backIndex = sizeVar - 1;

        // Deallocate the memory
        // of previous array
        delete[] arr;
        arr = temp;
    }

    // If size is zero
    if (empty()) {
        frontIndex = backIndex = 0;
        arr[backIndex] = x;
        sizeVar++;
        return;
    }

    // Increment back index cyclically
    backIndex = (backIndex + 1) % capacityVar;
    arr[backIndex] = x;
    sizeVar++;
    return;
}

// Function to insert the element
// to the front of the deque
template <class X>
void Deque<X>::push_front(X x)
{
    if (full()) {

        // If the deque is full, then
        // double the capacity
        capacityVar = capacityVar * 2;

        // Initialize new array of
        // double size
        X* temp = new X[capacityVar];

        // Copy the elements of the
        // previous array
        int i = frontIndex;
        int j = 0;
        while (i != backIndex) {
            temp[j] = arr[i];
            i = (i + 1) % sizeVar;
            j++;
        }
        temp[j] = arr[i];

        frontIndex = 0;
        backIndex = sizeVar - 1;

        // Deallocate the memory
        // of previous array
        delete[] arr;
        arr = temp;
    }

    // If size is zero
    if (empty()) {
        frontIndex = backIndex = 0;
        arr[backIndex] = x;
        sizeVar++;
        return;
    }

    // Decrement front index cyclically
    frontIndex
        = (frontIndex - 1 + capacityVar) % capacityVar;
    arr[frontIndex] = x;
    sizeVar++;
    return;
}

// Function to delete the element
// from the front of the deque
template <class X>
void Deque<X>::pop_front()
{
    // If deque is empty
    if (empty()) {
        cout << "Deque underflow" << endl;
        abort();
    }

    // If there is only one character
    if (frontIndex == backIndex) {

        // Mark deque as empty
        // and decrement sizeVar
        frontIndex = backIndex = -1;
        sizeVar--;
        return;
    }

    // Increment frontIndex cyclically
    frontIndex = (frontIndex + 1) % capacityVar;
    sizeVar--;
    return;
}
```

# 双端队列的 `pop_back()` 操作实现

## 函数实现

```cpp
// Function to delete the element
// from the back of the deque
template <class X>
void Deque<X>::pop_back()
{
    // If deque is empty
    if (empty()) {
        cout << "Deque underflow" << endl;
        abort();
    }

    // If there is only one character
    if (frontIndex == backIndex) {
        // Mark deque as empty
        // and decrement sizeVar
        frontIndex = backIndex = -1;
        sizeVar--;
        return;
    }

    // Decrement backIndex cyclically
    backIndex = (backIndex - 1 + capacityVar) % capacityVar;
    sizeVar--;
    return;
}
```

## 驱动代码示例

```cpp
// Driver Code
int main()
{
    // Deque initialization
    Deque<int> q;

    // Iterate range [1, 100],
    // push even numbers at the back
    // and push odd numbers at the front
    for (int i = 1; i < 10; i++)
        if (i % 2 == 0)
            q.push_back(i);
        else
            q.push_front(i);

    // Print the current capacity
    cout << "Current capacity " << q.capacity() << endl;

    // Print the current size
    cout << "Current size " << q.size() << endl;

    // Print front elements of deque
    cout << "Front element " << q.front() << endl;

    // Print last element of the deque
    cout << "Rear element " << q.back() << endl;

    cout << endl;

    cout << "Pop an element from front" << endl;

    // Pop an element from the front of deque
    q.pop_front();

    cout << "Pop an element from back" << endl;

    // Pop an element from the back of deque
    q.pop_back();

    cout << endl;

    // Print the current capacity
    cout << "Current capacity " << q.capacity() << endl;

    // Print current size
    cout << "Current size " << q.size() << endl;

    // Print front elements of deque
    cout << "Front element " << q.front() << endl;

    // Print last element of the deque
    cout << "Rear element " << q.back() << endl;

    return 0;
}
```

### 输出结果

```
Current capacity 16
Current size 9
Front element 9
Rear element 8

Pop an element from front
Pop an element from back

Current capacity 16
Current size 7
Front element 7
Rear element 6
```

### 复杂度分析

时间复杂度：``O(N)``
辅助空间：``O(N)``