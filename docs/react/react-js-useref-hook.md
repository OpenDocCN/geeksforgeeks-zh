# 反应 JS useRef 钩子

> 原文:[https://www.geeksforgeeks.org/react-js-useref-hook/](https://www.geeksforgeeks.org/react-js-useref-hook/)

useRef 钩子是 React 16.8 的新增功能。在继续阅读这篇文章之前，有一个先决条件要知道 [ref](https://www.geeksforgeeks.org/reactjs-refs/) in react。
useRef 是一个钩子，允许在功能组件中直接创建对 DOM 元素的引用。

**语法:**

```jsx
const refContainer = useRef(initialValue);
```

useRef 返回一个可变的 Ref 对象。此对象有一个名为. current 的属性。该值保存在 refContainer.current 属性中。这些值是从返回对象的当前属性中访问的。那个。当前属性可以初始化为传递的参数 initialValue，例如 useRef(initialValue)。对象可以在组件的整个生命周期内保持一个值。

**示例**:如何使用 useRef 钩子访问 DOM。

## java 描述语言

```jsx
import React, {Fragment, useRef} from 'react';

function App() {

  // Creating a ref object using useRef hook
  const focusPoint = useRef(null);
  const onClickHandler = () => {
    focusPoint.current.value =
      "The quick brown fox jumps over the lazy dog";
      focusPoint.current.focus();
  };
  return (
    <Fragment>
      <div>
        <button onClick={onClickHandler}>
         ACTION
        </button>
      </div>
      <label>
       Click on the action button to
       focus and populate the text.
      </label><br/>
      <textarea ref={focusPoint} />
    </Fragment>
  );
};

export default App;
```