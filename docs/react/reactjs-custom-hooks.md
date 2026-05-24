# 重新连接定制挂钩

> 原文:[https://www.geeksforgeeks.org/reactjs-custom-hooks/](https://www.geeksforgeeks.org/reactjs-custom-hooks/)

做出反应。Js 提供了许多内置的钩子，你可以在你的 React 应用程序中使用。但是除了它们之外，你可以自己定制钩子，并在你的应用程序中使用它，从而提高可读性，减少代码量。自定义钩子是普通的 JavaScript 函数，其名称以“use”开头，它们可以调用其他钩子(内置的或自定义的)。

**对自定义钩子的需求:**您应该使用自定义钩子的主要原因是为了在您的 React 应用程序中保持 [DRY](https://www.geeksforgeeks.org/7-common-programming-principles-that-every-developer-must-follow/) (不要重复自己)的概念。例如，假设您有一些利用一些内置钩子的逻辑，并且您需要在多个功能组件中使用该逻辑。因此，您还有两种方法——1)在每个组件中编写相同的逻辑(这违反了 DRY 的概念)和 2)创建一个单独的函数来包装其中的逻辑，然后从这些组件中调用它。第二种选择无疑是更好的选择，因为你只需要写一次逻辑。这里，您创建的单独函数是自定义钩子。所以，每当你觉得你有一个逻辑要在多个功能组件中使用时(钩子在类组件中不起作用)，就为它创建一个单独的定制钩子并使用它。

**构建自定义钩子:**创建自定义钩子与创建名称以“use”开头的 JavaScript 函数相同。它可以使用里面的其他钩子，返回任何你想要它返回的东西，把任何东西作为参数。下面例子中的函数“useCustomHook”是一个使用[状态变量](https://www.geeksforgeeks.org/reactjs-usestate-hook/)“计数器”的自定义钩子。函数“resetCounter”将计数器的值增加 1，每当计数器的值更新时，传递给 [useEffect](https://www.geeksforgeeks.org/reactjs-useeffect-hook/) 钩子的函数被调用。该函数执行一些将在多个组件中使用的代码(删除这些代码是为了专注于如何使用自定义钩子，而不是实现一个逻辑)。这个自定义钩子返回“重置计数器”函数。

**文件名- src/useCustomHook.js:**

## java 描述语言

```jsx
import {useState , useEffect} from "react";

// Remember to start the name of your custom hook with "use"
function useCustomHook(initializer , componentName){
    const [counter , setCounter] = useState(initializer);

    // Increases the value of counter by 1
       function resetCounter(){
        setCounter(counter + 1);
    }

    useEffect(() => {
        // Some logic that will be used in multiple components
        console.log("The button of the " 
        + componentName + " is clicked "
        + counter + " times.");
    } , [counter , componentName]); 

    // Calls the useEffect hook if the counter updates
    return resetCounter;
}

export default useCustomHook;
```

**在组件中使用自定义钩子:**要在组件中使用自定义钩子，只需从“src”文件夹中的“useCustomHook.js”文件导入“useCustomHook”函数。

**Filename-src/components/first component . js:**

## Javascript

```jsx
import React from "react";

// importing the custom hook
import useCustomHook from "../useCustomHook";

function FirstComponent(props){

    // ClickedButton = resetCounter;
    const clickedButton = useCustomHook(0 , "FirstComponent"); 

    return (
        <div>
            <h1> This is the First Component</h1>
            <button onClick={clickedButton}> 
                  Click here!
            </button>
        </div>
    );
}

export default FirstComponent;
```

**文件名:src/components/second component . js:**

## Javascript

```jsx
import React from "react";

// Importing the custom hook
import useCustomHook from "../useCustomHook";

function SecondComponent(props){

    // ClickedButton = resetCounter;
    const clickedButton = useCustomHook(0 , "SecondComponent"); 

    return (
        <div>
            <h1> This is the Second Component</h1>
            <button onClick={clickedButton}> 
               Click here!
            </button>
        </div>
    );
}

export default SecondComponent;
```

**档案名称:src/app . js:**

## 【JavaScript】

```jsx
import React from 'react';
import './App.css';
import FirstComponent from './components/FirstComponent';
import SecondComponent from './components/SecondComponent';

function App(){ 
    return( 
        <div className='App'> 
        <FirstComponent />
        <SecondComponent />
        </div> 
    );
} 

export default App;
```