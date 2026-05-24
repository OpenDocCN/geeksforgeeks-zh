# c++ 中的机器学习

> 原文:[https://www.geeksforgeeks.org/machine-learning-in-c/](https://www.geeksforgeeks.org/machine-learning-in-c/)

我们大多数人都把 C++ 作为我们的第一语言，但是当涉及到像数据分析和机器学习这样的东西时，Python 成为了我们的首选语言，因为它简单并且有大量的预写模块库。
但是 C++ 也可以用于机器学习吗？如果是，那怎么做？

**先决条件:**

1.  **C++ Boost 库:-** 这是一个功能强大的 C++ 库，用于各种目的，如大型数学运算等。
    可以参考这里的[来安装这个库](http://www.boost.org/doc/libs/1_62_0/more/getting_started/unix-variants.html#errors-and-warnings)
2.  **ML pack C++ 库:-** 这是一个小型且可扩展的 C++ 机器学习库。
    这个库的安装可以参考这里的[。
    **注意:**安装 mlpack 时设置 USE_OPENMP=OFF，不要担心，给定的链接有如何操作的指南](https://github.com/mlpack/mlpack/)
3.  **样本 CSV 数据文件:-** 由于 MLpack 库没有任何内置的样本数据集，因此我们必须使用自己的样本数据集。

### 我们的模型

我们正在编写的代码采用一个简单的向量数据集，并为每个数据点找到最近的邻居。

培训部分已突出显示

```cpp
Input : Our Input is a file named data.csv containing a dataset of vectors
The File Contains the Following Data:
3, 3, 3, 3, 0
3, 4, 4, 3, 0
3, 4, 4, 3, 0
3, 3, 4, 3, 0
3, 6, 4, 3, 0
2, 4, 4, 3, 0
2, 4, 4, 1, 0
3, 3, 3, 2, 0
3, 4, 4, 2, 0
3, 4, 4, 2, 0
3, 3, 4, 2, 0
3, 6, 4, 2, 0
2, 4, 4, 2, 0

```

**代码:**

```cpp
#include <mlpack/core.hpp>
#include <mlpack/methods/neighbor_search/neighbor_search.hpp>

using namespace std;
using namespace mlpack;
// NeighborSearch and NearestNeighborSort
using namespace mlpack::neighbor;
// ManhattanDistance
using namespace mlpack::metric;

void mlModel()
{
    // Armadillo is a C++ linear algebra library; 
    // mlpack uses its matrix data type.
    arma::mat data;

    /*
    data::Load is used to import data to the mlpack, 
    It takes 3 parameters,
        1\. Filename = Name of the File to be used
        2\. Matrix = Matrix to hold the Data in the File
        3\. fatal = true if you want it to throw an exception
         if there is an issue
    */
    data::Load("data.csv", data, true);

    /*
    Create a NeighborSearch model. The parameters of the 
    model are specified with templates:
        1\. Sorting method: "NearestNeighborSort" - This 
        class sorts by increasing distance.
        2\. Distance metric: "ManhattanDistance" - The 
        L1 distance, the sum of absolute distances.
        3\. Pass the reference dataset (the vectors to 
        be searched through) to the constructor.
     */
    NeighborSearch<NearestNeighborSort, ManhattanDistance> nn(data);
    // in the above line we trained our model or 
    // fitted the data to the model
    // now we will predict

    arma::Mat<size_t> neighbors; // Matrices to hold
    arma::mat distances; // the results

    /*
    Find the nearest neighbors. Arguments are:-
        1\. k = 1, Specify the number of neighbors to find
        2\. Matrices to hold the result, in this case, 
        neighbors and distances
    */
    nn.Search(1, neighbors, distances);
    // in the above line we find the nearest neighbor

    // Print out each neighbor and its distance.
    for (size_t i = 0; i < neighbors.n_elem; ++ i)
    {
        std::cout << "Nearest neighbor of point " << i << " is point "
                  << neighbors[i] << " and the distance is " 
                  << distances[i] << ".\n";
    }
}

int main()
{
    mlModel();
    return 0;
}
```

使用在终端/CMD 中运行上述代码

```cpp
g++ knn_example.cpp -o knn_example -std=c++ 11 -larmadillo -lmlpack -lboost_serialization

```

然后

```cpp
./knn_example

```

```cpp
Output:
Nearest neighbor of point 0 is point 7 and the distance is 1.
Nearest neighbor of point 1 is point 2 and the distance is 0.
Nearest neighbor of point 2 is point 1 and the distance is 0.
Nearest neighbor of point 3 is point 10 and the distance is 1.
Nearest neighbor of point 4 is point 11 and the distance is 1.
Nearest neighbor of point 5 is point 12 and the distance is 1.
Nearest neighbor of point 6 is point 12 and the distance is 1.
Nearest neighbor of point 7 is point 10 and the distance is 1.
Nearest neighbor of point 8 is point 9 and the distance is 0.
Nearest neighbor of point 9 is point 8 and the distance is 0.
Nearest neighbor of point 10 is point 9 and the distance is 1.
Nearest neighbor of point 11 is point 4 and the distance is 1.
Nearest neighbor of point 12 is point 9 and the distance is 1.

```