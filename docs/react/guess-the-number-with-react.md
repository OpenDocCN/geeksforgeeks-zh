# 用 React

猜数字

> 原文:[https://www.geeksforgeeks.org/guess-the-number-with-react/](https://www.geeksforgeeks.org/guess-the-number-with-react/)

我们创建了两个组件应用程序和结果。应用程序组件包含所有的逻辑，它是有状态的，结果组件只根据用户的猜测在页面上显示适当的消息。应用程序组件有一个受控的输入字段，用户可以在其中输入和猜测数字。我们给 App 组件**‘secret’**设置了一个默认道具，它保存了所需的秘密号，并且是随机生成的。应用程序组件将输入字段的值和密码传递给结果组件。结果组件相应地显示猜测的数字是高或低或正确的适当消息。

**先决条件:**

*   [React 基础知识](https://www.geeksforgeeks.org/react-js-introduction-working/#:~:text=A%20react%20application%20is%20made,out%20of%20simple%20building%20blocks.)
*   [设置开发环境](https://www.geeksforgeeks.org/reactjs-setting-development-environment/)

**示例:**这里我们将根据我们的要求编辑 index.html 文件和 app.js 文件。对于结果，我们将创建一个组件并设计输出组件。

*   **index.js:**

## java 描述语言

```jsx
import React from 'react'
import ReactDOM from 'react-dom'
import App from './App'

ReactDOM.render(<App />, document.querySelector('#root'))
```

*   **app.js :**

## java 描述语言

```jsx
import React, { Component } from 'react'
import Result from './Result'

class App extends Component{

  static defaultProps =  {
    secret : Math.floor(Math.random() * 20) + 1
  }

  constructor(props){
    super(props)
    this.state = { term : '' }

    this.handleChange = this.handleChange.bind(this)
  }

  handleChange(event){
    this.setState({
      [event.target.name] : event.target.value
    })
  }

  render(){
    return (
      <div>
        <div>
          <label htmlFor='term'>
            Guess Number between 1 to 20
          </label>
        </div>
        <input
          id='term'
          type='text'
          name='term'
          value={this.state.term}
          onChange={this.handleChange}
        />

        <Result term={this.state.term}
            secretNum={this.props.secret} />
      </div>
    )
  }
}
export default App
```

*   **Result.js:** 这个组件是为结果创建的。

## java 描述语言

```jsx
import React from 'react'

const Result = ({ term , secretNum }) => {
  let result;
  if(term){
    if(secretNum > term){
      result = 'You guessed Lower'
    }
    else if(secretNum < term){
      result ='You guessed Higher'
    }
    else{
      result ='Yippee, guessed it!'
    }
  }
  return <h3>{result}</h3>
}

export default Result
```

**输出:**

![](img/cd46299a032491b4867c696a20ae450c.png)

猜数字应用