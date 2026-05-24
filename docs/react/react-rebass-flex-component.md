# 反应钢筋弯曲构件

> 原文:[https://www.geeksforgeeks.org/react-rebass-flex-component/](https://www.geeksforgeeks.org/react-rebass-flex-component/)

**React Rebass** 是一个前端框架，设计时考虑到了 React。在本文中，我们将了解如何在 React Rebass 中使用 Flex 组件。Flex 是每个开发都需要的重要组件。因此，为了创建一个 Flex 组件，我们可以导入 Rebass Flex 组件。

flex 组件用于在内容上设置 felx。

**语法:**

```jsx
<Flex>
  Content
</FLex>
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

**示例 1:** 这是展示如何使用 Flex 组件的基本示例。

## App.js

```jsx
import React from "react";
import { Flex, Box } from "rebass";

const gfg = (props) => {
    return (
        <div id="gfg">
            <br />
            <Flex>
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
                <Box
                    p={5}
                    fontSize={5}
                    width={[0.5]}
                    color="bue"
                    bg="red"
                    textAlign="center"
                >
                    GeeksforGeeks
                </Box>
            </Flex>
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

![Flex Component](img/882f675e816117681c1deebc52284aeb.png)

**参考资料:**[https://rebusjs . org/flex](https://rebassjs.org/flex)