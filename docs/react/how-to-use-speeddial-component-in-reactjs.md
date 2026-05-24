# 如何在 ReactJS 中使用快速拨号组件？

> 原文:[https://www . geeksforgeeks . org/如何使用-speed dial-in-component-reactjs/](https://www.geeksforgeeks.org/how-to-use-speeddial-component-in-reactjs/)

快速拨号是用户的一个快速操作按钮，用户可以点击它并轻松访问拨号中提供的各种选项。React 的 Material UI 有这个组件可供我们使用，非常容易集成。我们可以在 ReactJS 中使用以下方法来使用快速拨号组件。

**创建反应应用程序并安装模块:**

*   **步骤 1:** 使用以下命令创建一个反应应用程序:

    ```jsx
    npx create-react-app foldername
    ```

*   **步骤 2:** 创建项目文件夹(即文件夹名**)后，使用以下命令移动到该文件夹中:**

    ```jsx
    cd foldername
    ```

*   **步骤 3:** 创建 ReactJS 应用程序后，使用以下命令安装 **material-ui** 模块:

    ```jsx
    npm install @material-ui/core
    npm install @material-ui/icons
    npm install @material-ui/lab
    ```

**项目结构:**如下图。

![](img/f04ae0d8b722a9fff0bd9bd138b29c23.png)

项目结构

**示例:**现在在 **App.js** 文件中写下以下代码。在这里，App 是我们编写代码的默认组件。

## App.js

```jsx
import React from 'react';
import SpeedDial from '@material-ui/lab/SpeedDial';
import SpeedDialAction from '@material-ui/lab/SpeedDialAction';
import ShareIcon from '@material-ui/icons/Share';
import SpeedDialIcon from '@material-ui/lab/SpeedDialIcon';
import EditIcon from '@material-ui/icons/Edit';
import PrintIcon from '@material-ui/icons/Print';

export default function App() {

  const [open, setOpen] = React.useState(false);
  return (
    <div style={{ display: 'block', padding: 30 }}>
      <h4>How to use SpeedDial Component in ReactJS?</h4>
      <SpeedDial
        ariaLabel="SpeedDial Component Demo"
        style={{
          left: 125,
          bottom: 125,
          position: 'absolute',
        }}
        icon={<SpeedDialIcon openIcon={<EditIcon />} />}
        onClose={() => {
          setOpen(false);
        }}
        onOpen={() => {
          setOpen(true);
        }}
        open={open}
      >
        {[
          { icon: <ShareIcon />, name: 'Share' },
          { icon: <PrintIcon />, name: 'Print' },
        ].map((action) => (
          <SpeedDialAction
            icon={action.icon}
            key={action.name}
            onClick={() => {
              setOpen(false);
            }}
            tooltipTitle={action.name}
          />
        ))}
      </SpeedDial>
    </div>
  );
}
```

**运行应用程序的步骤:**从项目的根目录使用以下命令运行应用程序:

```jsx
npm start
```

**输出:**现在打开浏览器，转到***http://localhost:3000/***，会看到如下输出:

![](img/8acef0ebcce1201ecbc30e70d432cdca.png)

**参考:**T2】https://material-ui.com/components/speed-dial/