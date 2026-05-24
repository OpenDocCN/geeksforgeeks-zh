# 反应堆中的可访问性

> 原文:[https://www.geeksforgeeks.org/accessibility-in-reactjs/](https://www.geeksforgeeks.org/accessibility-in-reactjs/)

**ReactJS 可访问性:**可访问性是一种必要的工具或方式，用户可以通过可点击的按钮或下拉菜单或空格来写评论等功能轻松访问网站。

React 完全支持构建可访问的网站，通常使用标准的 HTML 技术。

**语义 HTML:** 语义 HTML 是 web 可访问性的基础，因为它们为开发人员和测试团队提供了便利。有时我们使用太多的< div >来包装我们的代码以使其工作，这反过来又造成了理解代码从而调试代码的问题。

因此，有时我们会使用像<>或<fragment>这样的片段来对我们有利。记住我们需要先导入片段。</fragment>

**示例:**

## java 描述语言

```jsx
import React, { Fragment } from 'react';
function studentList() {
  return (
    <Fragment>      
        <dt>24</dt>
          <dd> Stefen Sen</dd>
    </Fragment>  );
}
```

**标签属性:**有很多标签属性要反应。标签属性属性设置或返回标签的属性值。

标签属性之一是 htmlFor 属性，它为属性设置或返回的值。

**例:**

## Javascript

```jsx
// Using htmlFor in label of form 
// Remember the camelCase writing

<label htmlFor="name">Name:</label>
<input id="name" type="text" name="name"/>
```

**键盘焦点:**键盘焦点指的是 web 应用程序中从用户接受来自键盘的数据或动作的部分，通常指的是 DOM 输入。通常在用户填写表单或任何类型的输入字段时使用。

有时 TAB 用于进入表单中的下一个条目。

**反应中的引用:**反应中的引用更像是反应的关键。它是 react 中的一个属性，可以存储对特定 react 元素的引用。它提供了一种访问 React 元素以供参考的方法，当我们需要在不使用 prop 的情况下更改子元素时会用到它。

**例:**

## Javascript

```jsx
class MyComponent extends React.Component {  
  constructor(props) {  
    super(props);  
    this.callRef = React.createRef();  
  }  
  render() {  
    return <div ref={this.callRef} />;  
  }  
}
```

**鼠标和指针事件:**大多数时候我们使用鼠标或指针设备访问互联网，所以我们必须非常清楚鼠标或指针事件，如点击、双击、悬停等。

**示例:**此示例用于外部点击。

## Javascript

```jsx
import React from 'react';
import ReactDOM from 'react-dom';

function clickMe() {
  alert("You Just Clicked");
}

const clickFun = (
  <button onClick={clickMe}>Click Me!</button>
);

ReactDOM.render(clickFun, document.getElementById('root'));
```

**示例:**onbulr 和 onFocus 的代码。

## Javascript

```jsx
function App() {
  const [fieldValue, setFieldValue] = React.useState('');

  const handleBlur = (e) => setFieldValue(e.target.value);

  console.log(fieldValue);

  return <input onBlur={handleBlur} />;
}

function App() {
  const [fieldValue, setFieldValue] = React.useState("");

  const handleChange = (e) => setFieldValue(e.target.value);

  console.log(fieldValue);

  return <input onChange={handleChange} />;
}
```

这段代码向指针设备和键盘用户公开了该功能。还要注意增加了 aria-*道具来支持屏幕阅读器用户。为了简单起见，启用弹出选项的箭头键交互的键盘事件还没有实现。