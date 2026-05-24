# 【React Native 和 React 有什么区别？

> 原文:[https://www . geesforgeks . org/react-native-react 之间的区别是什么/](https://www.geeksforgeeks.org/what-is-the-difference-between-react-native-and-react/)

**React 或 ReactJS 基本介绍:**是脸书为了更好的 UI 开发和高效的 DOM 操作而创建的开源 Javascript 库。React 有一个虚拟 DOM 的概念。当从服务器接收到任何数据时，该虚拟 Dom 已经相应地被修改，然后该更新的虚拟 DOM 通过某种算法与真实 DOM 匹配，并且只有真实 DOM 的不同于虚拟 DOM 的那些部分被更新。

**反作用**

1.  React 用于创建网站、网络应用程序、SPa 等。
2.  React 是一个用于创建用户界面层次结构的 Javascript 库。
3.  负责 UI 组件的渲染，被认为是 MVC 框架的 V 部分。
4.  React 的虚拟 DOM 比传统的完全刷新模型更快，因为虚拟 DOM 只刷新页面的一部分，从而减少了页面刷新时间。
5.  React 使用组件作为 UI 的基本单元，可以重复使用，这样可以节省编码时间。
6.  简单易学。

**反应样本代码**

```jsx
import React, { Component } from 'react';
import ReactDOM from 'react-dom';

// every component is created by 
// extending the React Component class. 
class Clock extends React.Component { 
  constructor(props) {
    super(props);
    // constructor creates an instance of this class.
    this.state = {date: new Date()};
  }

  componentDidMount() {
  // this function is called immediately 
  // after component is mounted on DOM.
    this.timerID = setInterval(
      () => this.tick(),
      1000
    );
  }

  componentWillUnmount() {
  // called before component will unmount from DOM.
    clearInterval(this.timerID);
  }

  tick() {
  // this function is used to update the 
  // state of Clock component.
    this.setState({
      date: new Date()
    });
  }

  render() {
    return (
      <div>
        <h1>Today Date and Time</h1>
        <h2>It is {this.state.date.toLocaleTimeString()}.</h2>
      </div>
    );
  }
}
// code will not run needs specific environment setup
ReactDOM.render(
  <Clock />,
  document.getElementById('root')
);
```

**React Native 的基本介绍:**
REACT Native 仅使用 JavaScript 即可帮助您创建真实且令人兴奋的移动应用程序，这是安卓和 iOS 平台设备都支持的。只需编写一次代码，REACT Native 应用程序就可以在 iOS 和安卓平台上使用，这有助于节省大量开发时间。发现了脸书创造的巨大人气。REACT Native，如今拥有庞大的社区支持。React Native 建立在 ReactJS 之上，是 AngularJS 的一个很好的替代。虽然“反应原生”和“反应”有一些相似之处和不同之处。
**反应原生**

1.  React Native 是一个用于创建跨平台 Native 应用程序的框架。这意味着你可以创建本地应用程序，同样的应用程序将在安卓和 ios 上运行。
2.  React native 拥有 React 的所有优点
3.  React native 允许开发人员以网络风格的方式创建原生应用程序。
4.  前端开发者很容易成为移动开发者。

**样本反应原生代码**

```jsx
import React, { Component } from 'react';
import { Text, View } from 'react-native';

class ReactNative extends Component {
  render() {
    return (
      // it is a container, layout support with flexbox think 
      // of it like a div with a container class.
      <View>
        <Text>// A react component for displaying text.
          If you like React on the web, you'll like React Native.
        </Text>
        <Text>
          You just use native components like 'View' and 'Text',
          instead of web components like 'div' and 'span'.
        </Text>
      </View>
    );
  }
}
```