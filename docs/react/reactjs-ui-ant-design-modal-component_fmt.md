# ReactJS UI Ant 设计模态组件

> 原文: [https://www.geeksforgeeks.org/reactjs-ui-ant-design-modal-component/](https://www.geeksforgeeks.org/reactjs-ui-ant-design-modal-component/)

蚂蚁设计库已经预建了这个组件，它也很容易集成。模态组件为创建对话框、灯箱、弹出窗口等提供了坚实的基础。它用于显示模态对话框。我们可以在 ReactJS 中使用以下方法来使用 Ant 设计模式组件。

## 模态道具

*   `afterClose` : 用于指定模式完全关闭时将触发的功能。
*   `bodyStyle`: 用于表示模态体元素的体式。
*   `cancelButtonProps`: 用于表示取消按钮道具。
*   `cancelText`: 用于表示取消按钮的文本。
*   `centered`: 用于制作居中情态。
*   `closable`: 用于指示模态对话框右上角是否可见关闭按钮。
*   `closeIcon`: 用于自定义关闭图标。
*   `confirmLoading`: 用于表示是否对 OK 按钮应用加载视觉效果。
*   `destroyOnClose`: 用于指示是否卸载 OnClose 上的子组件。
*   `focusTriggerAfterClose`: 表示对话框关闭后是否需要聚焦触发元素。
*   `footer`: 用于定义页脚内容。
*   `forceRender`: 用于强制渲染莫代尔。
*   `getContainer`: 该函数用于返回 Modal 的挂载节点。
*   `keyboard`: 用于指示是否支持按 ESC 键关闭。
*   `mask`: 表示是否显示蒙版。
*   `maskClosable`: 用于指示点击遮罩时是否关闭模态对话框。
*   `maskStyle`: 用于定义莫代尔的遮罩元素的样式。
*   `modalRender`: 用于自定义模态内容渲染。
*   `okButtonProps`: 用于定义确定按钮道具。
*   `okText`: 用于表示确定按钮的文本。
*   `okType`: 用于定义确定按钮的按钮类型。
*   `style`: 用于浮动图层的样式。
*   `title`: 用于定义模态对话框的标题。
*   `visible`: 用于表示模态对话框是否可见。
*   `width`: 用于表示模态对话框的宽度。
*   `wrapClassName`: 用于传递模态对话框容器的类名。
*   `zIndex`: 用于表示情态动词的 z-index。
*   `onCancel`: 当用户点击屏蔽、关闭或取消按钮时将触发的该功能。
*   `onOk`: 当用户点击确定按钮时将触发的功能。

## 模态方法

*   `destroyAll()`: 此方法用于销毁所有确认模式对话框。
*   `useModal()`: 这个方法是在使用*上下文时，返回一个*上下文持有者*插入孩子。*
*   `info()`: 此方法用于处理信息。
*   `success()`: 此方法用于处理成功。
*   `error()`: 此方法用于处理错误。
*   `warning()`: 此方法用于处理警告。
*   `confirm()`: 此方法用于处理确认。

## 模态法对象道具

*   `afterClose` : 用于指定模式完全关闭时将触发的功能。
*   `autoFocusButton`: 用于指定自动对焦哪个按钮。
*   `bodyStyle`: 用于表示模态体元素的体式。
*   `cancelButtonProps`: 用于表示取消按钮道具。
*   `cancelText`: 用于表示取消按钮的文本。
*   `centered`: 用于制作居中情态。
*   `className`: 用于传递容器的类名。
*   `closable`: 用于指示模态对话框右上角是否可见关闭按钮。
*   `closeIcon`: 用于自定义关闭图标。
*   `content`: 用于定义内容。
*   `getContainer`: 该函数用于返回 Modal 的挂载节点。
*   `icon`: 用于自定义图标。
*   `keyboard`: 用于指示是否支持按 ESC 键关闭。
*   `mask`: 表示是否显示蒙版。
*   `maskClosable`: 用于指示点击遮罩时是否关闭模态对话框。
*   `maskStyle`: 用于定义莫代尔的遮罩元素的样式。
*   `okButtonProps`: 用于定义确定按钮道具。
*   `okText`: 用于表示确定按钮的文本。
*   `okType`: 用于定义确定按钮的按钮类型。
*   `style`: 用于浮动图层的样式。
*   `title`: 用于定义模态对话框的标题。
*   `width`: 用于表示模态对话框的宽度。
*   `zIndex`: 用于表示情态动词的 z-index。

## 创建反应应用程序并安装模块

### 步骤 1
使用以下命令创建一个反应应用程序:
```jsx
npx create-react-app foldername
```

### 步骤 2
在创建项目文件夹(即文件夹名)后，使用以下命令将移动到该文件夹:
```jsx
cd foldername
```

### 步骤 3
创建 ReactJS 应用程序后，使用以下命令安装所需的模块:
```jsx
npm install antd
```

### 项目结构
如下图。

![](img/f04ae0d8b722a9fff0bd9bd138b29c23.png)

### 示例
现在在 `App.js` 文件中写下以下代码。在这里，`App` 是我们编写代码的默认组件。

`App.js`
```jsx
import React, { useState } from 'react';
import "antd/dist/antd.css";
import { Modal, Button } from 'antd';

export default function App() {

const [isModalVisible, setIsModalVisible] = useState(false);

return (
    <div style={{
      display: 'block', width: 700, padding: 30
    }}>
      <h4>ReactJS Ant-Design Modal Component</h4>
      <>
        <Button type="secondary" onClick={() => {
          setIsModalVisible(true);
        }}>
          Click to open Modal
      </Button>
        <Modal title="Modal Title"
          visible={isModalVisible}
          onOk={() => {
            setIsModalVisible(false);
          }}
          onCancel={() => {
            setIsModalVisible(false);
          }}>
          <p>Sample Modal contents</p>

</Modal>
      </>
    </div>
  );
}
```