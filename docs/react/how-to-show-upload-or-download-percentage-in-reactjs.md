# 如何在 ReactJS 中显示上传或下载百分比？

> 原文:[https://www . geesforgeks . org/how-show-upload-or-download-in-reactjs/](https://www.geeksforgeeks.org/how-to-show-upload-or-download-percentage-in-reactjs/)

我们可以使用带有一些核心逻辑的循环进度组件来显示百分比。React 的 Material UI 有这个组件可供我们使用，非常容易集成。我们可以用下面的方法在 ReactJS 上实现。

**创建反应应用程序并安装模块:**

**步骤 1:** 使用以下命令创建一个 React 应用程序。

```jsx
npx create-react-app foldername
```

**步骤 2:** 在创建项目文件夹(即文件夹名**)后，使用以下命令移动到该文件夹。**

```jsx
cd foldername
```

**步骤 3:** 创建 ReactJS 应用程序后，使用以下命令安装 **material-ui** 模块。

```jsx
npm install @material-ui/core
```

**App.js:** 现在在 **App.js** 文件中写下以下代码。在这里，App 是我们编写代码的默认组件。

## java 描述语言

```jsx
import React from 'react';
import Box from '@material-ui/core/Box';
import CircularProgress from '@material-ui/core/CircularProgress';

export default function App() {

  const [uploadOrDownloadCount, 
         setUploadOrDownloadCount] = React.useState(10);

  React.useEffect(() => {
    const timer = setInterval(() => {
      setUploadOrDownloadCount(
        (beforeValue) => (beforeValue >= 100 ? 0 
                          : beforeValue + 10));
    }, 800);
    return () => {
      clearInterval(timer);
    };
  }, []);

  return (
    <div>
      <h4>How to show upload/download percentage in ReactJS?</h4>
      <Box position="relative" display="inline-flex">
        <CircularProgress variant="determinate" 
                          value={uploadOrDownloadCount} />
        <Box
          bottom={0}
          right={0}
          top={0}
          justifyContent="center"
          left={0}
          display="flex"
          alignItems="center"
          position="absolute"
        >
          {`${Math.round(uploadOrDownloadCount)}%`}
        </Box>
      </Box>
    </div>
  );
}
```

**运行应用程序的步骤:**从项目的根目录使用以下命令运行应用程序:

```jsx
npm start
```

**输出:**现在打开浏览器，转到***http://localhost:3000/***，会看到如下输出。

![](img/f0dcc9da3de1c5d5261621887f47cba4.png)