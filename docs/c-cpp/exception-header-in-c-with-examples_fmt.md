# C++ 中的异常头，带示例

> 原文: [https://www.geeksforgeeks.org/exception-header-in-c-with-examples/](https://www.geeksforgeeks.org/exception-header-in-c-with-examples/)

[C++](https://www.geeksforgeeks.org/c-plus-plus/) 提供了名称空间 `std` 中的头文件 `<exception>` 中定义的标准异常列表，其中 `exception` 是所有标准异常的基类。标准库生成的所有异常，如 [`bad_alloc`](https://www.geeksforgeeks.org/bad_alloc-in-cpp/)、[`bad_cast`](https://www.geeksforgeeks.org/typeinfobad_cast-in-c-with-examples/?ref=rp)、[`runtime_error`](https://www.geeksforgeeks.org/g-fact-33/) 等都继承自 `std::exception`。因此，所有标准异常都可以通过引用来捕获。

**头文件:**

```cpp
#include <exception>
```

下面是 C++ 中抛出的错误:

| 异常 | 描述 |
| --- | --- |
| `bad_alloc` | 分配失败时由 `new` 引发 |
| `bad_cast` | 动态转换失败时由 `dynamic_cast` 引发 |
| `bad_exception` | 由某些动态异常说明符引发 |
| `bad_typeid` | 由 `typeid` 引发 |
| `bad_function_call` | 由空函数对象引发 |
| `bad_weak_ptr` | 当传递一个坏的 `weak_ptr` 时，由 `shared_ptr` 引发 |
| `logic_error` | 与程序内部逻辑相关的错误 |
| `runtime_error` | 与程序内部逻辑相关的错误 |

下面是程序来说明 C++ 中异常类的一些错误:

## 程序 1

下图为 `std::bad_alloc` 错误:

### 使用类 bad_alloc

```cpp
// C++ program to illustrate bad_alloc
// using class bad_alloc
#include <exception>
#include <iostream>
using namespace std;

// Function to illustrate bad_alloc
void createArray(int N)
{
    // Try Block
    try {
        // Create an array of length N
        int* array = new int[N];

// If created successfully then
        // print the message
        cout << "Array created successfully"
             << " of length " << N << " \n";
    }

// Check if the memory
    // was allocated or not
    // using class bad_alloc
    catch (bad_alloc& e) {

// If not, print the error message
        cout << e.what()
             << " for array of length "
             << N << " \n";
    }
}

// Driver Code
int main()
{
    // Function call to create an
    // array of 1000 size
    createArray(1000);

// Function call to create an
    // array of 1000000000 size
    createArray(1000000000);
    return 0;
}
```

### 使用类 exception

```cpp
// C++ program to illustrate bad_alloc
// using class exception
#include <exception>
#include <iostream>
using namespace std;

// Function to illustrate bad_alloc
void createArray(int N)
{
    // Try Block
    try {
        // Create an array of length N
        int* array = new int[N];

// If created successfully then
        // print the message
        cout << "Array created successfully"
             << " of length " << N << " \n";
    }

// Check if the memory
    // was allocated or not
    // using class exception
    catch (exception& e) {

// If not, print the error message
        cout << e.what()
             << " for array of length "
             << N << " \n";
    }
}

// Driver Code
int main()
{
    // Function call to create an
    // array of 1000 size
    createArray(1000);

// Function call to create an
    // array of 1000000000 size
    createArray(1000000000);
    return 0;
}
```

**Output:**

```cpp
Array created successfully of length 1000 
std::bad_alloc for array of length 1000000000
```

**说明:**

*   为了创建一个长度为 `1000` 的数组，**内存分配成功**并且没有为相同的内容抛出 `exception`。
*   为了创建长度为 `1000000000` 的数组，**内存分配不成功**，抛出异常 `std::bad_alloc`。抛出的异常属于类型 `bad_alloc`，它是从类 `exception` 派生的。函数 `what()` 是在[基类](https://www.geeksforgeeks.org/virtual-base-class-in-c/)中定义的[虚函数](https://www.geeksforgeeks.org/virtual-function-cpp/) `exception`。函数 `what()` 返回一个空终止字符串，通常是对错误的描述。

**注意:** `bad_alloc` 异常是在[内存分配](https://www.geeksforgeeks.org/what-is-dynamic-memory-allocation/)失败时由 [`operator new`](https://www.geeksforgeeks.org/new-vs-operator-new-in-cpp/) 抛出的。

**为什么我们通过引用捕捉到一个异常？**
通过值捕获异常将调用复制构造函数并创建异常的副本，这会增加运行时开销。因此，参照捕捉是一个更好的选择。如果我们想修改异常或向错误消息中添加一些附加信息，那么通过引用捕获是最好的方法。对于这种情况:

```cpp
catch (std::string str)
{
    s += "Additional info";
    throw;
}
```

上面的程序想要捕捉异常，给它添加一些信息并重新抛出它。但是 `str` 是一个值变量的调用，它在函数中被局部改变，当函数重新抛出异常时，原始异常被传递。

**正确代码:**

```cpp
catch (std::string& s)
{
    s += "Additional info";
    throw;
}
```

## 程序 2

下面是程序说明 `logic_error`:

```cpp
// C++ program to illustrate logic_error
#include <exception>
#include <iostream>
using namespace std;

// Function to find factorial of N and
// throws error if occurs
void findFactorial(int N)
{
    // Initialise variable by 1
    int factorial = 1;

// Check for errors
    try {
        // If N is less than zero then,
        // it shows errors as factorial
        // of negative number can't be
        // calculated
        if (N < 0) {

// Exception object which
            // returns the message passed
            // to it
            throw invalid_argument(
                "negative not allowed");
        }

// Find factorial if no error occurs
        for (int i = N; i > 0; i--) {
            factorial *= i;
        }
        cout << "Factorial of " << N
             << " is " << factorial << endl;
    }

// Print the error message
    catch (exception& e) {
        cout << e.what();
    }
}

// Driver Code
int main()
{
    // Function call to find factorial
    // of 0
    findFactorial(0);

// Function call to find factorial
    // of 3
    findFactorial(3);

// Function call to find factorial
    // of -1
    findFactorial(-1);

return 0;
}
```

**Output:**

```cpp
Factorial of 0 is 1
Factorial of 3 is 6
negative not allowed
```