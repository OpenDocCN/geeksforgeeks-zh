# 为什么咕噜在开发者中这么受欢迎？

> Original: [https://www.geeksforgeeks.org/why-golang-is-so-popular-among-developers/](https://www.geeksforgeeks.org/why-golang-is-so-popular-among-developers/)

Golang，也被称为“Go”，是一种编译语言，速度快，性能高，设计简单，易于阅读和理解。 Go 是由 Rob Pike、Robert Griesemer 和 Ken Thompson 在 Google 创建的，2009 年 11 月首次出现。 [**Golang**](https://www.geeksforgeeks.org/golang/)的语法被设计为高度干净和易于访问。

![Why-Golang-is-so-Popular-Among-Developers](img/772325c75f2878f8c05595fcb51ceab3.png)

Go 是在 2007 年发明的，当时多核 CPU 架构随处可见，没有编程语言简化了多线程应用的开发。 安全有效地管理不同线程的责任是开发人员的巨大责任。 围棋与其他语言不同，它很年轻，但很强大。 [Goroutines](https://www.geeksforgeeks.org/goroutines-concurrency-in-golang/)在另一个层面上彻底改变了竞争性编程。

测试证明，在 GO 上编写的应用程序具有很高的性能和可伸缩性。 Golang 是一种非常高效的语言，就像[C](https://www.geeksforgeeks.org/c-language-set-1-introduction/)/[C++](https://www.geeksforgeeks.org/c-plus-plus/)一样，像 Java 一样处理并行性，并且像 Python 和 PEPEL 一样具有简单的代码可读性。 与它的前身相比，歌朗拥有无可争辩的建筑优势。

Go 被一些大品牌使用，如 BBC、Uber、诺华、Basecamp 和 Soundcloud。 优步报告了更好的吞吐量、高性能、延迟和正常运行时间。 英国广播公司(BBC)是广播世界新闻的家喻户晓的公司，它将其用作后台，包括爬行器和网络刮取器。 SoundCloud 的构建和部署系统正在进行中。

### 为什么要去呢？

对于有 C++经验的程序员来说，学习起来很容易，而且将遗留代码转换为 Go 也非常简单。 作为一种编译的、静态类型的语言，它比解释选项快得多，也提供了大部分的性能优势。 Go 作为一种语言更类似于 C，然而，除了 C 特性之外，Go 还提供了内存安全、垃圾收集、结构类型和 CSP 风格的并发性。

Go 非常适合一般的面向性能的云软件。 流行的 DevOps 工具都是用 Go 编写的，比如 Docker，甚至开源容器编排系统 Kubernetes 都是构建在 Go 上的。 [Vitess](https://opensource.google.com/projects/vitess)是 Google 构建的分布式数据库系统，也是与 Golang 共同构建的 MySQL 后端，自 2011 年以来一直由 YouTube 使用。

在 2018 年进行的[堆栈溢出调查](https://insights.stackoverflow.com/survey/2018/#technology)中，高朗排名第 5 位。 根据 2018 年[第二季度 GitHub 报告](https://madnight.github.io/githut/#/pull_requests/2019/4)，Golang 的整体增长率接近 7%，与上一季度相比变化了 1.5%。 到 2019 年第四季度，Golang 的整体增长率已达到 8%。

### 歌郎如此受欢迎的原因是什么？

*   Go 是一种静态类型的编译语言；因此，您可以很容易地在早期发现问题。
*   GO 可以立即编译成机器码，因此它使得编辑/刷新周期相对较快，并且仍然可以生成相当高效的机器码。
*   围棋的设计使得编写高度并发的网络程序变得容易。
*   Go 附带了许多支持测试的内置基础设施；您可以毫不费力地定义和测试模块；这进一步加强了工程纪律。
*   Go 的跨平台特性使得移植代码变得非常容易，这是 Go 最显著的优势。
*   Go 提供了固执己见的格式化、LINTING 和 VET 工具作为包的默认部分，Go 编译器甚至强制执行了一些东西，比如未使用的变量。 这使它成为一种专业语言。
*   Go 本身对并发性和并行性的支持是它的独特之处。 这使得 Go 成为需要大量并发和/或并行处理、网络、海量计算等应用程序的完美语言。
*   Go 对云的兼容性是最好的。 GO 具有更好的垃圾收集设施，良好的网络包，解决了变量闲置、多文化和跨文化编译器的问题。

### 实际案例

### 1.SendGrid 移动到

早在 2014 年，客户沟通平台 SendGrid 就决定将 Go 作为其主要开发语言。 SendGrid 团队需要从根本上改变他们的开发语言，这归根结底是 Scala、Java 和 Go 之间的竞争。 当时 SendGrid 在开发中面临的最大挑战是并发编程。 将并发异步编程作为语言的一部分是 SendGrid 选择 Go 的最引人注目的原因之一。

### 2.Hexac 从 Python 切换到 Go

Hexac 的联合创始人兼首席技术官蒂格兰·贝伯茨先(Tgran Bayburtsyan)写了一篇独家文章，分享了他的公司从 Python 转向 Go 的原因。 根据他们的代码库统计数据，在 Go 中重写所有项目后，他们得到的代码比以前少了 64%。 由于围棋内置的语言功能，他们节省了大量的资源(内存、CPU)。

Go 为他们的开发团队提供了巨大的灵活性，所有用例都可以使用单一语言，而且对所有人来说，Go 都运行得很好。 在 Hexact Inc，他们在后端和 API 服务上的性能提高了约 30%。 现在，他们可以实时处理日志记录，将其传输到数据库，并使用 WebSocket 从单个或多个服务进行流式传输。 这是使用围棋语言功能的一个突出结果。

### 3.Salesforce 抛弃了 Python，转而选择 Go

在 2017 年推出爱因斯坦分析之前，Salesforce 更新了后台，并在谷歌流行的围棋语言上完全重建了它。 Salesforce 首席架构师纪尧姆·勒斯图姆(Guillaume Le Stum)表示：“Python 在多线程方面做得不好，而 Go 是为适合谷歌生产系统的重型应用程序而设计的，该语言已经过谷歌的测试和批准，所以 Salesforce 选择将 Salesforce 的关键部分爱因斯坦分析(Einstein Analytics)从混合 C-Python 应用程序转变为完全的 Go 应用程序。

### 4.Containerum 选择超越他人

Containerum，一个集装箱管理平台，使用 Go 作为他们的主要语言已经有大约四年了，尽管存在一些挑战，工程团队认为这是一个很好的选择。 在 Containerum 平台上选择 Go 的主要原因是它由一组较小的服务组成，这些服务与系统的其他组件进行通信。 为了确保这一点，非常有必要确保接口兼容性，并编写过于简单、易于阅读和维护的代码。

Go 支持添加补丁，并允许使用代码库中的现成组件，例如图像名称解析验证、关键对象模型等，这也是 Containerum 选择 Go 的原因之一。 Containerum 考虑超越其他语言，因为它有很多 Pro 特性/事实，比如静态类型、简约、标准库、出色的性能、超快的编译等等。

### 5.流行的 DevOps 工具都是用 Go 编写的

巨头谷歌曾考虑用其他语言编写 Kubernetes，包括但 Kubernetes 的联合创始人 Joe Beda 表示，这些语言都没有围棋那么有效。 库伯内斯被写成围棋有很多原因。 其中包括-伟大的库、快速的工具、内置的并发性、垃圾收集、类型安全等。根据 Joe 的说法，Go 中的模式和工具鼓励 Kubernetes 团队编写分解良好且可重用的代码，这将同时给他们带来高度的灵活性和速度。

多克一直是围棋的最大用户。 Docker 的团队喜欢这样做，因为它为他们提供了许多好处：无依赖的静态编译、中立的语言、完整的开发环境、广泛的强大标准库和数据类型、强大的鸭子类型，以及能够以最小的麻烦为多个架构构建。

Istio 是 Kubernetes 生态系统的一部分，也是用围棋编写的。 因为 Kubernetes 也是用围棋写的，所以对于 Istio 来说，用围棋写是一个完美的方法。 这不仅仅是一个原因，在众多原因中，Go 对分散、分布式网络项目的适用性是 Istio 选择 Go 的主要原因之一。

如果您使用 GoLang 编写应用程序，那么练习 CI/CD 有多难？ 很难，不是吗？ 嗯，现在不是时候。 随着围棋的最新创新，如围棋中心 GOPROXY，通往高质量 CI/CD 的道路变得更加清晰。 GoCenter 是不变围棋模块的中心公共集合。 它允许您搜索模块和版本，还可以轻松地将您的模块添加到其中以供公开共享。