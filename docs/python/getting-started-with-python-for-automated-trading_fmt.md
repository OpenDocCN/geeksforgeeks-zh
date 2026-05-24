# 开始使用 Python 进行自动交易

> 原文: [https://www.geeksforgeeks.org/getting-started-with-python-for-automated-trading/](https://www.geeksforgeeks.org/getting-started-with-python-for-automated-trading/)

`自动交易`是通过计算机处理和执行的交易入口和出口的术语。自动化交易有一定的优势:

1.  **最小化人为干预:** 自动化交易系统在交易过程中消除了情绪因素。交易者通常更容易通过控制情绪来坚持策略。
2.  **在历史数据上进行回测:** 回测允许交易者在历史数据（前一周/月/年数据）上应用他们的策略。这有助于他们理解策略在实时数据上的影响，并帮助他们确定交易盈利或亏损的概率。
3.  **在波动市场中保持纪律:** 当市场波动时，交易者会跳过交易规则。这会导致市场纪律涣散。当交易者屈服于贪婪或恐惧的人类情绪时，纪律就会丧失。自动化交易可以避免此类问题。自动化交易有助于确保一致性，保证策略执行遵循规则。
4.  **提高订单输入速度:** 因为计算机可以立即响应不断变化的市场条件，所以一旦交易要求得到满足，自动化系统就可以生成订单。

`Python` 因其能够轻松构建复杂的统计模型而在量子金融中广受欢迎。这是因为像 `pandas`、`NumPy`、`Matplotlib`、`PyAlgoTrade`、`Pybacktest` 等科学库。

## 自动化交易所需的组件

1.  **Anaconda:** 设置 `Python` 的第一步是下载 `Anaconda`。`Anaconda` 是一个可靠的 `Python` 发行版，它包含了执行 `Python` 代码所需的所有工具和库。
2.  **Spyder IDE:** `IDE` 代表集成开发环境。它提供了一个用于编写、调试、编译和执行 `Python` 代码的界面。
3.  **Jupyter Notebook:** `Jupyter Notebook` 是一个用来理解代码片段的交互平台。`Jupyter Notebook` 主要使用“标记”单元格解释代码，使用“代码”单元格执行代码。对于试图理解代码片段工作原理的学习者来说，它非常有用。

**注意:** `Spyder IDE` 用于运行和执行大项目，而 `Jupyter Notebook` 用于执行小块代码。

## 理解 Python 中关于量子交易的流行包/库

`Python` 有一个庞大的库集合，可以用于不同的功能，如编程、机器学习、可视化等。然而，在真正开始使用 `Python` 之前，我们将讨论编码交易策略所需的最重要的库。

我们将需要导入财务数据，进行数字评估，构建交易策略，绘制图表，并执行数据回溯测试。所需的库如下所示:

1.  **NumPy:** `NumPy` 是 `Numerical Python` 的缩写，用于数据的数值分析。
2.  **Pandas:** 当处理表格格式（即行和列）的数据（如电子表格）时，`Pandas` 被广泛使用。它可用于在 `Python` 代码中导入 `Excel` 和 `CSV` 文件。
3.  **Matplotlib:** 这个库包含用于绘制2D图形的函数。
4.  **TA-Lib:** `TA-Lib` 被广泛用于对数据执行技术分析，例如布林带、`RSI`（相对强弱指标）、`VWAP`（成交量加权平均价）、`MA`（移动平均线）。
5.  **Zipline:** 一个支持回溯测试和实时交易的事件驱动系统。

在开始用 `Python` 构建自己的策略之前，您需要了解以下几个基本概念。

## 参考文献

1.  [https://numpy.org/](https://numpy.org/)
2.  [https://matplotlib.org/](https://matplotlib.org/)
3.  [https://pandas.pydata.org/](https://pandas.pydata.org/)
4.  [https://www.zipline.io/](https://www.zipline.io/)
5.  [https://github.com/mrjbq7/ta-lib](https://github.com/mrjbq7/ta-lib)