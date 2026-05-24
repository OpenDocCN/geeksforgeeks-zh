# 线性回归工作的数学解释

> 原文：[https://www.geeksforgeeks.org/mathematical-explanation-for-linear-regression-working/](https://www.geeksforgeeks.org/mathematical-explanation-for-linear-regression-working/)

假设给我们一个数据集

![](img/3df69c07642f0498cce4883323ba3718.png)

给出了一个公司的工作与经验数据集，任务是根据员工的工作经验预测其工资。
本文旨在解释当我们使用预定义函数执行预测任务时，现实中[线性回归](https://www.geeksforgeeks.org/ml-linear-regression/)在数学上是如何工作的。
让我们探索一下当线性回归算法被训练时，这些东西是如何工作的。

**迭代 1**–开始时，随机选择`θ0`和`θ1`值。我们假设，`θ0 = 0`，`θ1 = 0`。

*   **线性回归假设下迭代 1 后的预测值。**

![](img/c591eec05f6466f55d36c4c15d41771f.png)

*   **成本函数–错误**

![](img/c3924d581d5dc3f1e2796b2c8d9dda1e.png)

*   **梯度下降–更新`θ0`值**【这里，`j = 0`】

![](img/148fe02f6b63c31281611f3c37667cd9.png)

*   **梯度下降–更新`θ1`值**【这里，`j = 1`】

![](img/eca6f828215091f3fabc71bcbec05ea2.png)

**迭代 2**–`θ0 = 0.005`，`θ1 = 0.02657`

*   **线性回归假设下迭代 1 后的预测值。**

![](img/1e9cc11c5b5c7c5841dde5f640cc53e0.png)

现在，类似于上面执行的第 1 次迭代，我们将再次计算成本函数，并使用梯度下降更新`θj`值。
我们将继续迭代，直到成本函数不再减少。此时，模型达到最佳`θ`值。在模型假设中使用这些`θ`值将给出最佳的预测结果。