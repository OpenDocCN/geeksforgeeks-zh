# 如何通过 API 取数使用 React app 创建随机笑话？

> 原文:[https://www . geesforgeks . org/如何创建-随机-笑话-使用-反应-应用-通过 API-获取/](https://www.geeksforgeeks.org/how-to-create-a-random-joke-using-react-app-through-api-fetching/)

在本教程中，我们将创建一个从外部应用编程接口获取数据(笑话)并将其显示在屏幕上的网站。我们将使用完全反应来建立这个网站。每次我们重新加载页面并点击按钮，一个新的笑话就会被 React 提取并呈现在屏幕上。当我们在这个项目中使用 React 时，我们不需要重新加载页面来显示提取的数据。

“按钮”组件。“应用程序”文件是一个功能组件，包含一个状态变量“笑话”，该变量最初设置为空字符串，根据笑话的状态，输出被呈现。如果玩笑包含空字符串，则组件输出“按钮”组件；如果玩笑不为空，则组件输出值。正在呈现的“按钮”组件也是一个输出按钮元素的导入功能组件。我们还向“按钮”组件传递了一些道具，这是一个名为 callAPI 的方法。

**先决条件:**本项目的先决条件是:

*   [反应](https://www.geeksforgeeks.org/react-js-introduction-working/)
*   [功能组件](https://www.geeksforgeeks.org/reactjs-functional-components/)
*   [ReactJS AJAX 和 API](https://www.geeksforgeeks.org/reactjs-ajax-and-api/)
*   [是 6](https://www.geeksforgeeks.org/introduction-to-es6/)

**创建这个应用的理由:**建立这样一个简单网站的目的是获得一些使用 API 的经验，因为它们或多或少都是相同的。该网站使用一个简单的界面，我们有一个按钮，当悬停时改变颜色，当点击时向一些外部应用编程接口发出请求并获取数据。

**示例:**使用命令 **npx create-react-app** 创建一个新的 React 项目。在同一个目录中，我们有一个文件 **index.js** ，它管理我们所有的组件，并将应用程序组件呈现在屏幕上。

*   **步骤 1(创建 Button.js):** 在开始使用 ReactJS 部件之前，创建组件 Button.js，该组件将分别用于返回 Button 和 App 组件。

    按钮组件接受道具并呈现按钮。我们在按钮上添加了一个事件监听器，当点击它时会调用函数 callAPI()。下一节将详细讨论 callAPI()函数。Button 组件非常简单，不需要太多解释。它只返回一个按钮元素。

    **按钮. js:**

    ## java 描述语言

    ```jsx
    // Import React (Mandatory Step).
    import React from "react";

        // Create a functional component
        const Button = (props) => {
            return <button onClick={props.callApi}>
             Hello Geek!!
             </button>;
        }

    // Export Button Component
    export default Button;
    ```

*   **App.js:** 这个文件将把作为容器工作的主 App 返回给所有其他组件。在这个项目中，我们只使用了功能组件，但是使用类组件也可以做到这一点。应用程序组件是所有其他组件的父组件。它返回一个包含条件语句的 div，如果 Joke 变量的值为空字符串("")，则返回 Button 组件，否则返回存储在带有段落标记的 Joke 中的字符串。

    首先，我们定义了一个初始化为""的状态变量。它已被销毁，因此我们可以直接访问可以用来更改笑话状态的笑话变量和设置笑话()。

    我们还有一个 callAPI()，它调用 API，获取响应，并将其传递给 json()，后者获取响应流并将其读取完成。它返回一个承诺，解析的结果是将正文文本解析为 JSON，这是一个数据类型对象、字符串等的 JavaScript 值。它返回一个对象，该对象具有一个名为 joke 的属性，可以使用 **data.joke** 进行访问，并且可以使用 console.log(data.joke) *登录到控制台。*然后我们使用设置笑话作为**数据来改变笑话变量的状态。**

    当我们将状态设置为 data.joke 时，react 会重新呈现整个组件。存储在“笑话”中的字符串显示在字符串上。

    ## java 描述语言

    ```jsx
    // Import React (Mandatory Step).
    import React from "react";
    // Import ReactDOM (Mandatory Step).
    import ReactDOM from "react-dom";

    // Import The Button Component from Button.js 
    import Button from "./Component/Button";

    const rootElement = document.getElementById("root");

    // Create a functional component
    const App = () => {
        // Declare a state variable
        const [Joke, setJoke] = React.useState("");

        const fetchApi = () => {
            // Fetching data from the API
                fetch("https://sv443.net/jokeapi/v2/joke/Programming?type=single")
                .then((res) => res.json())
                .then((data) => setJoke(data.joke));
          };

        return (
            // Return the Button Component with a conditional statement
            <div>{Joke === "" ? <Button callApi={fetchApi} /> : 
    <p>{Joke}</p>
    }</div>
          );
    }

    // Rendering the App Component.
    ReactDOM.render(
        <App />,
      rootElement
    );
    export default App
    ```

**输出:**我们的 app 现在已经完成并且可以工作了，虽然 app 很简单，但是对于理解如何在 react 中进行 API 调用以及操纵接收到的响应以在 app 中使用它有很大帮助。

![](img/7444cb6255af0ab7d15ea53f7cea41bd.png)