# C/c++ 中多维数组的初始化

> 原文:[https://www.geeksforgeeks.org/g-fact-44/](https://www.geeksforgeeks.org/g-fact-44/)

在 C/C++ 中，多维数组的初始化可以让大部分维度成为可选的。除了最左边的尺寸，必须指定所有其他尺寸。
例如，以下程序编译失败，因为没有指定两个维度。

## C

```cpp
#include<stdio.h>
int main()
{
  int a[][][2] = { {{1, 2}, {3, 4}},
                   {{5, 6}, {7, 8}}
                 };  // error
  printf("%d", sizeof(a));
  getchar();
  return 0;
}
```

## C++

```cpp
#include<bits/stdc++.h>
using namespace std;
int main()
{
  int a[][][2] = { {{1, 2}, {3, 4}},
                   {{5, 6}, {7, 8}} };  // error
  cout << sizeof(a);
  getchar();
  return 0;
}

// This code is contributed by Mayank Tyagi
```

以下两个程序工作正常，没有任何错误。

## C

```cpp
// Program 1
#include<stdio.h>
int main()
{
  int a[][2] = {{1,2},{3,4}}; // Works
  printf("%lu", sizeof(a)); // prints 4*sizeof(int)
  getchar();
  return 0;
}
```

## C++

```cpp
// Program 1
#include<bits/stdc++.h>
using namespace std;
int main()
{
  int a[][2] = {{1, 2}, {3, 4}}; // Works
  cout << sizeof(a); // prints 4*sizeof(int)
  return 0;
}

// This code is contributed by Mayank Tyagi
```

## C

```cpp
// Program 2
#include<stdio.h>
int main()
{
  int a[][2][2] = { {{1, 2}, {3, 4}},
                     {{5, 6}, {7, 8}}
                   }; // Works
  printf("%lu", sizeof(a)); // prints 8*sizeof(int)
  getchar();
  return 0;
}
```

## C++

```cpp
// Program 2
#include<bits/stdc++.h>
using namespace std;
int main()
{
  int a[][2][2] = { {{1, 2}, {3, 4}},
                     {{5, 6}, {7, 8}} }; // Works
  cout << sizeof(a); // prints 8*sizeof(int)
  return 0;
}

// This code is contributed by Mayank Tyagi
```

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。