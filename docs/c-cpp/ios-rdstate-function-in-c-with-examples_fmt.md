# ios rdstate()函数在 C++ 中的应用举例

> 原文：[https://www.geeksforgeeks.org/ios-rdstate-function-in-c-with-examples/](https://www.geeksforgeeks.org/ios-rdstate-function-in-c-with-examples/)

C++ 中 `ios` 类的 `rdstate()` 方法用来读取这个流的内部状态。

## 语法

```cpp
iostate rdstate() const;
```

## 参数

此方法不接受任何参数。

## 返回值

这个方法返回这个流的当前内部状态。

## 例 1

```cpp
// C++ code to demonstrate
// the working of rdstate() function

#include <bits/stdc++.h>
using namespace std;

int main()
{

// Stream
    stringstream ss;

// Using rdstate() function
    cout << "stream rdstate: "
         << ss.rdstate() << endl;

return 0;
}
```

**输出：**

```cpp
stream rdstate: 0
```

## 例 2

```cpp
// C++ code to demonstrate
// the working of rdstate() function

#include <bits/stdc++.h>
using namespace std;

int main()
{

// Stream
    stringstream ss;
    ss.clear(ss.failbit);

// Using rdstate() function
    cout << "stream rdstate: "
         << ss.rdstate() << endl;

return 0;
}
```

**输出：**

```cpp
stream rdstate: 4
```

## 参考

[http://www.cplusplus.com/reference/ios/ios/rdstate/](http://www.cplusplus.com/reference/ios/ios/rdstate/)