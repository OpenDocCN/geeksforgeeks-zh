# 反应使用回拨钩

> 原文:[https://www.geeksforgeeks.org/react-js-usecallback-hook/](https://www.geeksforgeeks.org/react-js-usecallback-hook/)

当您有一个组件，其中的子组件在不需要的情况下一次又一次地重新呈现时，使用 useCallback 钩子。

传递内联回调和依赖项数组。useCallback 将返回回调的记忆化版本，该版本仅在依赖项之一发生更改时才会更改。当将回调传递给依赖引用相等性的优化子组件以防止不必要的呈现时，这很有用。

**语法:**

```jsx
const memoizedCallback = useCallback(
 () => {
   doSomething(a, b);
 },
 [a, b],
);
```

**创建反应应用程序:**

**步骤 1:** 使用以下命令创建一个 React 应用程序。

```jsx
npx create-react-app foldername
```

**步骤 2:** 创建项目文件夹(即文件夹名)后，使用以下命令移动到该文件夹。

```jsx
cd foldername
```

**项目结构:**如下图。

![](img/61c6f1343b04abacfcac2db8b7a3d996.png)

**不带 useCallback Hook:** 问题是一旦计数器更新，三个函数都会重新创建。警报一次增加三个，但是如果我们更新一些状态，所有与该状态相关的函数都应该重新实例化。如果另一个状态值不变，则不应触摸它。这里，文件名是 App.js

## java 描述语言

```jsx
import React, { useState, useCallback } from 'react'
const funccount = new Set();
const App = () => {

  const [count, setCount] = useState(0)
  const [number, setNumber] = useState(0)

  const incrementCounter = () => {
    setCount(count + 1)
  }
  const decrementCounter = () => {
    setCount(count - 1)
  }

   const incrementNumber = () => {
    setNumber(number + 1)
  }

funccount.add(incrementCounter);
funccount.add(decrementCounter);
funccount.add(incrementNumber);
alert(funccount.size);

  return (
    <div>
      Count: {count}
      <button onClick={incrementCounter}>
        Increase counter
      </button>
      <button onClick={decrementCounter}>
         Decrease Counter
      </button>
      <button onClick={incrementNumber}>
        increase number
      </button>
    </div>
  )
}

export default App;
```

**带 useCallback 钩子:**要解决这个问题，我们可以使用 useCallback 钩子。这里的文件名是 App.js。

## java 描述语言

```jsx
import React, { useState, useCallback } from 'react'
var funccount = new Set();
const App = () => {

  const [count, setCount] = useState(0)
  const [number, setNumber] = useState(0)

const incrementCounter = useCallback(() => {
  setCount(count + 1)
}, [count])
const decrementCounter = useCallback(() => {
  setCount(count - 1)
}, [count])
const incrementNumber = useCallback(() => {
  setNumber(number + 1)
}, [number])

funccount.add(incrementCounter);
funccount.add(decrementCounter);
funccount.add(incrementNumber);
alert(funccount.size);

  return (
    <div>
      Count: {count}
      <button onClick={incrementCounter}>
         Increase counter
      </button>
      <button onClick={decrementCounter}>
         Decrease Counter
      </button>
      <button onClick={incrementNumber}>
         increase number
      </button>
    </div>
  )
}

export default App;
```

**输出:**从下面的输出可以看出，当我们改变状态‘计数’时，两个函数将重新实例化，因此集合大小将增加 2，当我们更新状态‘名称’时，只有一个函数将重新实例化，集合大小将仅增加 1。

![](img/1c6eac09510232943a89124e9fbd9b10.png)