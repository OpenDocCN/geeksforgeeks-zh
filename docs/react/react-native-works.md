# 【React Native 是如何工作的？

> 原文:[https://www.geeksforgeeks.org/react-native-works/](https://www.geeksforgeeks.org/react-native-works/)

在[之前的博文](https://www.geeksforgeeks.org/introduction-react-native/)中，我们构建了 starter app，显示“GeeksForGeeks 真棒！”文本，并使用 React Native 平台学习了一些 JavaScript 代码。

**但是在底层代码中，在原生项目中会发生什么呢？**
所以在深入研究 React Native Examples 之前，让我们先了解一下底层代码中到底发生了什么。

**反应原生应用程序中的线程**

反应原生应用程序中有 4 个线程:

**1) UI 线程:**又称主线程。这用于原生 android 或 iOS UI 渲染。例如，在 android 中，这个线程用于 android 测量/布局/绘制发生。

**2) JS 线程:** JS 线程或 Javascript 线程是逻辑将要运行的线程。例如，这是执行应用程序的 javascript 代码、进行 api 调用、处理触摸事件等的线程。对本机视图的更新在 JS 线程中的每个事件循环结束时被批处理并发送到本机端(并最终在 UI 线程中执行)。

为了保持良好的性能，JS 线程应该能够在下一帧渲染截止日期之前向 UI 线程发送批量更新。例如，iOS 每秒显示 60 帧，这将导致每 16.67 毫秒出现一个新帧。如果您在 javascript 事件循环中进行一些复杂的处理，导致用户界面发生变化，并且花费了 16.67 毫秒以上的时间，那么用户界面将显得迟钝。

一个例外是完全发生在 UI 线程中的本机视图，例如，navigatorIOS 或 scrollview 完全在 UI 线程中运行，因此不会因 js 线程速度慢而被阻止。

**3)原生模块线程:**有时候应用程序需要访问平台 API，而这是作为原生模块线程的一部分发生的。

**4)渲染线程:**仅在 Android L (5.0)中，react 原生渲染线程用于生成实际的 OpenGL 命令，用于绘制您的 UI。

**反应原生体工作中涉及的过程**

app 第一次启动时，主线程开始执行，开始加载 JS 包。

2)当 JavaScript 代码加载成功后，主线程会将其发送给另一个 JS 线程，因为当 JS 进行一些繁重的计算时，会填充线程一段时间，UI 线程在任何时候都不会受到影响。

3)当 React 开始渲染时，协调器开始“区分”，当它生成新的虚拟 DOM(布局)时，它将更改发送到另一个线程(影子线程)。

4) Shadow 线程计算布局，然后将布局参数/对象发送到主(UI)线程。(这里你可能会奇怪为什么我们叫它“影子”？这是因为它会生成阴影节点)

5)由于只有主线程能够在屏幕上渲染一些东西，所以阴影线程应该将生成的布局发送给主线程，然后 UI 才会渲染。

**反应天然产物的分离**

通常，我们可以将 React Native 分为 3 个部分:

1)原生反应–原生端

2)原生反应–JS 端

3)原生反应-桥接

这通常被称为“反应原生的三个部分”

本文由 **[Saket Kumar](https://www.facebook.com/saketkumar95)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。