# 如何在 React 中持续一定时间后改变状态？

> 原文：[https://www.geeksforgeeks.org/how-to-change-state-continuously-after-a-certain-amount-of-time-in-react/](https://www.geeksforgeeks.org/how-to-change-state-continuously-after-a-certain-amount-of-time-in-react/)

在某些情况下，切换需要一定时间后才能连续改变状态。首先，创建一个负责改变组件状态的函数。然后第一次从构造函数方法调用该函数。使用函数内部的 `setInterval` 方法在固定时间后更改状态。`setInterval` 方法采取两个参数回调和时间。在给定的时间后，`callback` 函数被反复调用。使用 `setState` 方法改变组件的状态。

```jsx
timing(){
  setInterval(() => {
    this.setState({
      stateName : new-state-value
    })
  }, time)
}
```

**例 1：** 这个例子说明了如何在一定时间后连续改变状态。

**index.js：**

```jsx
import React from 'react'
import ReactDOM from 'react-dom'
import App from './App'

ReactDOM.render(<App />, document.querySelector('#root'))
```