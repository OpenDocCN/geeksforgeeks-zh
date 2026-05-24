# 反应|条件渲染

> 原文:[https://www . geeksforgeeks . org/reactjs-conditional-rendering/](https://www.geeksforgeeks.org/reactjs-conditional-rendering/)

我们已经讨论了如何[创建组件](https://www.geeksforgeeks.org/reactjs-components/)、如何[渲染组件](https://www.geeksforgeeks.org/reactjs-rendering-elements/)、使用[属性](https://www.geeksforgeeks.org/reactjs-proptypes/)、使用[状态](https://www.geeksforgeeks.org/reactjs-state-react/)存储信息等等。在我们之前的文章中，我们还在 ReactJS 中开发了一个基本的[计算器应用程序](https://www.geeksforgeeks.org/reactjs-calculator-app-introduction/)。
可能会出现一种情况，我们想要基于某种条件渲染某样东西。例如，考虑处理登录/注销按钮的情况。这两个按钮具有不同的功能，因此它们将是独立的组件。现在，任务是如果用户登录，那么我们将必须呈现注销组件来显示注销按钮，如果用户没有登录，那么我们将必须呈现登录组件来显示登录按钮。这就是我们在 ReactJS 中所说的**条件渲染**。即创建多个组件，并根据某些条件进行渲染。这也是 React 支持的一种封装。
现在让我们在 React 中创建一个页面，该页面将有一条消息和一个按钮。如果用户未登录，该按钮将显示“登录”，如果用户登录，则显示“注销”。我们还将为该按钮添加一些功能，因为单击“登录”时，消息将显示“欢迎用户”，按钮将更改为“注销”，单击“注销”时，消息将更改为“请登录”，按钮将更改为“登录”。
为此，我们将创建一个名为“主页”的父组件、两个名为“登录”和“注销”的组件以及一个名为“消息”的组件。我们将使用一个名为“isLoggedIn”的状态变量来存储用户是否登录的信息。该变量的值将根据用户点击按钮而改变。*主页*组件将呈现*消息*组件以显示消息，并且它还将基于存储在*中的值呈现*登录*和*注销*中的组件之一。*消息*组件也会根据状态*的值返回不同的消息。
现在让我们看看完成上述任务的完整程序:**

打开您的 react 项目目录，从 src 文件夹中编辑 **Index.js** 文件:

**src index . js:**T2】

## java 描述语言

```jsx
import React from 'react';
import ReactDOM from 'react-dom';

// Message Component
function Message(props)
{
    if (props.isLoggedIn)
        return <h1>Welcome User</h1>;
    else
        return <h1>Please Login</h1>;
}

// Login Component
function Login(props)
{
   return(
           <button onClick = {props.clickFunc}>
               Login
           </button>
       );
}

// Logout Component
function Logout(props)
{
    return(
           <button onClick = {props.clickFunc}>
               Logout
           </button>
       );
}

// Parent Homepage Component
class Homepage extends React.Component{

    constructor(props)
    {
        super(props);

        this.state = {isLoggedIn : false};

        this.ifLoginClicked = this.ifLoginClicked.bind(this);
        this.ifLogoutClicked = this.ifLogoutClicked.bind(this);
    }

    ifLoginClicked()
    {
        this.setState({isLoggedIn : true});
    }

    ifLogoutClicked()
    {
        this.setState({isLoggedIn : false});
    }

    render(){

        return(

            <div>

                <Message isLoggedIn = {this.state.isLoggedIn}/>

                {
                    (this.state.isLoggedIn)?(
                    <Logout clickFunc = {this.ifLogoutClicked} />
                    ) : (
                    <Login clickFunc = {this.ifLoginClicked} />
                    )
                }

            </div>

            );
    }
}

ReactDOM.render(
    <Homepage />,
    document.getElementById('root')
);
```