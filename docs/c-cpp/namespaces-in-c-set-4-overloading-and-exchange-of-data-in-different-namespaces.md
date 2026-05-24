# c++ 中的命名空间|集合 4(不同命名空间中的重载和数据交换)

> 原文:[https://www . geesforgeks . org/namespace-in-c-set-4-不同命名空间中数据的重载和交换/](https://www.geeksforgeeks.org/namespaces-in-c-set-4-overloading-and-exchange-of-data-in-different-namespaces/)

**先决条件:**

*   [c++ 中的命名空间|集合 1(简介)](https://www.geeksforgeeks.org/namespace-in-c/)
*   [c++ 中的命名空间|集合 2(扩展命名空间和未命名的命名空间)](https://www.geeksforgeeks.org/namespace-in-c-set-2-extending-namespace-and-unnamed-namespace/)
*   [c++ 中的命名空间|集合 3(访问、创建头、嵌套和别名)](https://www.geeksforgeeks.org/namespace-c-set-3-creating-header-nesting-aliasing-accessing/)

在本文中，我们将讨论不同命名空间之间数据共享的概念，如何访问和重载标准操作符以在用户定义的命名空间内为用户定义的类工作，以及它们的实现。
在 [C++ ](https://www.geeksforgeeks.org/c-plus-plus/) 中，我们可以在不同的名称空间内创建类，而这些类的范围仅限于创建它们的名称空间。因此，我们必须使用范围解析运算符 **(::)** 来访问这些类。
下面是理解命名空间内类的声明和程序中对象的初始化的实现:

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate the basics
// of classes inside namespaces
#include <iostream>
#include <string>

// Declaration of namespace
namespace GeeksforGeeks {

// Output string
std::string out = "This is not from (GeeksforGeeks::string) class!";

// Class inside GeeksforGeeks namespace
class string {
private:
    std::string s = "Hello! ";

public:
    // Make string
    string(const std::string& str)
    {
        s += str;
    }

    // Function to get string
    std::string get_str()
    {
        return s;
    }
};
};

// Driver Code
int main()
{
    std::cout << GeeksforGeeks::out
              << std::endl;

    // Create an object of string class
    // of Test namespace
    GeeksforGeeks::string str("From namespace Test!");

    // Print the string
    std::cout << str.get_str()
              << std::endl;
    return 0;
}
```

**Output:** 

```cpp
This is not from (GeeksforGeeks::string) class!
Hello! From namespace Test!
```

在上面的程序中，我们可以清楚地看到类**“字符串”**在 **GeeksforGeeks** 命名空间中的范围只在命名空间中，该类由参数化的构造函数初始化，该构造函数还更改了命名空间 Test 中类字符串的私有字符串**“**”。
下面的程序是 [**操作符的重载**](https://www.geeksforgeeks.org/operator-overloading-c/) **概念的说明，不同的名字空间类对象**作为参数，**从一个名字空间访问和交换数据到另一个名字空间** :

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to show overloading and
// accessing from different namespaces
#include <iostream>
#include <string>

// Declare namespace test_space1
namespace test_space1 {

const std::string const_prefix = "(test_space1::string) ";

// String class
class string {
private:
    std::string str = "";

    // Private default constructor
    string();

public:
    // Public parameterized constructor
    string(const std::string& s)
        : str(const_prefix + s)
    {
    }

    // Get string function
    std::string get_str() const
    {
        return str;
    }
};
};

// Declare namespace test_space2
namespace test_space2 {

const std::string const_prefix = "(test_space2::string) ";
class string {
private:
    std::string str = "";
    const std::string check_scope = "test_space2!";
    string();

public:
    // Public parameterized constructor
    string(const std::string& s)
        : str(const_prefix + s)
    {
    }

    std::string get_str() const
    {
        return str;
    }
    std::string getScopestr() const
    {
        return check_scope;
    }
};
};

// Declare namespace test_space3
namespace test_space3 {

// Object from another namespace
// (test_space2 in this case!)
const std::string const_prefix = "(test_space3::string) from both nmspaces test_space3 & ";

// Class inside namespace test_space3
class string {
    std::string str = "";
    string();

public:
    string(const test_space2::string& s)
        : str(const_prefix + s.getScopestr())
    {
    }

    // Access function from test_space2
    // and adding a private string of
    // test_space2:: string to str of
    // test_space3
    std::string get_str() const
    {
        return str;
    }
};
};

// Overloading << operator for test_space1
std::ostream& operator<<(std::ostream& os,
                         const test_space1::string& s1)
{
    os << s1.get_str();
    return os;
}

// Overloading << operator for test_space2
std::ostream& operator<<(std::ostream& os,
                         const test_space2::string& s2)
{
    os << s2.get_str();
    return os;
}

// Overloading << operator for test_space3
std::ostream& operator<<(std::ostream& os,
                         const test_space3::string& s3)
{
    os << s3.get_str();
    return os;
}

// Driver Code
int main()
{

    // String str
    const std::string str("This is a standard string");

    // Print the string str
    std::cout << str << std::endl;

    const std::string sample1("This is a test_space1 namespace string");

    // Declare a test_space1 namespace
    // string class object
    const test_space1::string s2(sample1);
    std::cout << s2 << std::endl;

    // Print test_space1 string
    const std::string sample2("This is a test_space2 namespace string");

    // std string
    test_space2::string s3(sample2);

    // Declare a test_space2 namespace
    // string class object
    std::cout << s3 << std::endl;

    // Print test_space2 string
    test_space3::string s4(s3);

    // Print string s4
    std::cout << s4 << std::endl;
    return 0;
}
```

**Output:** 

```cpp
This is a standard string
(test_space1::string) This is a test_space1 namespace string
(test_space2::string) This is a test_space2 namespace string
(test_space3::string) Accessing from both namespaces test_space3 and test_space2!
```

**说明:**

1.  在上面的程序中，我们已经创建了三个名称空间–**test _ space 1、test_space2 和 test_space3** 。
2.  所有这些名称空间都有一个公共的类字符串。我们已经创建了它们各自的对象 **s2、s3 和 s4** ，这些对象在初始化期间采用不同的参数。
3.  名称空间 **test_space** 3 用于从名称空间 **test_space2** 的字符串类内部访问类成员，因此， **test_space3::字符串的构造函数**不同于其他两个类的构造函数。
4.  因此，我们可以从 **test_space2** 获取数据，并在 **test_space3** 中使用。这显示了不同名称空间及其类之间的数据可访问性和交换。