# 在 ReactJS 中如何运用单一责任原则？

> 原文:[https://www . geeksforgeeks . org/如何使用-单一责任原则-in-reactjs/](https://www.geeksforgeeks.org/how-to-use-single-responsibility-principle-in-reactjs/)

如果你是一名开发人员，那么在你的编程生涯中，你肯定听过好几次[](https://www.geeksforgeeks.org/solid-principle-in-programming-understand-with-real-life-examples/)**原则这个词。在软件开发中，SOLID 原则作为开发人员的指南。你在项目中使用哪种语言并不重要，为了使你的代码干净和可维护，你需要在你的项目中应用固体原则。**

**SOLID 原则使开发人员更容易完成任务，也有助于他们维护项目中的代码。让我们来谈谈 React now，这是一个在开发人员中非常流行的框架。**

**借助 [***【反应过来】***](https://www.geeksforgeeks.org/react-js-introduction-working/) ，可以创建一个漂亮的 UI。在你职业生涯的早期阶段，你可能会在用 React 编写代码时犯很多错误，但是一旦你有了使用它的经验，你就会明白在 React 中编写干净且可维护的代码也很重要。出于这个原因，有一件事可以帮助你，那就是固体原理。**

**您可以编写小的、漂亮的和干净的 React 组件。坚实的原则使你的组件清晰可见，责任明确。固体原理告诉我们，每个类都应该有一个唯一的存在目的。在“反应”中，组件一次只能做一件事。**

**![How-To-Use-Single-Responsibility-Principle-in-ReactJS](img/dcc76efd6e43ed78712e7ea5ae2677ef.png)**

**现在让我们了解如何在 React 中重构一个坏代码，并使它更干净。首先， ***我们来考虑一个不好的例子*** …**

## **java 描述语言**

```jsx
import React, {useEffect, useReducer, useState} from "react";

const initialState = {
    isLoading: true
};

// COMPLEX STATE MANAGEMENT
function reducer(state, action) {
    switch (action.type) {
        case 'LOADING':
            return {isLoading: true};
        case 'FINISHED':
            return {isLoading: false};
        default:
            return state;
    }
}

export const SingleResponsibilityPrinciple = () => {

    const [users , setUsers] = useState([])
    const [filteredUsers , setFilteredUsers] = useState([])
    const [state, dispatch] = useReducer(reducer, initialState);

    const showDetails = (userId) => {
        const user = filteredUsers.find(user => user.id===userId);
        alert(user.contact)
    }

    // REMOTE DATA FETCHING
    useEffect(() => {
        dispatch({type:'LOADING'})
        fetch('https://jsonplaceholder.typicode.com/users')
            .then(response => response.json())
            .then(json => {
                dispatch({type:'FINISHED'})
                setUsers(json)
            })
    },[])

    // PROCESSING DATA
    useEffect(() => {
        const filteredUsers = users.map(user => {
            return {
                id: user.id,
                name: user.name,
                contact: `${user.phone} , ${user.email}`
            };
        });
        setFilteredUsers(filteredUsers)
    },[users])

    // COMPLEX UI RENDERING
    return <>
        <div> Users List</div>
        <div> Loading state: {state.isLoading? 'Loading': 'Success'}</div>
        {users.map(user => {
            return <div key={user.id} onClick={() => showDetails(user.id)}>
                <div>{user.name}</div>
                <div>{user.email}</div>
            </div>
        })}
    </>
}
```

**这里，我们从远程源获取数据，然后在用户界面中呈现它。我们也在检测 API 调用的加载状态。基本上，上面的代码主要分为…四件事…**

*   **远程数据提取…**
*   **数据过滤…**
*   **复杂的状态管理…**
*   **复杂的用户界面功能…**

**现在让我们看看如何改进这段代码的设计，以及如何使它更易于清理…**

### **1.从代码中分离数据处理逻辑。**

**您永远不应该将 HTTP 调用保留在组件中。这是一个基本的经验法则。要从组件中删除这些代码，可以遵循几种策略。**

**您可以创建一个自定义钩子，并且可以在该自定义钩子内移动您的数据获取和过滤逻辑。让我们看看怎么做…**

**创建一个名为 useGetRemoteData 的钩子。如下图所示…**

## **java 描述语言**

```jsx
import {useEffect, useReducer, useState} from "react";

const initialState = {
    isLoading: true
};

function reducer(state, action) {
    switch (action.type) {
        case 'LOADING':
            return {isLoading: true};
        case 'FINISHED':
            return {isLoading: false};
        default:
            return state;
    }
}

export const useGetRemoteData = (url) => {

    const [users , setUsers] = useState([])
    const [state, dispatch] = useReducer(reducer, initialState);

    const [filteredUsers , setFilteredUsers] = useState([])

    useEffect(() => {
        dispatch({type:'LOADING'})
        fetch('https://jsonplaceholder.typicode.com/users')
            .then(response => response.json())
            .then(json => {
                dispatch({type:'FINISHED'})
                setUsers(json)
            })
    },[])

    useEffect(() => {
        const filteredUsers = users.map(user => {
            return {
                id: user.id,
                name: user.name,
                contact: `${user.phone} , ${user.email}`
            };
        });
        setFilteredUsers(filteredUsers)
    },[users])

    return {filteredUsers , isLoading: state.isLoading}
}
```

**现在，如果你看看你的主要组成部分，那么它会像这样…**

## **java 描述语言**

```jsx
import React from "react";
import {useGetRemoteData} from "./useGetRemoteData";

export const SingleResponsibilityPrinciple = () => {

    const {filteredUsers , isLoading} = useGetRemoteData()

    const showDetails = (userId) => {
        const user = filteredUsers.find(user => user.id===userId);
        alert(user.contact)
    }

    return <>
        <div> Users List</div>
        <div> Loading state: {isLoading? 'Loading': 'Success'}</div>
        {filteredUsers.map(user => {
            return <div key={user.id} onClick={() => showDetails(user.id)}>
                <div>{user.name}</div>
                <div>{user.email}</div>
            </div>
        })}
    </>
}
```

**您可以观察到，您的组件现在更干净、更容易理解了。让我们使用更多的技术或方法使我们的代码变得更好。**

### **2.分离数据获取代码，使其可重用**

**useGetRemoteData 在您的代码中有两个用途…**

1.  **从远程源获取数据**
2.  **过滤数据**

**我们可以做一个单独的钩子，我们可以把我们的数据获取逻辑移到那里。让我们给它起个名字……useHttpGetRequest。它将 URL 作为一个组件。**

## **java 描述语言**

```jsx
import {useEffect, useReducer, useState} from "react";
import {loadingReducer} from "./LoadingReducer";

const initialState = {
    isLoading: true
};

export const useHttpGetRequest = (URL) => {

    const [users , setUsers] = useState([])
    const [state, dispatch] = useReducer(loadingReducer, initialState);

    useEffect(() => {
        dispatch({type:'LOADING'})
        fetch(URL)
            .then(response => response.json())
            .then(json => {
                dispatch({type:'FINISHED'})
                setUsers(json)
            })
    },[])

    return {users , isLoading: state.isLoading}

}
```

**让我们也将减速器逻辑分离到一个单独的文件中……** 

## **java 描述语言**

```jsx
export function loadingReducer(state, action) {
    switch (action.type) {
        case 'LOADING':
            return {isLoading: true};
        case 'FINISHED':
            return {isLoading: false};
        default:
            return state;
    }
}
```