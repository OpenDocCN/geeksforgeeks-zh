# 反应钢筋箱组件

> 原文:[https://www.geeksforgeeks.org/react-rebass-box-component/](https://www.geeksforgeeks.org/react-rebass-box-component/)

**React Rebass** 是一个前端框架，设计时考虑到了 React。在本文中，我们将了解如何在 React Rebass 中使用 Box 组件。盒子是每个开发都需要的重要组件。因此，为了创建一个盒子组件，我们可以导入 Rebass Box 组件。

盒子组件用来制作一个盒子，我们可以在里面添加一些内容和元素。

**语法:**

```jsx
<Box>
    Content
</Box>
```

**创建反应应用程序并安装模块:**

**步骤 1:** 使用以下命令创建一个 React 应用程序。

```jsx
npx create-react-app foldername
```

**步骤 2:** 创建项目文件夹(即文件夹名)后，使用以下命令移动到该文件夹。

```jsx
cd foldername
```

**步骤 3:** 在给定的目录中安装 React Rebass。

```jsx
 npm install --save react-toolbox
```

**项目结构**:如下图。

![](img/f04ae0d8b722a9fff0bd9bd138b29c23.png)

文件结构

**示例 1:** 这是展示如何使用 Box 组件的基本示例。

## App.js

```jsx
import React from "react";
import { Box } from "rebass";

const gfg = (props) => {
    return (
        <div id="gfg">
            <br />
            <Box
                p={5}
                fontSize={5}
                width={[0.5]}
                color="white"
                bg="Green"
                textAlign="center"
            >
                GeeksforGeeks
            </Box>
        </div>
    );
};

export default gfg;
```

**运行应用程序的步骤:**使用以下命令从项目的根目录运行应用程序。

```jsx
npm start
```

**输出:**

![](img/e27ca3103dbdf4048c02233b5793e1ce.png)

**参考:**T2】https://rebassjs.org/box