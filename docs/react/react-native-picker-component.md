# 反应原生拾取器组件

> 原文:[https://www . geesforgeks . org/react-native-picker-component/](https://www.geeksforgeeks.org/react-native-picker-component/)

在本文中，我们将看到如何在 [react-native](https://www.geeksforgeeks.org/introduction-react-native/) 中创建一个拾取器。为此，我们将使用 Picker 组件。它用于从多个给定选项中选择特定项目。基本上，它就像一个下拉列表。

**语法:**

```jsx
<Picker>
    <Picker.Item />
    <Picker.Item />
    <Picker.Item />
</Picker>
```

**拾取器中的道具:**

*   **启用:**如果为假，则用户无法进行选择。
*   **项目样式:**用于项目标签的样式。
*   **模式:**决定所选项目将如何显示，仅在安卓平台上可用。
*   **onvaluechangge:**是选择项时的回调函数，它取两个参数第一个是变值，第二个是该项的索引。
*   **提示:**显示为对话框标题，仅在安卓平台提供。
*   **选择值:**显示选择的值。
*   **风格:**它基本上是给采摘者定风格。
*   **testID:** 用于在端到端测试中定位该视图。

**现在我们从实现开始:**

**步骤 1:** 打开终端，通过以下命令安装 expo-cli。

```jsx
npm install -g expo-cli
```

**步骤 2:** 现在通过以下命令创建一个项目。

```jsx
expo init myapp
```

**第三步:**现在进入你的项目文件夹，即 myapp

```jsx
cd myapp
```

**第 4 步:**对于 picker，我们在 React Native 中有一个 picker 组件，但是该组件现在已经被**弃用了**，所以作为替代，我们将使用一个名为 react-native-picker 的外部包。使用以下命令安装该软件包。

```jsx
npm install @react-native-picker/picker
```

**项目结构:**

![](img/1a9748005cbc03d1c29d9be185008303.png)

**示例:**现在让我们实现 Picker。在这里，我们创建了一个精选课程。

**App.js**

## java 描述语言

```jsx
import React , {useState} from 'react';
import { StyleSheet, View} from 'react-native';
import {Picker} from "@react-native-picker/picker";
export default function App() {

  const [Enable , setEnable]  = useState("courses");

  return (
    <View style={styles.container}>
        <Picker
          selectedValue={Enable}
          style={{ height: 50, width: 250 }}
          mode={"dialog"}
          onValueChange={(itemValue) => setEnable(itemValue)}
        >
           // Items
          <Picker.Item label="Courses" value="courses" />
          <Picker.Item label="Data-Structures" value="DSA" />
          <Picker.Item label="ReactJs" value="react" />
          <Picker.Item label="C++" value="cpp" />
          <Picker.Item label="Python" value="py" />
          <Picker.Item label="Java" value="java" />
        </Picker>
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
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

![](img/fd9591ea4bbac3c975160641b7eca6ff.png)

**参考:**T2】https://reactnative.dev/docs/picker