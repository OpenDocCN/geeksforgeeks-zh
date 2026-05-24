# 对原生进度做出反应

> 原文:[https://www . geesforgeks . org/react-native-progressbarandroid/](https://www.geeksforgeeks.org/react-native-progressbarandroid/)

在本文中，我们将讨论如何为安卓应用程序创建进度条。我们将使用反应原生组件 ProgressBarAndroid。

**语法:**

```jsx
<View>
   // Other Component
  <ProgressBarAndroid/>
   // Other Component
<View>
```

**进步巴拉德里德命题:**

*   **动画:**布尔值，指定是否显示进度条。
*   **颜色:**指定进度条的颜色。
*   **不定:**用来表示不定的进程。
*   **进度:**指定进度值为数字。
*   **styleAttr:** 指定 ProgressBar 安卓组件的样式。它可以有水平、正常(默认)、小、大、反、小反和大反作为值。
*   **testID:** 用于在端到端测试中定位该视图。

**现在我们从实现开始:**

*   **步骤 1:** 打开终端，通过以下命令安装 expo-cli。

    ```jsx
    npm install -g expo-cli
    ```

*   **步骤 2:** 现在通过以下命令创建一个项目。

    ```jsx
    expo init ProgressBarAndroidDemo
    ```

*   **步骤 3:** 现在使用以下命令进入您的项目文件夹，即 ProgressBarAndroidDemo。

    ```jsx
    cd ProgressBarAndroidDemo
    ```

**项目结构:**如下图。

![](img/a374ef949d6e0f47a47796e3a5d2627e.png)

**示例:**现在让我们实现 ProgressBarAndroid。这里我们展示了一个简单的加载器动画，在它结束后，我们向用户展示了一个文本。

## App.js

```jsx
import React, { useState } from 'react';
import {
  StyleSheet, Text, View, ProgressBarAndroid,
  TouchableWithoutFeedback
} from 'react-native';

export default function App() {

  // State to hold current value
  const [val, setVal] = useState(true);

  return (
    <View style={styles.container}>
      <TouchableWithoutFeedback onPress={() => { setVal(false); }}
        style={{ flex: 1 }}>
        <View style={{
          flex: 1, justifyContent: 'center',
          alignItems: 'center'
        }}>
          <ProgressBarAndroid animating={val} color="blue"
            styleAttr='LargeInverse' />
          {!val && <Text>App has finished loading</Text>}
        </View>
      </TouchableWithoutFeedback>
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    backgroundColor: '#fff',
    alignItems: 'center',
    justifyContent: 'center',
  },
});
```

使用以下命令启动**服务器**。

```jsx
npm run android
```

**输出:**如果你的模拟器没有自动打开，那么你需要手动打开。首先，去你的安卓工作室运行模拟器。现在再次启动服务器。

![](img/774d06196284e9650b32cee22649a599.png)

**参考:**T2】https://reactnative.dev/docs/progressbarandroid