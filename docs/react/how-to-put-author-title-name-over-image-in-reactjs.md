# 在 ReactJS 中如何将作者/标题名称放在图片上方？

> 原文:[https://www . geesforgeks . org/how-to-put-author-title-name-over-image-in-reactjs/](https://www.geeksforgeeks.org/how-to-put-author-title-name-over-image-in-reactjs/)

我们可以使用 ReactJS 中的 GridListTileBar 组件将作者或书名放在的图像上。该组件在子组件上添加覆盖。React 的 Material UI 有这个组件可供我们使用，非常容易集成。我们可以使用以下方法在 ReactJS 中使用 GridListTileBar 组件。

**创建反应应用程序并安装模块:**

**步骤 1:** 使用以下命令创建一个反应应用程序:

```jsx
npx create-react-app foldername
```

**步骤 2:** 创建项目文件夹(即文件夹名**)后，使用以下命令移动到该文件夹中:**

```jsx
cd foldername
```

**步骤 3:** 创建 ReactJS 应用程序后，使用以下命令安装 **material-ui** 模块:

```jsx
npm install @material-ui/core
npm install @material-ui/icons
```

**项目结构:**如下图。

![](img/f04ae0d8b722a9fff0bd9bd138b29c23.png)

项目结构

**文件名-App.js:** 现在在 **App.js** 文件中写下以下代码。在这里，App 是我们编写代码的默认组件。

## java 描述语言

```jsx
import React from 'react';
import GridList from '@material-ui/core/GridList';
import GridListTile from '@material-ui/core/GridListTile';
import GridListTileBar from '@material-ui/core/GridListTileBar';
import ListSubheader from '@material-ui/core/ListSubheader';
import IconButton from '@material-ui/core/IconButton';
import InfoIcon from '@material-ui/icons/Info';

const App = () => {
  return (
    <div style={{ width: 700, margin: 'auto' }}>
      <h3>How to put title over image in ReactJS?</h3>
      <GridList cellHeight={180} >
        <GridListTile key="Subheader" cols={2} rows={4} style={{ height: 'auto' }}>
          <ListSubheader component="div">December</ListSubheader>
        </GridListTile>
        <GridListTile>
         <img
         src="https://write.geeksforgeeks.org/static/media/Group%20210.08204759.svg"/>
          <GridListTileBar
            title='Computer Science Portal'
            subtitle={<span>by: GeeksforGeeks</span>}
            actionIcon={
              <IconButton aria-label={`Best Place to learn`}>
                <InfoIcon />
              </IconButton>
            }
          />
        </GridListTile>
      </GridList>
    </div>
  );
}

export default App;
```

**运行应用程序的步骤:**从项目的根目录使用以下命令运行应用程序:

```jsx
npm start
```

**输出:**现在打开浏览器，转到***http://localhost:3000/***，会看到如下输出:

![](img/4be55f95639c77c97ce891ed8a2ade2e.png)