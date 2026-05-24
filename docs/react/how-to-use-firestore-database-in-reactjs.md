# 如何在 ReactJS 中使用 Firestore 数据库？

> 原文:[https://www . geeksforgeeks . org/how-用法-firestore-database-in-reactjs/](https://www.geeksforgeeks.org/how-to-use-firestore-database-in-reactjs/)

Firebase 是一款谷歌产品，可以帮助我们轻松构建、管理和开发我们的应用程序。在本文中，我们将看到如何使用 firebase firestore 作为后端，并在我们的演示 react 项目中使用 firebase 提供的 G-auth。当您设计像 iOS 或 Android 应用程序或 web 应用程序这样的移动应用程序时，数据库是一个大问题，这并不是因为它很难设计，当然设计起来有点棘手，有时它会消耗大量带宽数据库和应用程序前端之间的流量是一个大问题除此之外，主机页面也是一个问题， 想象一下，如果你的应用程序有照片共享功能，你想访问那里的所有照片，那么现在维护所有这些功能并不容易。此外，管理自己的身份验证系统也很棘手，因为每个人都需要来自脸书的身份验证，也许推特，也许谷歌，甚至一个简单的登录系统都不容易从头设计。 现在火基地来了，火基地给你一个完整的解决方案，关于如何把东西拿下来。现在这是一个非常好的完整后端解决方案，您可以使用。现在有了 firebase，您可以进行各种身份验证，最常见的是用户名、电子邮件和密码，但是有很多不同的登录方式，下面是所有可能方式的快照。

![](img/605dd62628e3f85ee14c79967ae994f3.png)

firebase 还解决了数据库的一个非常好的问题，它为您提供了一个实时数据库，在本文中，我们将看到如何将 firebase 用于数据库。

**创建反应应用程序并安装模块:**

**步骤 1:** 使用以下命令创建一个反应应用程序:

```jsx
npx create-react-app foldername
```

**步骤 2:** 创建项目文件夹(即文件夹名**)后，使用以下命令移动到该文件夹中:**

```jsx
cd foldername
```

**步骤 3:** 创建 ReactJS 应用程序后，使用以下命令安装所需的****模块:****

```jsx
**npm i firebase**
```

******项目结构:**如下图。****

****![](img/576713853b1e482880f128a068cd8ed7.png)

项目结构**** 

******运行应用程序的步骤:**从项目的根目录使用以下命令运行应用程序:****

```jsx
**npm start**
```

****让我们首先创建两个输入字段，即名称和密码以及一个提交按钮。****

## ****App.js****

```jsx
**import React, { useState } from "react";
import "./App.css";

function App() {
  const [customerName, setCustomerName] = useState("");
  const [customerPassword, setCustomerPassword] = useState("");

  return (
    <div className="App">
      <div className="App__form">
        <input
          type="text"
          placeholder="Name"
          value={customerName}
          onChange={(e) => setCustomerName(e.target.value)}
        />
        <input
          type="text"
          placeholder="Password"
          value={customerPassword}
          onChange={(e) => setCustomerPassword(e.target.value)}
        />
        <button>Submit</button>
      </div>
    </div>
  );
}

export default App;**
```

## ****App.css****

```jsx
**.App {
  text-align: center;
  height: 100vh;
  display: grid;
  place-items: center;
}

.App__form {
  display: flex;
  flex-direction: column;
}

input {
  padding: 7px 11px;
  border-radius: 3px;
  border: none;
  border-bottom: 1px solid gray;
  margin: 20px;
  outline: none;
}

button {
  display: inline-block;
  margin-right: auto;
  margin-left: auto;
  padding: 7px 12px;
  border: none;
  border-radius: 4px;
}**
```

******现在我们将创建火基地项目并创建** **火基地配置文件。******

******创建** **火基地项目的步骤:******

******第一步:**登录火基仪表盘，点击添加项目卡。****

******第二步:**输入你的项目名称点击继续。****

******步骤 3:** 在配置谷歌分析中，选择 Firebase 的默认帐户，然后单击创建项目。****

****![](img/100d5d761c82cbf8ba69d8173e887843.png)****

******第四步:**等待 firebase 创建你的项目。****

****![](img/4cd88053be86dc7a2350ea23ac7c394b.png)****

******第 5 步:**项目创建后，转到如图所示的网络图标。****

****![](img/04c71c418a3412b071b7a19298deee1d.png)****

******第六步:**给应用取昵称，选择 firebase hosting 复选框如果你想用 firebase 托管你的应用，注册你的应用。****

****![](img/04c71c418a3412b071b7a19298deee1d.png)****

******第 7 步:**如果尚未安装 Firebase CLI，只需在您的 VScode 终端上使用下面给出的命令进行安装****

```jsx
**npm install -g firebase-tools**
```

****![](img/b4420dfc5301f2437d06f8b9b996db3a.png)****

******步骤 8:** 完成后，使用下面给出的命令，使用命令行或 VSCode 中的终端登录到您的 firebase。****

```jsx
**firebase login**
```

******第 9 步:**点击继续控制台。****

******第 10 步:**下一步进入你的应用点击设置图标，在底部选择配置选项复制配置数据。转到您的本地项目，在 src 文件夹中创建一个名为 firebase.js 的文件，并粘贴配置数据以及其中的几行，如下所示。****

****![](img/bec6a54a81796842015e2e5d3b643673.png)****

## ****火库. js****

```jsx
**import firebase from "firebase";

const firebaseConfig = {
  apiKey: "AIzaSyATKyTSJVN7-Zx60WQ66kkHo3nBhuMhYDs",
  authDomain: "meteor-3fd94.firebaseapp.com",
  projectId: "meteor-3fd94",
  storageBucket: "meteor-3fd94.appspot.com",
  messagingSenderId: "391620415322",
  appId: "1:391620415322:web:6848292646d9e91e6e6d63",
  measurementId: "G-69J20TCH7X",
};

const firebaseApp = firebase.initializeApp(firebaseConfig);
const db = firebase.firestore();

export default db;**
```

******现在我们已经准备好了配置文件，我们只需要为 CRUD 操作添加代码:******

******1。创建集合:**要创建集合，我们只需使用我们在上面的 **firebase.js** 中创建的 **db** 对象。我们只需将它导入到我们的文件中，并使用 collection 方法来定位集合，在创建之后，我们的数据将存储在该集合中。如果您的集合嵌套在其他集合中，您将不得不像这样编写它， ***db.collection( <父集合>)。doc( < doc-id >)。收藏(<子-收藏>)****以此类推。现在一旦我们在我们的集合中，我们只是简单地**添加**我们的数据作为一个对象。*****

## *****App.js*****

```jsx
***import React, { useState } from "react";
import "./App.css";
import db from "./firebase";

function App() {
  const [customerName, setCustomerName] = useState("");
  const [customerPassword, setCustomerPassword] = useState("");

  const submit = (e) => {
    e.preventDefault();
    db.collection("customersData").add({
      name: customerName,
      password: customerPassword,
    });

    setCustomerName("");
    setCustomerPassword("");
  };

  return (
    <div className="App">
      <div className="App__form">
        <input
          type="text"
          placeholder="Name"
          value={customerName}
          onChange={(e) => setCustomerName(e.target.value)}
        />
        <input
          type="text"
          placeholder="Password"
          value={customerPassword}
          onChange={(e) => setCustomerPassword(e.target.value)}
        />
        <button onClick={submit}>Submit</button>
      </div>
    </div>
  );
}

export default App;***
```

*****现在我们将测试我们的代码是否工作。*****

*****![](img/f74f34f18da9f636d1419d3fca2c6255.png)*****

*****一旦我们看到这一页，那么我们都准备好了。只需转到本地主机，输入详细信息并按提交，然后再次打开 Firebase 中的 Firestore 数据库，您将看到如下所示的内容:*****

*****![](img/fdfea2762afed4413e46525de91e521a.png)*****

*****所以我们可以看到如上所示的数据*****

*******2。读取操作:**现在读取数据，初始过程相同，即导入**数据库**对象。不，我们去存储我们想要读取的数据的集合，然后我们使用 **onSnapshot** 方法，顾名思义，每当数据库中发生任何更改时，它都会简单地拍摄快照。这个函数负责我们使用 firebase 时获得的实时感觉。*****

## *****App.js*****

```jsx
***import React, { useState, useEffect } from "react";
import "./App.css";
import db from "./firebase";

function App() {
  const [customerName, setCustomerName] = useState("");
  const [customerPassword, setCustomerPassword] = useState("");
  const [customersData, setCustomersData] = useState([]);

  useEffect(() => {
    db.collection("customersData").onSnapshot((snapshot) => {
      setCustomersData(
        snapshot.docs.map((doc) => ({
          id: doc.id,
          data: doc.data(),
        }))
      );
    });
    console.log({ customersData });
  }, []);

  const submit = (e) => {
    e.preventDefault();
    db.collection("customersData").add({
      name: customerName,
      password: customerPassword,
    });

    setCustomerName("");
    setCustomerPassword("");
  };

  return (
    <div className="App">
      <div className="App__form">
        <input
          type="text"
          placeholder="Name"
          value={customerName}
          onChange={(e) => setCustomerName(e.target.value)}
        />
        <input
          type="text"
          placeholder="Password"
          value={customerPassword}
          onChange={(e) => setCustomerPassword(e.target.value)}
        />
        <button onClick={submit}>Submit</button>
      </div>
      <div className="App__DataDisplay">
        <table>
          <tr>
            <th>NAME</th>
            <th>PASSWORD</th>
          </tr>

          {customersData?.map(({ id, data }) => (
            <tr key={id}>
              <td>{data.name}</td>
              <td>{data.password}</td>
            </tr>
          ))}
        </table>
      </div>
    </div>
  );
}

export default App;***
```

*******运行应用程序的步骤:**从项目的根目录使用以下命令运行应用程序:*****

```jsx
***npm start***
```

*******输出:**现在打开浏览器，转到***http://localhost:3000/***，会看到如下输出:*****

*****![](img/d9e696ba6ca1102d0dbf3f1467b906da.png)*****

*******3。更新操作:**我们先来看一个应该更新的按钮和应该出现的字段。现在我们从 **firebase.js** 导入 **db** 对象后，我们只需转到存储要更新的数据的集合，然后我们指定需要更新的文档，因为一个集合有许多文档，所以我们必须指定要更新什么文档，然后我们只需使用**更新**方法并传递更新的对象。*****

## *****App.js*****

```jsx
***import React, { useState, useEffect } from "react";
import "./App.css";
import db from "./firebase";

function App() {
  const [customerName, setCustomerName] = useState("");
  const [customerPassword, setCustomerPassword] = useState("");
  const [customersData, setCustomersData] = useState([]);
  const [updatedCustomerName, setUpdatedCustomerName] = useState("");
  const [updatedCustomerPassword, setUpdatedCustomerPassword] = useState("");
  const [dataIdToBeUpdated, setDataIdToBeUpdated] = useState("");

  useEffect(() => {
    db.collection("customersData").onSnapshot((snapshot) => {
      setCustomersData(
        snapshot.docs.map((doc) => ({
          id: doc.id,
          data: doc.data(),
        }))
      );
    });
  }, []);

  const submit = (e) => {
    e.preventDefault();
    db.collection("customersData").add({
      name: customerName,
      password: customerPassword,
    });

    setCustomerName("");
    setCustomerPassword("");
  };

  const updateData = (e) => {
    e.preventDefault();
    db.collection("customersData").doc(dataIdToBeUpdated).update({
      name: updatedCustomerName,
      password: updatedCustomerPassword,
    });

    setUpdatedCustomerPassword("");
    setUpdatedCustomerName("");
    setDataIdToBeUpdated("");
  };

  return (
    <div className="App">
      {!dataIdToBeUpdated ? (
        <div className="App__form">
          <input
            type="text"
            placeholder="Name"
            value={customerName}
            onChange={(e) => setCustomerName(e.target.value)}
          />
          <input
            type="text"
            placeholder="Password"
            value={customerPassword}
            onChange={(e) => setCustomerPassword(e.target.value)}
          />
          <button onClick={submit}>Submit</button>
        </div>
      ) : (
        <div className="App__Updateform">
          <input
            type="text"
            placeholder="Name"
            value={updatedCustomerName}
            onChange={(e) => setUpdatedCustomerName(e.target.value)}
          />
          <input
            type="text"
            placeholder="Password"
            value={updatedCustomerPassword}
            onChange={(e) => setUpdatedCustomerPassword(e.target.value)}
          />
          <button onClick={updateData}>Update</button>
        </div>
      )}

      <div className="App__DataDisplay">
        <table>
          <tr>
            <th>NAME</th>
            <th>PASSWORD</th>
            <th>Update</th>
          </tr>

          {customersData?.map(({ id, data }) => (
            <tr key={id}>
              <td>{data.name}</td>
              <td>{data.password}</td>
              <td>
                <button
                  onClick={() => {
                    setDataIdToBeUpdated(id);
                    setUpdatedCustomerPassword(data.password);
                    setUpdatedCustomerName(data.name);
                  }}
                >
                  Update
                </button>
              </td>
            </tr>
          ))}
        </table>
      </div>
    </div>
  );
}

export default App;***
```

*******运行应用程序的步骤:**从项目的根目录使用以下命令运行应用程序:*****

```jsx
***npm start***
```

*******输出:**现在打开浏览器，转到***http://localhost:3000/***，会看到如下输出。更新数据后，您可以在 firebase 仪表板中查看数据是否更新。*****

*****![](img/6271d6d9369316bf1df21a1e31a11fb5.png)*****

*******4。删除操作:**从同样的事情开始，我们在我们的文件中导入 **db** 对象，然后我们简单地转到存储要删除的数据的集合，然后我们指定我们需要删除的文档，因为一个集合有许多文档，所以我们必须指定要删除什么文档，然后我们简单地调用**删除**方法。*****

## *****App.js*****

```jsx
***import React, { useState, useEffect } from "react";
import "./App.css";
import db from "./firebase";

function App() {
  const [customerName, setCustomerName] = useState("");
  const [customerPassword, setCustomerPassword] = useState("");
  const [customersData, setCustomersData] = useState([]);
  const [updatedCustomerName, setUpdatedCustomerName] = useState("");
  const [updatedCustomerPassword, setUpdatedCustomerPassword] = useState("");
  const [dataIdToBeUpdated, setDataIdToBeUpdated] = useState("");

  useEffect(() => {
    db.collection("customersData").onSnapshot((snapshot) => {
      setCustomersData(
        snapshot.docs.map((doc) => ({
          id: doc.id,
          data: doc.data(),
        }))
      );
    });
  }, []);

  const submit = (e) => {
    e.preventDefault();
    db.collection("customersData").add({
      name: customerName,
      password: customerPassword,
    });

    setCustomerName("");
    setCustomerPassword("");
  };

  const updateData = (e) => {
    e.preventDefault();
    db.collection("customersData").doc(dataIdToBeUpdated).update({
      name: updatedCustomerName,
      password: updatedCustomerPassword,
    });

    setUpdatedCustomerPassword("");
    setUpdatedCustomerName("");
    setDataIdToBeUpdated("");
  };

  const deleteData = (id) => {
    db.collection("customersData").doc(id).delete();
  };

  return (
    <div className="App">
      {!dataIdToBeUpdated ? (
        <div className="App__form">
          <input
            type="text"
            placeholder="Name"
            value={customerName}
            onChange={(e) => setCustomerName(e.target.value)}
          />
          <input
            type="text"
            placeholder="Password"
            value={customerPassword}
            onChange={(e) => setCustomerPassword(e.target.value)}
          />
          <button onClick={submit}>Submit</button>
        </div>
      ) : (
        <div className="App__Updateform">
          <input
            type="text"
            placeholder="Name"
            value={updatedCustomerName}
            onChange={(e) => setUpdatedCustomerName(e.target.value)}
          />
          <input
            type="text"
            placeholder="Password"
            value={updatedCustomerPassword}
            onChange={(e) => setUpdatedCustomerPassword(e.target.value)}
          />
          <button onClick={updateData}>Update</button>
        </div>
      )}

      <div className="App__DataDisplay">
        <table>
          <tr>
            <th>NAME</th>
            <th>PASSWORD</th>
            <th>Update</th>
            <th>Delete</th>
          </tr>

          {customersData?.map(({ id, data }) => (
            <tr key={id}>
              <td>{data.name}</td>
              <td>{data.password}</td>
              <td>
                <button
                  onClick={() => {
                    setDataIdToBeUpdated(id);
                    setUpdatedCustomerPassword(data.password);
                    setUpdatedCustomerName(data.name);
                  }}
                >
                  Update
                </button>
              </td>
              <td>
                <button
                  onClick={() => {
                    deleteData(id);
                  }}
                >
                  Delete
                </button>
              </td>
            </tr>
          ))}
        </table>
      </div>
    </div>
  );
}

export default App;***
```

*******运行应用程序的步骤:**从项目的根目录使用以下命令运行应用程序:*****

```jsx
***npm start***
```

*******输出:**现在打开浏览器，转到***http://localhost:3000/***，会看到如下输出。删除数据后，您可以在 firebase 仪表板中检查数据是否被删除。*****

*****![](img/7c0d442b14a307cfbb97ee97f5c5f6bc.png)*****