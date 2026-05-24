# 重新获取语义用户界面转换门户插件

> 原文:[https://www . geeksforgeeks . org/reactjs-semantic-ui-transitionableportal-addons/](https://www.geeksforgeeks.org/reactjs-semantic-ui-transitionableportal-addons/)

语义用户界面是一个现代框架，用于为网站开发无缝设计。它为用户提供了轻量级的组件体验。它使用预定义的 CSS 和 JQuery 语言来整合到不同的框架中。

在本文中，我们将了解如何在 ReactJS 语义用户界面中使用 TransitionablePortal 插件。TransitionablePortal 加载项用于在页面上的任何位置呈现它。

**属性:**

*   **受控:**受控属性用于使受控 TransitionablePortal。对于控件，它用于定义转换。
*   **bsPrefix:** 这个道具用来表示 CSS 中某个组件的变化。它用于自定义引导 CSS。默认值是微调器，类型是字符串。
*   **大小:**道具的大小用来演示旋转器的大小。道具的大小用于组件大小的变化。尺码的类型是 sm。
*   **颜色:**颜色道具用来表示旋转器的颜色。
*   **类名:**类名道具用于表示 CSS 中组件样式的类名。
*   **children:** 用于在 React JS 中将 children 元素传递给这个组件。子类型是一个元素。

**语法:**

```jsx
<TransitionablePortal>Children content</TransitionablePortal>
```

**创建反应应用程序并安装模块:**

*   **步骤 1:** 使用以下命令创建一个反应应用程序。

    ```jsx
    npx create-react-app foldername
    ```

*   **步骤 2:** 创建项目文件夹(即文件夹名称)后，使用以下命令移动到该文件夹。

    ```jsx
    cd foldername
    ```

*   **Step 3:** Install semantic UI in your given directory.

    ```jsx
     npm install semantic-ui-react semantic-ui-css
    ```

    **项目结构**:如下图。

    ![](img/f04ae0d8b722a9fff0bd9bd138b29c23.png)

    **运行应用程序的步骤:**使用以下命令从项目的根目录运行应用程序。

    ```jsx
    npm start
    ```

    **示例 1:** 这是展示如何使用 TransitionablePortal 插件的基本示例。

    ## App.js

    ```jsx
    import React, { Component } from 'react'
    import { Button, Grid, Header, Segment, 
        TransitionablePortal } from 'semantic-ui-react'

    const styleLink = document.createElement("link");
    styleLink.rel = "stylesheet";
    styleLink.href = 
    "https://cdn.jsdelivr.net/npm/semantic-ui/dist/semantic.min.css";
    document.head.appendChild(styleLink);

    export default class 
      TransitionablePortalExampleTransitionablePortal 
      extends Component {
      state = {

        open: false,
      }

      Open = () => {
        this.setState({ open: true })

      }

      Close = () => {
        this.setState({ open: false })

      }

      render() {
        const {  open } = this.state

        return (
          <div id='gfg'>
          <Grid columns={2}>
            <Grid.Column>
              <TransitionablePortal
                closeOnTriggerClick
                openOnTriggerClick
                trigger={
                  <Button
                    content={open ? 'Close TransitionablePortal' 
                                  : 'Open TransitionablePortal'}
                    negative={open}
                    positive={!open}
                  />
                }
                onOpen={this.Open}
                onClose={this.Close}
              >
                <Segment
                  style={{
                    left: '32%',
                    position: 'fixed',
                    top: '2%',
                    zIndex: 1000,
                  }}
                >
                  <Header><h1>GeeksforGeeks</h1></Header>
                  <p>Computer Science Portal</p>
                </Segment>
              </TransitionablePortal>
            </Grid.Column>
          </Grid>
          </div>
        )
      }
    }
    ```

    ## index.css

    ```jsx
    #gfg {
        margin: 40px;
    }
    ```