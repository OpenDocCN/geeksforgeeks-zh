# 【ReactJS ES6 语法与 ES5 相比有何不同？

> 原文:[https://www . geesforgeks . org/how-reactjs-es6-语法不同-与-es5 相比/](https://www.geeksforgeeks.org/how-reactjs-es6-syntax-is-different-compared-to-es5/)

在本文中，我们将学习 ReactJs 中 ES6 和 ES5 语法的区别。ES6 和 ES5 都是开发行业的 Javascript 脚本语言。ECMA 脚本或 ES 是一种由 ECMA 国际公司制造的商标脚本语言。欧洲计算机制造协会或 ECMA 被用于全球网络的客户端脚本。ES5 于 2009 年发布，ES6 于 2015 年发布。ES5 很好，但是很长。就代码优化和可读性而言，新的 ES6 是对 ES5 的重大更新和增强。

**是 5∶**

*   ES5 的完整形式是 ECMA 脚本 5，开发于 2009 年。
*   这里允许的数据类型有*数字、字符串、null、布尔值、未定义的*、*、*和*符号。*
*   ES5 使用 ***要求*** 模块导入我们脚本文件中的任何成员模块。

**语法:**

```jsx
var React = require('react'); // ES5
```

*   在 ES5 中，我们只能使用 ***var*** 来定义全局范围内的变量。
*   使用 ***模块将任何组件导出为模块。导出*** 关键字。

**语法:**

```jsx
module.exports = Component; // ES5
```

*   ES5 使用函数关键字和 return 关键字来定义函数。

**语法:**

```jsx
// ES5
var sum = function(x, y) {
    return x + y;
};
```

*   ES5 使用***createReactClass()***或***React . createclass()***API 创建 react 组件类，并使用***getinitialistate()***方法定义 react 组件状态。
*   对象操作的处理速度很慢。
*   ES5 的性能缺乏新的特性，因此相对较低。
*   ES5 拥有巨大的社区支持，因为它已经使用了很长时间。

**创建反应应用程序并安装模块:**

**步骤 1:** 使用以下命令创建一个反应应用程序:

```jsx
npx create-react-app foldername
```

**步骤 2:** 创建项目文件夹(即文件夹名)后，使用以下命令移动到该文件夹:

```jsx
cd foldername
```

**项目结构:**如下图。

![](img/e3dd5555048e70b07ee15f52e1c03e9f.png)

**示例:**现在在 App.js 文件中写下以下代码。在这里，App 是我们编写代码的默认组件。

**示例 1:使用 React 的 ES5 语法**

*T1 文件内*

## java 描述语言

```jsx
var React = require("react"); // ES5
var ReactDOM = require("react-dom"); // ES5
var createReactClass = require("create-react-class"); // ES5

// ES5 Syntax
var CountComp = createReactClass({
  getInitialState: function () {
    return {
      counter: 0,
    };
  },
  Increase: function () {
    this.setState({
      counter: this.state.counter + 1,
    });
  },
  Decrease: function () {
    this.setState({
      counter: this.state.counter - 1,
    });
  },
  render: function () {
    return (
      <div>
        <button onClick={this.Increase}>
          Count increase
        </button>
        <h1> {this.state.counter} </h1>
        <button onClick={this.Decrease}>
          Count decrease
        </button>
      </div>
    );
  },
});

// ES5 Syntax
var Component = createReactClass({
  render: function () {
    return (
      <div>
        <CountComp />
      </div>
    );
  },
});

ReactDOM.render(<Component />, 
    document.getElementById("root"));
```

**输出:**

<video class="wp-video-shortcode" id="video-689547-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210930204713/es.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210930204713/es.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210930204713/es.mp4)</video>

**是 6∶**

*   ES6 的完整形式是 ECMA 剧本 6，于 2015 年出版。
*   这里允许的数据类型有*数字、字符串、null、布尔值、未定义的*、*、*和*符号。*
*   ES6 使用 ***导入*** 模块来导入我们脚本文件中的任何成员模块。

**语法:**

```jsx
import React from 'react'; // ES6
```

*   在 ES6 中，我们还可以使用 let 和 ***const*** 在本地定义一个变量。
*   Es5 使用 ***导出默认*** 关键字将任何组件导出为模块。

**语法:**

```jsx
export default Component; // ES6
```

*   在 ES6 中，我们不需要使用函数关键字来定义函数。在 ES6 中使用 Arrow 函数使其更加紧凑。这是一个用“= >”语法描述的函数。

**语法:**

```jsx
var sum = (x,y)=>{ return x+y };// ES6
```

*   ES6 使用扩展 ***React 的 ES6 类。组件*** 并使用构造函数中的**定义一个 react 组件状态()。**
*   **由于对象析构，对象操作很快。这个过程通过允许模式匹配来加强绑定模式。**
*   **由于添加了高级功能和代码优化，ES6 提供了高性能。**
*   **ES6 的社区支持比 ES5 少，因为它是 ES5 的最新更新，并非所有浏览器都支持它。**

****示例 2:使用 React 的 ES6 语法****

*****索引内*** **。** ***js*** 文件**

## **java 描述语言**

```jsx
import React from "react"; // ES6
import ReactDOM from "react-dom"; // ES6

let CountComp = (Compprop) =>
  class extends React.Component {
    constructor(props) {
      super(props);
      this.state = {
        counter: 0,
      };
      this.Increase = this.Increase.bind(this);
      this.Decrease = this.Decrease.bind(this);
    } // ES6 Syntax

    // ES6 Syntax
    Increase() {
      this.setState({
        counter: this.state.counter + 1,
      });
    }
    Decrease() {
      this.setState({
        counter: this.state.counter - 1,
      });
    }
    render() {
      return (
        <div>
          <Compprop
            {...this.state}
            increase={this.Increase}
            decrease={this.Decrease}
          />
        </div>
      );
    }
  };

// ES6 Syntax
const Button = (props) => {
  return (
    <div>
      <button onClick={props.increase}>
        Count increase
      </button>
      <h1> {props.counter} </h1>
      <button onClick={props.decrease}>
        Count decrease
      </button>
    </div>
  );
};

// ES6 Syntax
let CompClick = CountComp(Button);

const Component = () => {
  return (
    <div>
      <CompClick />
    </div>
  );
};

ReactDOM.render(<Component />, 
  document.getElementById("root"));
```

****输出:****

**<video class="wp-video-shortcode" id="video-689547-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210930204713/es.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20210930204713/es.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210930204713/es.mp4)</video>**

****ES5 和 ES6 的区别:****

<figure class="table">

|  | 反应堆 5 | **反应堆 6** |
| 1。 | The complete form of ES5 is ECMA script 5. | The complete form of ES6 is ECMA script 6. |
| 2。 | Supported data types: number, string, null, Boolean, undefined. | Supported data types: number, string, null, Boolean, undefined, symbol. |
| 3。 | ES5 uses var to declare a variable. | ES6 has an additional feature called let and const, which is used to define a variable. |
| 4。 | We can't import a JSX file into another file in ES5. | In ES6, we can import a jsx file into another file. |
| 5。 | ES5 uses the Require js module to contain react modules or components. | ES6 uses import modules to contain react modules or components. |
| 6。 | ES5 uses function keyword and return keyword to define functions. | In ES6, we don't need to use function keywords to define functions. Use the Arrow function in ES6 to make it more compact. |
| 7。 | Props are implicitly defined in ES5, and we implicitly bind "this" to the function. | In ES6, we explicitly pass props through the constructor () and explicitly bind "this" to the function inside the constructor. |
| 8。 | Es5 does not need to use the same tower of babel. | Es6 needs to use the same tower of babel. |
| 9。 | In ES5, we need to use commas to separate functions or methods within a class. | In ES6, we don't need commas to separate functions or methods within a class. |
| 10。 | Object processing speed is slow. .. | Due to the destruction of the object, the object operates quickly. |
| Eleven. | ES5 performance lacks new features, so it is relatively low. | With the addition of advanced functions and code optimization, ES6 provides high performance. |
| Twelve. | ES5 has huge community support because it has been used for a long time. | ES6 has less community support than ES5 because it is the latest update of ES5. |

</figure>