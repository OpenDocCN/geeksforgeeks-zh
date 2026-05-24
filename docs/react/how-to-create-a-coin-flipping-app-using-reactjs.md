# 如何使用 ReactJS 创建投币应用？

> 原文:[https://www . geeksforgeeks . org/如何创建一个投币应用程序-使用-reactjs/](https://www.geeksforgeeks.org/how-to-create-a-coin-flipping-app-using-reactjs/)

基本上，我们想建立一个应用程序来投掷或投掷硬币。每次硬币随机翻转时，硬币的一面会从头到尾显示出来，我们还想记录硬币翻转了多少次，以及正面和反面出现了多少次。

我们创建了三个组件“应用程序”和“动画币”和“硬币”。应用程序组件仅渲染单个动画输入组件。应用程序组件中没有实际的逻辑。FlipCoin 组件包含逻辑背后的所有内容。它有一个默认的道具硬币，是一个数组，包含两个图像头和尾(硬币的两面)。它是一个有状态组件，有三个状态的当前面、翻转总数和头数。点击事件处理程序被设置为按钮“翻转”。处理函数基本上根据随机生成的值随机选择面部头部或尾部，并在每次处理程序运行时根据选择的面部更新当前面部状态。处理函数还跟踪翻转按钮被点击的次数和随机生成的头面部的次数，并将其值更新为相应的状态。最后一个硬币组件负责根据从 FlipCoin 组件中的处理函数中随机选择的一面来显示正确的硬币面。FlipCoin 使用道具系统与硬币组件进行通信。

**示例:**在这个示例中，我们将在 App.js 上进行一些更改，以导入一个组件。在该组件中，我们将包括一个图像的硬币的两面。把它翻转成一张图片。

**档案名称索引. js:**

## 【JavaScript】

```jsx
import React from 'react'
import ReactDOM from 'react-dom'
import App from './App'

ReactDOM.render(<App />, document.querySelector('#root'))
```