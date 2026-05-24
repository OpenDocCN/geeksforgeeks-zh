# 如何使用 ReactJS 创建彩盒应用？

> 原文:[https://www . geesforgeks . org/how-to-create-a-color-box-app-using-reactjs/](https://www.geeksforgeeks.org/how-to-create-a-color-box-app-using-reactjs/)

基本上，我们想建立一个应用程序，显示盒子的数量，给每个盒子分配不同的颜色。每次应用程序加载时，都会分配不同的随机颜色。当用户单击任何一个框时，它会将其颜色更改为一些不同的随机颜色，这些颜色不等于其先前的颜色值。

我们创建了三个组件“应用程序”、“盒子容器”和“盒子”。应用程序组件仅呈现单个 BoxContainer 组件。应用程序组件中没有实际的逻辑。BoxContainer 组件包含所有背后的逻辑。它有一个默认的道具“num ”,它代表了屏幕上显示的许多不同的颜色框。它是一个有状态的组件，有一个包含 RGB 颜色值数组的单一状态。我们映射每种颜色的状态“颜色”，对于每种颜色，我们渲染一个“盒子”组件。盒子组件负责显示每个单独的盒子，并在盒子的背景中设置合适的颜色。box 组件为每个 box 组件设置一个点击事件处理程序，当用户点击任何一个 box 时，会执行一些逻辑来改变该 Box 的颜色。BoxContainer 组件使用道具系统与 Box 组件进行通信。

**示例:**

*   **index.js:**

    ## java 描述语言

    ```jsx
    import React from 'react'
    import ReactDOM from 'react-dom'
    import App from './App'

    ReactDOM.render(<App />, document.querySelector('#root'))
    ```