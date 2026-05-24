# 如何在 C++ 中实现用户定义的共享指针

> 原文:[https://www . geesforgeks . org/如何实现-用户定义-共享指针-in-c/](https://www.geeksforgeeks.org/how-to-implement-user-defined-shared-pointers-in-c/)

**共享指针:**
一个 std::shared_ptr 是一个原始指针的容器。它是一个引用计数所有权模型，也就是说，它与 std::shared_ptr 的所有副本一起维护其包含的指针的引用计数。因此，每当新指针指向资源时，计数器就递增，而当对象的析构函数被调用时，计数器就递减。
**引用计数:**
这是一种存储引用、指针或句柄数量的技术，这些引用、指针或句柄指向某个资源，如对象、内存块、磁盘空间或其他资源。
被包含的原始指针引用的对象将不会被销毁，直到引用计数大于零，即直到 std::shared_ptr 的所有副本都被删除。
**何时使用:**当我们想要将一个原始指针分配给多个所有者时，应该使用 shared_ptr。
关于共享指针和其他智能指针的更多信息和细节，请阅读这里的。
**共享指针的用户定义实现:**
**程序:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <iostream>
using namespace std;

// Class representing a reference counter class
class Counter
{
public:
    // Constructor
    Counter()
        : m_counter(0){};

    Counter(const Counter&) = delete;
    Counter& operator=(const Counter&) = delete;

    // Destructor
    ~Counter() {}

    void reset()
    {
      m_counter = 0;
    }

    unsigned int get()
    {
      return m_counter;
    }

    // Overload post/pre increment
    void operator++()
    {
      m_counter++ ;
    }

    void operator++(int)
    {
      m_counter++ ;
    }

    // Overload post/pre decrement
    void operator--()
    {
      m_counter--;
    }
    void operator--(int)
    {
      m_counter--;
    }

    // Overloading << operator
    friend ostream& operator<<(ostream& os,
                               const Counter& counter)
    {
        os << "Counter Value : " << counter.m_counter
           << endl;
        return os;
    }

private:
    unsigned int m_counter{};
};

// Class representing a shared pointer
template <typename T>

class Shared_ptr
{
public:
    // Constructor
    explicit Shared_ptr(T* ptr = nullptr)
    {
        m_ptr = ptr;
        m_counter = new Counter();
        if (ptr)
        {
            (*m_counter)++ ;
        }
    }

    // Copy constructor
    Shared_ptr(Shared_ptr<T>& sp)
    {
        m_ptr = sp.m_ptr;
        m_counter = sp.m_counter;
        (*m_counter)++ ;
    }

    // Reference count
    unsigned int use_count()
    {
      return m_counter->get();
    }

    // Get the pointer
    T* get()
    {
      return m_ptr;
    }

    // Overload * operator
    T& operator*()
    {
      return *m_ptr;
    }

    // Overload -> operator
    T* operator->()
    {
      return m_ptr;
    }

    // Destructor
    ~Shared_ptr()
    {
        (*m_counter)--;
        if (m_counter->get() == 0)
        {
            delete m_counter;
            delete m_ptr;
        }
    }

    friend ostream& operator<<(ostream& os,
                               Shared_ptr<T>& sp)
    {
        os << "Address pointed : " << sp.get() << endl;
        os << *(sp.m_counter) << endl;
        return os;
    }

private:
    // Reference counter
    Counter* m_counter;

    // Shared pointer
    T* m_ptr;
};

int main()
{
    // ptr1 pointing to an integer.
    Shared_ptr<int> ptr1(new int(151));
    cout << "--- Shared pointers ptr1 ---\n";
    *ptr1 = 100;
    cout << " ptr1's value now: " << *ptr1 << endl;
    cout << ptr1;

    {
        // ptr2 pointing to same integer
        // which ptr1 is pointing to
        // Shared pointer reference counter
        // should have increased now to 2.
        Shared_ptr<int> ptr2 = ptr1;
        cout << "--- Shared pointers ptr1, ptr2 ---\n";
        cout << ptr1;
        cout << ptr2;

        {
            // ptr3 pointing to same integer
            // which ptr1 and ptr2 are pointing to.
            // Shared pointer reference counter
            // should have increased now to 3.
            Shared_ptr<int> ptr3(ptr2);
            cout << "--- Shared pointers ptr1, ptr2, ptr3 "
                    "---\n";
            cout << ptr1;
            cout << ptr2;
            cout << ptr3;
        }

        // ptr3 is out of scope.
        // It would have been destructed.
        // So shared pointer reference counter
        // should have decreased now to 2.
        cout << "--- Shared pointers ptr1, ptr2 ---\n";
        cout << ptr1;
        cout << ptr2;
    }

    // ptr2 is out of scope.
    // It would have been destructed.
    // So shared pointer reference counter
    // should have decreased now to 1.
    cout << "--- Shared pointers ptr1 ---\n";
    cout << ptr1;

    return 0;
}
```

**Output:** 

```cpp
--- Shared pointers ptr1 ---
Address pointed : 0x1cbde70
Counter Value : 1

--- Shared pointers ptr1, ptr2 ---
Address pointed : 0x1cbde70
Counter Value : 2

Address pointed : 0x1cbde70
Counter Value : 2

--- Shared pointers ptr1, ptr2, ptr3 ---
Address pointed : 0x1cbde70
Counter Value : 3

Address pointed : 0x1cbde70
Counter Value : 3

Address pointed : 0x1cbde70
Counter Value : 3

--- Shared pointers ptr1, ptr2 ---
Address pointed : 0x1cbde70
Counter Value : 2

Address pointed : 0x1cbde70
Counter Value : 2

--- Shared pointers ptr1 ---
Address pointed : 0x1cbde70
Counter Value : 1

```