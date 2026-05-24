# ReactJS UI Ant 设计模态组件

> 原文:[https://www . geeksforgeeks . org/reactjs-ui-ant-design-modal-component/](https://www.geeksforgeeks.org/reactjs-ui-ant-design-modal-component/)

蚂蚁设计库已经预建了这个组件，它也很容易集成。模态组件为创建对话框、灯箱、弹出窗口等提供了坚实的基础。它用于显示模态对话框。我们可以在 ReactJS 中使用以下方法来使用 Ant 设计模式组件。

**模态道具:**

*   **afterClose** :用于指定模式完全关闭时将触发的功能。
*   **bodyStyle:** 用于表示模态体元素的体式。
*   **取消按钮道具:**用于表示取消按钮道具。
*   **取消文本:**用于表示取消按钮的文本。
*   **居中:**用于制作居中情态。
*   **可关闭:**用于指示模态对话框右上角是否可见关闭按钮。
*   **关闭图标:**用于自定义关闭图标。
*   **确认加载:**用于表示是否对 OK 按钮应用加载视觉效果。
*   **destroyoonclose:**用于指示是否卸载 OnClose 上的子组件。
*   **focusustriggerafterclose:**表示对话框关闭后是否需要聚焦触发元素。
*   **页脚:**用于定义页脚内容。
*   **强制渲染:**用于强制渲染莫代尔。
*   **getContainer:** 该函数用于返回 Modal 的挂载节点。
*   **键盘:**用于指示是否支持按 ESC 键关闭。
*   **蒙版:**表示是否显示蒙版。
*   **maskClosable:** 用于指示点击遮罩时是否关闭模态对话框。
*   **遮罩样式:**用于定义莫代尔的遮罩元素的样式。
*   **模态渲染:**用于自定义模态内容渲染。
*   **确定按钮道具:**用于定义确定按钮道具。
*   **确定文本:**用于表示确定按钮的文本。
*   **确定类型:**用于定义确定按钮的按钮类型。
*   **样式:**用于浮动图层的样式。
*   **标题:**用于定义模态对话框的标题。
*   **可见:**用于表示模态对话框是否可见。
*   **宽度:**用于表示模态对话框的宽度。
*   **wrapClassName:** 用于传递模态对话框容器的类名。
*   **zIndex:** 用于表示情态动词的 z-index。
*   **onCancel:** 当用户点击屏蔽、关闭或取消按钮时将触发的该功能。
*   **onOk:** 当用户点击确定按钮时将触发的功能。

**模态方法:**

*   **销毁所有():**此方法用于销毁所有确认模式对话框。
*   **useModal():** 这个方法是在使用*上下文时，返回一个*上下文持有者*插入孩子。*
*   **info():** 此方法用于处理信息。
*   **成功():**此方法用于处理成功。
*   **错误():**此方法用于处理错误。
*   **警告():**此方法用于处理警告。
*   **确认():**此方法用于处理确认。

**模态法对象道具:**

*   **afterClose** :用于指定模式完全关闭时将触发的功能。
*   **自动对焦按钮:**用于指定自动对焦哪个按钮。
*   **bodyStyle:** 用于表示模态体元素的体式。
*   **取消按钮道具:**用于表示取消按钮道具。
*   **取消文本:**用于表示取消按钮的文本。
*   **居中:**用于制作居中情态。
*   **类名:**用于传递容器的类名。
*   **可关闭:**用于指示模态对话框右上角是否可见关闭按钮。
*   **关闭图标:**用于自定义关闭图标。
*   **内容:**用于定义内容。
*   **getContainer:** 该函数用于返回 Modal 的挂载节点。
*   **图标:**用于自定义图标。
*   **键盘:**用于指示是否支持按 ESC 键关闭。
*   **蒙版:**表示是否显示蒙版。
*   **maskClosable:** 用于指示点击遮罩时是否关闭模态对话框。
*   **遮罩样式:**用于定义莫代尔的遮罩元素的样式。
*   **确定按钮道具:**用于定义确定按钮道具。
*   **确定文本:**用于表示确定按钮的文本。
*   **确定类型:**用于定义确定按钮的按钮类型。
*   **样式:**用于浮动图层的样式。
*   **标题:**用于定义模态对话框的标题。
*   **宽度:**用于表示模态对话框的宽度。
*   **zIndex:** 用于表示情态动词的 z-index。

**创建反应应用程序并安装模块:**

**步骤 1:** 使用以下命令创建一个反应应用程序:

```jsx
npx create-react-app foldername
```

**步骤 2:** 在创建项目文件夹(即文件夹名**)后，使用以下命令将**移动到该文件夹:

```jsx
cd foldername
```

**步骤 3:** 创建 ReactJS 应用程序后，使用以下命令安装所需的****模块:****

```jsx
**npm install antd**
```

******项目结构:**如下图。****

****![](img/f04ae0d8b722a9fff0bd9bd138b29c23.png)

项目结构**** 

******示例:**现在在 **App.js** 文件中写下以下代码。在这里，App 是我们编写代码的默认组件。****

****App.js

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
```****