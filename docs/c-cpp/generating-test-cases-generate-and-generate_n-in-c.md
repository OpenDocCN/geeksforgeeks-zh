# 生成测试用例(C++ 中的 generate()和 generate _ n())

> 原文:[https://www . geesforgeks . org/generating-test-cases-generate-and-generate _ n-in-c/](https://www.geeksforgeeks.org/generating-test-cases-generate-and-generate_n-in-c/)

为数组程序生成测试用例可能是一个麻烦的过程。但是 STL(标准模板库)中的 generate 和 generate_n 函数可以方便地用随机值填充数组。

*   **generate()**

    生成函数将通过调用生成器函数“gen”提供的随机值分配给范围[begin，end 中的元素。请注意，范围中包括开始，但不包括结束。

    下面的代码演示了生成的实现:

    ```cpp
    // C++ program to demonstrate generate function in STL
    #include <bits/stdc++.h>     
    using namespace std;

    // function to generate random numbers in range [0-999] :
    int randomize() 
    {   
        return (rand() % 1000); 
    }

    int main () 
    {
      // for different values each time we run the code
      srand(time(NULL)); 

      vector<int> vect(10); // declaring the vector

      // Fill all elements using randomize()
      generate(vect.begin(), vect.end(), randomize);

      // displaying the content of vector
      for (int i=0; i<vect.size(); i++)
         cout << vect[i] << " " ;

      return 0;
    }
    ```

    输出:

    ```cpp
    832 60 417 710 487 260 920 803 576 58

    ```

    注意:由于 srand 的原因，每次运行代码时，输出都会不同。如果我们去掉 srand，我们每次运行代码都会得到相同的随机数。

*   **generate_n()**
    The generate_n does the same job as generate upto n elements starting from the element pointed to by the begin iterator.

    The following code demonstrates the working of generate_n :

    ```cpp
    // C++ program to demonstrate generate_n() function in STL
    #include <bits/stdc++.h>    
    using namespace std;

    // function to generate random numbers in range [0-999] :
    int randomize() 
    {   
        return (rand() % 1000); 
    }

    int main () 
    {
      // for different values each time we run the code 
      srand(time(NULL)); 

      vector<int> vect(10); // declaring the vector

      // Fill 6 elements from beginning using randomize()
      generate_n(vect.begin(), 6, randomize);

      // displaying the content of vector
      for (int i=0; i<vect.size(); i++)
        cout << vect[i] << " " ;

      return 0;
    }
    ```

    输出:

    ```cpp
    177 567 15 922 527 4 0 0 0 0

    ```

    注意:在这里，由于 srand 的原因，每次运行代码时输出都会不同。如果我们去掉 srand，我们每次运行代码都会得到相同的随机数。

如果发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论