# 负数上的模数

> 原文:[https://www.geeksforgeeks.org/modulus-on-negative-numbers/](https://www.geeksforgeeks.org/modulus-on-negative-numbers/)

下面的 C 程序会输出什么？

## c

```cpp
#include <stdio.h>
int main()
{
   int a = 3, b = -8, c = 2;
   printf("%d", a % b / c);
   return 0;
}
```

## C++

```cpp
#include <iostream>
using namespace std;

int main() {

   int a = 3, b = -8, c = 2;
   cout << a % b / c;
   return 0;
}
```

**Output**

```cpp
1
```

%和/具有相同的优先级和从左到右的关联性。所以首先执行%导致 3，然后执行/导致 1。重点是，在 C 中模数运算符的情况下，左操作数的 ***符号被追加到结果中。*** 

## c

```cpp
#include <stdio.h>
int main()
{
   // a positive and b negative.
   int a = 3, b = -8;
   printf("%d", a % b);
   return 0;
}
```

## C++

```cpp
#include <iostream>
using namespace std;

int main() {
     int a = 3, b = -8;
     cout << a % b;
    return 0;
}
```

输出

```cpp
3
```

## c

```cpp
#include <stdio.h>
int main()
{
   // a negative and b positive
   int a = -3, b = 8;
   printf("%d", a % b);
   return 0;
}
```

## C++

```cpp
#include <iostream>
using namespace std;

int main()
{
   // a negative and b positive
   int a = -3, b = 8;
   cout << a%b;
   return 0;
}
```

输出

```cpp
-3
```

## c

```cpp
#include <stdio.h>
int main()
{
   // a and b both negative
   int a = -3, b = -8;
   printf("%d", a % b);
   return 0;
}
```

## C++

```cpp
#include <iostream>
using namespace std;

int main() {
   // a and b both negative
   int a = -3, b = -8;
   cout << a % b;
   return 0;
}
```

输出

```cpp
-3
```

当两个操作数都为正时，任何人都可以预测模数运算符的输出。但是当涉及到负数时，不同的语言给出不同的输出。

在 C 语言中，模数计算如下:

a % n = a –( n * trunc(a/n))。

例如，
8%-3 = 8 –(-3 * trunc(8/-3))
= 8 –(-3 * trunc(-2.666)..))
= 8 –(-3 *-2){四舍五入为零}
= 8–6
= 2

更多信息请参见[https://en.wikipedia.org/wiki/Modulo_operation](https://en.wikipedia.org/wiki/Modulo_operation)

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。