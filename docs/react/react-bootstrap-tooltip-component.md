# 反应引导工具提示组件

> Original: [https://www.geeksforgeeks.org/react-bootstrap-tooltip-component/](https://www.geeksforgeeks.org/react-bootstrap-tooltip-component/)

Reaction-Bootstrap 是一个前端框架，其设计考虑到了 Reaction。 工具提示组件用于在用户悬停、聚焦或点击元素时显示信息性文本。 我们可以在 ReactJS 中使用以下方法来使用 Reaction-Bootstrap 工具提示组件。

**工具提示道具：**

*   **arrowProps：**它用于定位工具提示箭头。
*   **id：**这只是可访问性所必需的 HTML*id*属性。
*   **放置：**用于设置工具提示的定位方向。
*   **Popper：**它是 Object 类型，指示工具提示元素的 Popper 属性。
*   **show：**表示工具提示是否打开。
*   **bsPrefix：**它是使用高度定制的引导程序css的安全通道。

**创建 Reaction 应用程序并安装模块：**

*   **步骤 1：**使用以下命令创建 Reaction 应用程序：

    ```jsx
    npx create-react-app foldername
    ```

*   **步骤 2：**创建项目文件夹(即 foldername**)后，**使用以下命令移动到该文件夹：

    ```jsx
    cd foldername
    ```

*   **步骤 3：**创建 ReactJS 应用程序后，使用以下命令安装所需的****模块：****

    ```jsx
    **npm install react-bootstrap 
    npm install bootstrap**
    ```

******项目结构：**如下所示。****

****![](img/f04ae0d8b722a9fff0bd9bd138b29c23.png)

项目结构**** 

******示例：**现在在**App.js**文件中写下以下代码。 在这里，App 是我们编写代码的默认组件。****

## ****App.js****

```jsx
**import React from 'react';
import 'bootstrap/dist/css/bootstrap.css';
import Tooltip from 'react-bootstrap/Tooltip';
import Button from 'react-bootstrap/Button';
import OverlayTrigger from 'react-bootstrap/OverlayTrigger'

export default function App() {
  return (
    <div style={{ display: 'block', width: 700, padding: 30 }}>
      <h4>React-Bootstrap Tooltip Component</h4>
      <OverlayTrigger
        delay={{ hide: 450, show: 300 }}
        overlay={(props) => (
          <Tooltip {...props}>
            Hii, I am a simple tooltip information!!!
          </Tooltip>
        )}
        placement="bottom"
      ><Button variant="warning">Tooltip Button</Button>
      </OverlayTrigger>,
    </div>
  );
}**
```

******运行应用程序的步骤：**使用以下命令从项目根目录运行应用程序：****

```jsx
**npm start**
```

******输出：**现在打开浏览器，转到***http://localhost:3000/***，您将看到以下输出：****

****![](img/cb065fc066a538788ee99607dbe524fc.png)****

******引用：**[https://react-bootstrap.github.io/components/overlays/#tooltips](https://react-bootstrap.github.io/components/overlays/#tooltips)****