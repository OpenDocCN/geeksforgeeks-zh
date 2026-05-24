# 开发者最常犯的错误

> 原文:[https://www . geesforgeks . org/最常见的错误-反应-开发人员-制造/](https://www.geeksforgeeks.org/most-common-mistakes-that-react-developers-make/)

React 是一个用于构建用户界面的 JavaScript 库。在开发 React 应用的过程中，我们会犯很多常见的错误。这不是我们犯错误的问题，但如果我们不通过犯错误来学习一些东西，这永远是一个比其他任何事情都更大的问题。从错误中学习应该是我们作为开发人员的态度。在本文中，我们将了解 React 开发人员最常犯的 5 大错误。

**1。未能正确应用结构**

编写应用程序有两种方式:将所有东西放在一个大组件中(**整块**)，或者将所有东西拆分成更小的组件(**微服务**)。初学者往往构建不够，这使得他们的代码更加复杂。

React 最重要的特性之一是组件。根据设计，React 应用程序被设计成独立的组件。请考虑以下页面:

![](img/170cce86792780dc2f7fe0de600c1246.png)

为了使用 React 正确构建这个页面，我们应该把它看作是一组组成页面的组件，而不是整个页面本身。因此，通过这种方式，我们可以创建不同的组件集，我们可以将它们集成在一起组成整个页面。

**示例:**大组件可能如下图所示:

## java 描述语言

```jsx
import React from 'react';

function MyComponent() {
  return (  
    <div>  
      <div>    
        { // Header related HTML }
      </div>   

      <div>
        { // Chart related HTML }
      </div>

      <div>    
        { //Footer related HTML }
      </div>   

    </div>  
  );  
}
```

这种做法使代码变得更加复杂，您可能很难调试一个大组件。因此，您应该投入时间来分离应用程序中各种相互依赖的部分，并将这些部分提取并移动到不同的组件中。这使得您的组件在需要时更容易维护和重用。

我们可以按照以下方式将上述组件分为三个不同的组件:

*   **表头组件:**

    ## Header.js

    ```jsx
    import React, { Component } from 'react';

    class Header extends Component {
      render() {
        return (
          <div>
            { // Header related HTML }
          </div>
        );
      }
    }

    export default Header;
    ```

*   **图表组件:**

    ## 图表. js

    ```jsx
    import React, { Component } from 'react';

    class Chart extends Component {
      render() {
        return (
          <div>
            { // Chart related HTML }
          </div>
        );
      }
    }

    export default Chart;
    ```

*   **页脚组件:**

    ## 页脚. js

    ```jsx
    import React, { Component } from 'react';

    class Footer extends Component {
      render() {
        return (
          <div>
            { // Footer related HTML }
          </div>
        );
      }
    }

    export default Footer;
    ```

**主应用:**我们已经将我们的应用程序分成了三个不同的组件，现在我们可以通过以下方式将其集成到我们的应用程序中。这种方法节省了您的时间，并使您的代码可重用且易于调试。

## java 描述语言

```jsx
// MyComponent.js
import React from "react";
import Header from "./Header"
import Chart from "./Chart"
import Footer from "./Footer"

function MyComponent() {
  return (
    <div>
      <Header/>
      <Chart/>
      <Footer/>
    </div>
  );
}
```

**2。不大写组件名称**

每个 React 组件的名称必须以大写字母开头，否则如果我们使用该组件，浏览器会将该组件视为一个内置元素，如 span 或 div，您可能会收到警告。

**示例:**如果我们创建一个名为 chart 的组件并尝试渲染<图表/ >，React 将忽略该组件，我们将得到以下警告:

> **【警告】**
> 标签<图表>在此浏览器中无法识别。如果您打算渲染一个 React 组件，请以大写字母开始它的名称。

为了避免这种警告，请始终以大写字母作为 React 组件名称的开头。

**3。使用类代替类名**

在 React 中指定元素的类名时，初学者使用类而不是类名，这会给他们带来错误。因为 class 关键字已经在 JavaScript 中保留了，而 JSX 只不过是 JavaScript 的扩展，这就是 React 使用 className 而不是 class 的原因。

**示例:**

## java 描述语言

```jsx
import React from 'react';

function MyComponent() {
  return (  
    <div class="yellow-bg">  
    <h1>Hello World!</h1>
    </div>  
  );  
}
```

您可能认为上面的代码是有效的，但它是无效的代码，因为它使用一个类来指定元素的类名。为了避免错误，请使用类名来指定元素的类名。一些有经验的 React 开发人员也经常重复这个错误，所以请始终记住，class 关键字已经在 JavaScript 中保留了，因此 React 使用 className 来指定元素的类名。

**4。从类组件调用钩子**

钩子允许我们编写更好的 React 代码，并利用功能组件内部的状态和组件生命周期方法。但是有时，您可能会从类组件中调用钩子，并且您可能会得到错误。

React 提供了很多钩子，比如 useEffect、useState、useRef 等等。但是我们只能在功能组件内部使用这些钩子。

**示例:**

## java 描述语言

```jsx
import React,{Component} from 'react';

class MyComponent extends Component {

  render(){

      const [sampleState, setState] = useState('hello world');

      return (  
        <div class="yellow-bg">  
        <h1>{sampleState}</h1>
        </div>  
      );
   }
}
export default MyComponent
```

上面的代码看起来可能是有效的，但是它是无效的代码，因为在上面的代码中，useState 是从类组件中调用的。由于 useState 是一个钩子，所以上面的代码会给我们以下错误:

**注意:**React Hook“useState”不能在类组件中调用。必须在函数组件中调用 React Hooks。

所以使用钩子的正确方法是从函数组件调用它，如下所示:

## java 描述语言

```jsx
import React from 'react';

function MyComponent() {

  const [sampleState, setState] = useState('hello world');

  return (  
    <div class="yellow-bg">  
    <h1>{sampleState}</h1>
    </div>  
  );  
}

export MyComponent
```

**5。使用阵图法时不使用关键道具**

我们通常使用数组映射方法来显示存储在数组中的项目列表。我们可以用以下方式呈现项目列表:

## java 描述语言

```jsx
const lists = ['obj1', 'obj2', 'obj3'];

render() {
  return (
    <ul>
      {lists.map(item =>
        <li>{item}</li>)}
    </ul>
  );
}
```

上述代码可能适用于较小的应用程序。但是有时您可能会在尝试修改或删除列表中的项目时遇到渲染问题。React 必须跟踪 DOM 上的每个列表元素。因此，关键道具有助于 React 识别哪些项目已被修改或删除。要给数组中的每个元素一个唯一的 id，需要一个密钥道具。在使用数组映射方法时，我们通常不使用关键道具，但有时它可能会产生一些问题。

我们可以在下面的列表中为您的所有 lemon 添加一个密钥:

## java 描述语言

```jsx
const lists = ['obj1', 'obj2', 'obj3'];

render() {
  return (
    <ul>
      {lists.map(item =>
        <li key={item}>{item}</li>)}
    </ul>
  );
}
```