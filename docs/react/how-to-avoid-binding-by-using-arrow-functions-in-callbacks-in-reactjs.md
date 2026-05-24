# 如何在 ReactJS 中的回调中使用箭头函数避免绑定？

> 原文:[https://www . geeksforgeeks . org/如何通过使用回叫中的箭头函数来避免绑定/in-reactjs/](https://www.geeksforgeeks.org/how-to-avoid-binding-by-using-arrow-functions-in-callbacks-in-reactjs/)

在 React 基于类的组件中，当我们使用事件处理程序回调时，特别注意“this”关键字是非常重要的。在这些情况下，当回调函数实际被调用时，上下文是未定义的，这就是为什么我们必须绑定它的上下文。现在如果绑定每个类的所有方法就很烦人了。我们可以使用内联箭头函数来代替绑定，因为箭头函数没有自己的值，而是使用父值或公共值。使用内联箭头函数，我们可以每次都摆脱烦人的方法绑定，而且代码看起来非常紧凑和有条理。

**示例 1:** 这个示例说明了如何在回调中使用箭头函数

*   **index.js:**

    ## java 描述语言

    ```jsx
    import React from 'react'
    import ReactDOM from 'react-dom'
    import App from './App'

    ReactDOM.render(<App />, document.querySelector('#root'))
    ```

*   **App.js :**

    ## java 描述语言

    ```jsx
    import React, { Component } from 'react'

    class App extends Component {
      // Default props
      static defaultProps = {
        courceContent : [
          'JSX', 'React Props', 'React State', 'React Lifecycle Methods',
          'React Event Handlers', 'React Router', 'React Hooks', 'Readux',
          'React Context'
        ]
      }

      constructor(props){
        super(props)

        // Set initial state
        this.state = {msg : 'React Cource', content:''}
      }

      // Return an unordered list of contents
      renderContent(){
        return (
          <ul>
            {/* map over all the contents and
                return some JSX for each  */}
            {this.props.courceContent.map(content => (
              <li>{content}</li>
            ))}
          </ul>
        ) 
      }

      render(){
        const button = !this.state.content && 
        <button 
          // Arrow function in callback
          onClick={() => {
            // Update state
            this.setState({
              msg : 'Cource Content',
              content : this.renderContent()
            })
          }}
        >
          Click here to know contents!
        </button>
        return (
          <div>

    <p>{this.state.msg}</p>

    <p>{this.state.content}</p>

            {button}
          </div>
        )
      }
    }

    export default App
    ```

**输出:**

![](img/c31c7fa78469d9e6815b599100a06707.png)

**例 2 :**

*   **index.js :**

    ## java 描述语言

    ```jsx
    import React from 'react'
    import ReactDOM from 'react-dom'
    import App from './App'

    ReactDOM.render(<App />, document.querySelector('#root'))
    ```

*   **App.js :**

    ## java 描述语言

    ```jsx
    import React, { Component } from 'react'

    class App extends Component{
      // Default props 
      static defaultProps = { 
        name : ['John', 'Alex', 'Bob'] 
      } 
      constructor(props){ 
        super(props) 
        // Nnitialize count state 
        this.state = {msg : 'Hi There', count:0}
      } 

      render(){ 
        return( 
          <div> 
            <h3>Greetings!</h3>     

    <p>{this.state.msg}</p>

            <button 
              // Arrow function in callback
              // does not required explicit binding
              onClick={() => {
                this.setState(st => (
                  st.msg = `${st.msg}, ${this.props.name[st.count]}`,
                  st.count += 1
                ))
              }}
            > 
              Say greeting to employees! 
            </button> 
          </div>    
        )  
      } 
    }
    export default App
    ```

**输出:**

![](img/fd71dabfae512d331536d7921aede42a.png)