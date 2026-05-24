# c++ STL 中矢量的修改器

> 原文:[https://www . geesforgeks . org/modifiers-for-vector-in-CPP-STL/](https://www.geeksforgeeks.org/modifiers-for-vector-in-cpp-stl/)

点击这里[设置 1](https://www.geeksforgeeks.org/vector-in-cpp-stl/) 向量。

**修改器**
1.1 赋值(先输入 _ 迭代器，后输入 _ 迭代器)–将新内容赋给矢量并调整大小
1.2 赋值(size_type n，const value _ type g)–将新内容赋给矢量并调整大小

```cpp
#include <iostream>
#include <vector>

using namespace std;

int main()
{
    vector <int> g1;
    vector <int> g2;
    vector <int> g3;

    g1.assign(5, 10);   // 5 elements with value 10 each

    vector <int> :: iterator it;
    it = g1.begin() + 1;

    g2.assign(it, g1.end() - 1); // the 3 middle values of g1

    int gquiz[] = {1, 2};
    g3.assign(gquiz, gquiz + 2);   // assigning from array

    cout << "Size of g1: " << int(g1.size()) << '\n';
    cout << "Size of g2: " << int(g2.size()) << '\n';
    cout << "Size of g3: " << int(g3.size()) << '\n';
    return 0;
}
```

上述程序的输出是:

```cpp
Size of g1: 5
Size of g2: 3
Size of g3: 2

```

2.push _ back(const value _ type g)–在向量末尾添加新元素‘g’，并将向量容器大小增加 1
3。pop _ back()–删除向量末尾的元素，即最后一个元素，并将向量容器的大小减少 1

```cpp
#include <iostream>
#include <vector>

using namespace std;

int main()
{
  vector <int> gquiz;
  int sum = 0;
  gquiz.push_back(10);
  gquiz.push_back(20);
  gquiz.push_back(30);

  while (!gquiz.empty())
  {
    sum += gquiz.back();
    gquiz.pop_back();
  }

  cout << "The sum of the elements of gquiz is :  "
       << sum << '\n';

  return 0;
}
```

上述程序的输出是:

```cpp
The sum of the elements of gquiz is : 60

```

4.1 insert(const_iterator q，const value _ type g)–在迭代器“q”引用的元素之前添加元素“g”并返回指向新添加元素的迭代器
4.2insert(const_iterator q，size_type n，const value _ type g)–在迭代器“q”当前引用的元素之前添加每个都带有值“g”的“n”个元素，并返回指向第一个新添加元素的迭代器
4.3 insert(const_iterator q，type

```cpp
#include <iostream>
#include <vector>

using namespace std;

int main()
{
    vector <int> gquiz1(3, 10);
    vector <int> :: iterator it;

    it = gquiz1.begin();
    it = gquiz1.insert(it, 20);

    gquiz1.insert(it, 2, 30);

    it = gquiz1.begin();

    vector <int> gquiz2(2, 40);
    gquiz1.insert(it + 2, gquiz2.begin(), gquiz2.end());

    int gq [] = {50, 60, 70};
    gquiz1.insert(gquiz1.begin(), gq, gq + 3);

    cout << "gquiz1 contains : ";
    for (it = gquiz1.begin(); it < gquiz1.end(); it++)
        cout << *it << '\t';

    return 0;
}
```

上述程序的输出是:

```cpp
gquiz1 contains : 50    60    70    30    30    
40    40    20    10    10    10

```

5.1 erase(const_iterator q)–删除由‘q’引用的元素，并返回一个迭代器到被删除元素后面的元素
5.2 erase(const_iterator 优先，const _ iterator 最后)–删除范围内从第一个到最后一个的元素，第一个迭代器包含在范围内，最后一个迭代器不包含在内，并返回一个迭代器到被删除元素后面的元素

```cpp
#include <iostream>
#include <vector>
using namespace std;

int main ()
{
    vector <int> gquiz;

    for (int i = 1; i <= 10; i++)
        gquiz.push_back(i * 2);

    // erase the 5th element
    gquiz.erase(gquiz.begin() + 4);

    // erase the first 5 elements:
    gquiz.erase(gquiz.begin(), gquiz.begin() + 5);

    cout << "gquiz contains :";
    for (int i = 0; i < gquiz.size(); ++ i)
        cout << gquiz[i] << '\t';

    return 0;
}
```

上述程序的输出是:

```cpp
gquiz contains :14    16    18    20

```

6.交换(向量 q，向量 r)–交换‘q’和‘r’的内容
7。clear()–从向量中移除所有元素

```cpp
#include <iostream>
#include <vector>

using namespace std;

int main()
{
    vector <int> gquiz1;
    vector <int> gquiz2;
    vector <int> :: iterator i;

    gquiz1.push_back(10);
    gquiz1.push_back(20);

    gquiz2.push_back(30);
    gquiz2.push_back(40);

    cout << "Before Swapping, \n"
         <<"Contents of vector gquiz1 : ";

    for (i = gquiz1.begin(); i != gquiz1.end(); ++ i)
        cout << *i << '\t';

    cout << "\nContents of vector gquiz2 : ";
    for (i = gquiz2.begin(); i != gquiz2.end(); ++ i)
        cout << *i << '\t';

    swap(gquiz1, gquiz2);

    cout << "\n\nAfter Swapping, \n";
    cout << "Contents of vector gquiz1 : ";
    for (i = gquiz1.begin(); i != gquiz1.end(); ++ i)
        cout << *i << '\t';

    cout << "\nContents of vector gquiz2 : ";
    for (i = gquiz2.begin(); i != gquiz2.end(); ++ i)
        cout << *i << '\t';

    cout << "\n\nNow, we clear() and then add "
         << "an element 1000 to vector gquiz1 : ";
    gquiz1.clear();
    gquiz1.push_back(1000);
    cout << gquiz1.front();

    return 0;
}
```

上述程序的输出是:

```cpp
Before Swapping, 
Contents of vector gquiz1 : 10    20    
Contents of vector gquiz2 : 30    40    

After Swapping, 
Contents of vector gquiz1 : 30    40    
Contents of vector gquiz2 : 10    20    

Now, we clear() and then add an element 1000 to vector gquiz1 : 1000

```

点击此处获取[向量集 3](https://www.geeksforgeeks.org/upper_bound-and-lower_bound-for-vector-in-cpp-stl/) 。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论