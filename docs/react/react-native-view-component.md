# 反应原生视图组件

> 原文:[https://www.geeksforgeeks.org/react-native-view-component/](https://www.geeksforgeeks.org/react-native-view-component/)

在本文中，我们将看到如何在 react-native 中创建视图组件。为此，我们将使用反应原生视图组件。它基本上是一个小容器，支持带有 flexbox、样式、一些触摸处理和辅助功能控件的布局。视图直接映射到在任何运行 React Native 的平台上等效的原生视图，无论是 UIView、

、android.view 等等。

该组件被设计为嵌套在其他视图中，可以有 0 到多个任何类型的子组件。

**语法:**

```jsx
<view props="value"/>
```

**视图组件道具:**

*   **onstartshortsetresponder:**这个道具是一个函数类型，它用来在用户触摸组件时启动视图。
*   **可访问:**这个道具用来表示视图是一个可访问元素，默认值为真。
*   **accessibilityLabel:** 这个道具用来覆盖用户与元素交互时屏幕阅读器读取的文本。
*   **accessibilityHint:** 这个道具帮助用户理解当他们在可访问性元素上执行一个操作时会发生什么，如果这个结果没有从可访问性标签中清除的话。
*   **accessibilityRole:** 该道具用于向辅助技术的用户传达组件的目的。
*   **accessibilityState:** 用于向辅助技术用户描述组件的当前状态。
*   **accessibilityValue:** 该属性用于表示组件的当前值
*   **accessibilityActions:** 这个道具允许辅助技术以编程方式调用组件的动作。
*   **onAccessibilityAction:** 当用户执行辅助功能操作时，这个道具被用来调用。
*   **onAccessibilityTap:** 如果当用户执行可访问性轻击手势时系统将调用该功能，则可访问性道具应为 te true。
*   **onMagicTap:** 如果在用户执行魔击手势时系统会调用此功能，则使用此道具，可访问的道具应为 te true。
*   **on accessibilityscape:**如果当用户执行转义手势时，系统将调用此功能，则可访问的道具应为 te true。
*   **accessibilityviewsimmodal:**此属性指示 VoiceOver 是否应该忽略视图中与接收器是同级的元素。
*   **accessibilitylementshidden:**此属性指示包含在此可访问性元素中的可访问性元素是否被隐藏。
*   **accessibilitygnoresvertcolors:**此属性表示当颜色反转打开时，该视图应该或不应该反转。
*   **accessibilityLiveRegion:** 该属性向可访问性服务指示当该视图发生变化时是否应该通知用户。
*   **重要性对于可访问性:**这个道具控制视图对于可访问性的重要性，如果它触发可访问性事件，如果它被报告给查询屏幕的可访问性服务，它只在安卓上工作。
*   **hitSlop:** 这个属性定义了触摸事件可以从视图开始的距离
*   **nativeID:** 这个道具是用来从原生类中定位这个视图的。
*   **在线布局:**这个道具用于激活挂载和布局改变时的视图。
*   **OnMoveHodset responder:**当视图上的每个触摸动作不是响应者时，都会调用该道具。
*   **OnMoveHathSetResponderCapture:**如果父视图想要防止子视图成为移动中的响应者，那么它应该有这个返回 true 的处理程序。
*   **onResponderGrant:** 道具使视图对触摸事件做出响应。
*   **onResponderMove:** 这个道具是激活用户手指移动的应答者视图。
*   **onResponderReject:** 如果一个响应者已经处于活动状态，那么该属性将阻止另一个响应者的请求。
*   **onResponderRelease:** 这个道具用来在触摸结束时触发视图。
*   **onResponderTerminate:** 这个道具是用来从视图中带走应答者的。
*   **on responderterminationrequest:**如果任何视图想要成为响应者，而此时任何其他视图都是响应者，则此道具将要求此活动视图释放其响应者。
*   **onstartshortshortsetrespondercapture:**如果父视图希望防止子视图在触摸开始时成为响应者，则仅使用此道具。
*   **指针显示:**此道具用于控制视图是否可以成为触摸事件的目标。
*   **removeclipped subview:**这个道具是用来在有很多子视图的时候滚动内容的，这些子视图大部分都在屏幕外。
*   **样式:**此道具用于设置视图组件的样式。
*   **testID:** 这个道具用于在端到端测试中定位这个视图。
*   **可折叠:**这个在视图中使用的道具，只用于布局他们的孩子或者不绘制任何东西，可以作为一个优化从原生层次结构中自动移除。
*   **需要屏幕阿尔法合成:**这个道具定义了视图需要在屏幕外渲染并与阿尔法合成，以保持正确的颜色和混合行为。
*   **render tohardware texture Android:**
*   **应该栅格化 IOS:** 这个道具定义了在合成之前应该将视图渲染为位图，这在 IOS 设备上很有用。
*   **nextFocusDown:** 这个道具是设置当用户向下导航时下一个视图接收焦点。
*   **nextFocusForward:** 这个道具是设置当用户向前导航时，下一个视图接收焦点。
*   **nextFocusLeft:** 这个道具是设置当用户向左导航时，下一个视图接收焦点。
*   **nextFocusRight:** 这个道具是设置当用户向右导航时，下一个视图接收焦点。
*   **next focussup:**这个道具是设置当用户向上导航时下一个视图接收焦点。
*   **可聚焦:**此道具用于将视图定义为应可通过非触摸输入设备聚焦。

**现在我们从实现开始:**

*   **步骤 1:** 打开终端，通过以下命令安装 expo-cli。

    ```jsx
    npm install -g expo-cli
    ```

*   **步骤 2:** 现在通过以下命令创建一个项目。

    ```jsx
    expo init myapp
    ```

*   **第三步:**现在进入你的项目文件夹，即 myapp

    ```jsx
    cd myapp
    ```

**项目结构:**

![](img/42e739eb740dd2867a400334f668bdb8.png)

**示例:**现在让我们实现视图组件。在这里，我们在该组件中创建了一个视图组件，我们可以放置任何 API，但是在这里，我们将放置一个警报按钮，当有人单击该按钮时，将弹出一个警报。

## App.js

```jsx
import React from 'react';
import { StyleSheet,
        Text,
        View,
        Button,
        Alert
        } from 'react-native';

export default function App() {

// Alert function
const alert = ()=>{
    Alert.alert(
    "GeeksforGeeks",
    "A Computer Science Portal",
    [
        {
        text: "Cancel",
        },
        {
        text: "Agree",
        }
    ]
    );
}

return (
    <View style={styles.container}>
      <Button title={"Register"} onPress={alert}/>
    </View>
);
}

const styles = StyleSheet.create({
container: {
    flex: 1,
    backgroundColor: 'green',
    alignItems: 'center',
    justifyContent: 'center',
},
});
```

使用以下命令启动服务器。

```jsx
npm run android
```

**输出:**如果你的模拟器没有自动打开，那么你需要手动打开。首先，去你的安卓工作室运行模拟器。现在再次启动服务器。

![](img/eab1c2a6a4b5e2b3c1ebd433ee178d63.png)

**参考:**T2】https://reactnative.dev/docs/view