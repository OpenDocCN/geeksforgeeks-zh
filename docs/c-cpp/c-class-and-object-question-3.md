# C++ |类和对象|问题 3

> 原文:[https://www . geesforgeks . org/c-class-and-object-question-3/](https://www.geeksforgeeks.org/c-class-and-object-question-3/)

```cpp
class Test {
    int x; 
};
int main()
{
  Test t;
  cout << t.x;
  return 0;
}
```

**(A)** 0
**(B)** 垃圾值
**(C)** 编译器错误

**答案:****(C)**

**说明:**在 C++ 中，默认访问是私有的。因为 x 是 Test 的私有成员，所以在类外访问它是编译器错误。

[本题小测验](https://www.geeksforgeeks.org/quiz-corner-gq/)