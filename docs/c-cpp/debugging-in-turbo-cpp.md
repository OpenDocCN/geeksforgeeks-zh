# Turbo c++ 中的调试

> 原文:[https://www.geeksforgeeks.org/debugging-in-turbo-cpp/](https://www.geeksforgeeks.org/debugging-in-turbo-cpp/)

调试是程序员检测并删除程序中现有或潜在的[错误/bug](https://www.geeksforgeeks.org/software-engineering-differences-between-defect-bug-and-failure/)的过程。这是编写有效代码的一个很好的实践。现在，Turbo C++ 为其社区提供了各种有用的特性。在我们的调试中起重要作用的一些选项是监视和跟踪。让我们通过以下程序来理解这些概念:

**示例:**编写一个程序来检查两个数字是否相等

![](img/9d09cafda98b2d9f65d32d9c60b6c73d.png)

现在通过下面提到的步骤来清楚地了解如何调试:

**第一步:**进入窗口菜单，点击下方*手表*。

![Select Watch](img/b199ebefd4fd338a4a061e919731dc93.png)

**步骤 2:** 您将能够在 IDE 底部看到一个名为“Watch”的面板。

![Watch panel](img/af7533f633a1a93fdd0aa35efeacdaaa.png)

**第三步:**同样，从窗口菜单中，我们将选择*输出*和*消息*，然后点击平铺以获得更好的视图。

![Output and Message window](img/a0c27a7cac7a62c9665f742840fa8ccb.png)

**第四步:**转到*调试*，然后在【手表】下选择*添加手表(或 Ctrl+F7)。*

![Add Watch](img/2e76751d856ac382dd79983a6eabcfc8.png)

**第五步:**屏幕上会出现一个对话框，显示“*输入表情添加为手表*”。输入“a”。

![Enter Watch Expression](img/b5f02c1a64e8e0490f5f69592a8a241e.png)

**第六步:**手表面板会显示添加‘a’作为手表表情的结果。

![Watch expression 'a'](img/f75c529c60a10e973279e33957c22a51.png)

**第 7 步:**再次跟随第 5 步，输入‘b’。

![Watch expression 'b'](img/022fcd244b6405ff085cd359eab15efd.png)

**第 8 步:**进入运行选项，点击*追踪进入(或 F7)。*

![Trace Into](img/aae6da5541496c273e11cc9441e68238.png)

**第九步:**你会注意到 void main()被高亮显示。这意味着我们的程序已经开始运行。

![Code is executing](img/f990f638322d624c17df7e5a5f357f0f.png)

**第 10 步:**进入运行菜单，点击*跳过(或 F8)* 进入下一步。

![Step over](img/f458dbd7c673f076fa9354fbedb424d8.png)

**第 11 步:**上一步进入下一条语句。

![Step over#2](img/07b91810f959d75b79110d3080325cd0.png)

**第 12 步:**按 F8 执行下一条语句。

![Step over#3](img/6f586decbcf25c1e74d0ec63110c61a4.png)

**第 13 步:**步过(F8)。

![Step over#4](img/cc044a83cd802e9cf3bed76a885225d3.png)

**第 14 步:**进入下一步(F8)。

![Step over#5](img/1b8493cd7ebcdc1ef94ebd7787c85383.png) **第 15 步:**在控制台输入 2 个数字。

![Enter 2 numbers](img/db70981dd6edd796930fcb85e0c3f1b5.png)

**第 16 步:**看一下手表和输出面板。从用户获得输入后，编译器会覆盖变量中的值。

![Output](img/b74d8142331c6ed63a6055110de52ff5.png)

**第十七步:**按 F8。

![Press F8](img/19ec6eaa71794a5a92ffdd1ce2781fb1.png)

请记住，从我们的*开始，如果条件*为真，编译器就不应该检查 *else 语句*。

**第 18 步:**按 F8 进入下一步。

![Press F8](img/a569cd542b5ff17b5541822cceba469c.png)

**第 19 步:**按 F8 查看下一步是什么。您现在可以看到输出屏幕。

![Output](img/1fd4af3d06c587417084b09e2238f179.png)

**第 20 步:**按 F8 查看接下来会发生什么。

![Debugging ends](img/9e65369dcfce782c0b60ac5843b39931.png)

请注意，右括号现在高亮显示，这意味着程序已经结束。如果再次按下 F8，程序将从第一步重新运行。