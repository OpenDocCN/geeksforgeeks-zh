# 如何在 TypeScript 类内部强制转换 JSON 对象？

> 原文: [https://www.geeksforgeeks.org/how-to-cast-a-json-object-inside-of-typescript-class/](https://www.geeksforgeeks.org/how-to-cast-a-json-object-inside-of-typescript-class/)

我们使用 JSON 对象在服务器和客户端应用程序之间存储和传输数据，或者在节点项目中本地存储和传输数据。在 Typescript 中，有两种类型的对象。

### Ordinary objects:
当我们尝试使用 [`json.parse()`](https://www.geeksforgeeks.org/javascript-json-parse-method/) 方法解析 JSON 数据时，我们得到的是普通对象而不是类对象。

### Class (constructor) object:
类对象是 Typescript 类的实例，具有其自己定义的属性、构造函数和方法。

## 示例:

### Data 1:
假设我们在客户端定义了一个 Typescript 类：

```typescript
class Todo {
    userId: number;
    id: number;
    title: string;
    done: boolean;

    getTitle() {
        return this.title;
    }

    isDone() {
        return this.done;
    }
}
```

### Data 2:
我们在项目中本地存储了一个 JSON 对象：

```json
{
    "userId": 1,
    "id": 1,
    "title": "Add Info about the new project",
    "done": true
}
```

上述 JSON 对象可以由服务器发送到网页或任何其他客户端应用程序。如果我们清楚地观察，JSON 对象的结构相当于 Typescript 类的结构，但是如果我们想为 JSON 对象访问 `Todo` 类的方法呢！我们有两种方法可以完成这个任务，使用 [`Object`](https://www.geeksforgeeks.org/javascript-objects/) 类的 `assign` 方法，本质上是将 JSON 对象克隆到 `Todo` 类对象。另一种方法是使用 `类转换器` 工具，该工具用于将类型脚本对象转换为类对象。

## 方法 1:
首先，我们将不得不导入我们的 TypeScript 文件中的 JSON 对象，这可以通过使用 TypeScript 中的 `import` 关键字来完成，这将把 JSON 对象加载到 TypeScript 变量中。在我的例子中，我们将 JSON 文件存储在与我的 TypeScript 文件相同的目录中。然后，我们可以只使用 `Object.assign()` 方法，它将返回一个 `Todo` 类对象，我们可以访问 `Todo` 类中定义的方法。

### 节目 1:

```typescript
import jsonObhect from './todo.json';

// Defining our Todo class
class Todo {
    userId: number;
    id: number;
    title: string;
    done: boolean;

    getTitle() {
        return this.title;
    }

    isDone() {
        return this.done;
    }
}

// Object.assign() will clone jsonData into
// Todo class object Storing the new class
// object in a typescript variable
let newTodo = Object.assign(new Todo(), jsonData);

// Logging the output onto the console
console.log(newTodo);
console.log(newTodo.getTitle());
```

### 输出:

```
Todo {
  userId: 1,
  id: 1,
  title: 'Add Info about new project',
  done: true
}
Add Info about new project
```

## 方法 2:
这里讨论的方法一对于简单的 JSON 对象来说很容易也很有用，但是如果我们有一个具有复杂层次结构的对象或者一组复杂的 JSON 对象，事情可能会出错。为此，我们可以使用 `类转换器` 工具，它可以使用 [节点包管理器](https://www.geeksforgeeks.org/node-js-npm-node-package-manager/) 轻松安装在您的本地系统或节点项目中。在本地系统中，使用终端或命令窗口(取决于您的操作系统)执行以下命令。

### Command:
`-g` 是用于全局安装。我们将使用类转换器工具的 `plainToClass` 方法将我们的 JSON 对象转换为 TypeScript 类对象。

```bash
npm install -g class-transformer
```

这个方法将采用两个参数，第一个参数将是 `Todo` 类的实例，第二个参数是从我们的本地项目导入的 JSON 对象。首先，我们必须从我们的 TypeScript 文件中的类转换器工具中导入该方法，这样 TypeScript 就知道使用哪种方法。同样，我们将我的 JSON 文件存储在与我的 TypeScript 文件相同的目录中。

### Procedure:

```typescript
import jsonObhect from './todo.json';
import { plainToClass } from "class-transformer";

// Defining our Todo class
class Todo {
    userId: number;
    id: number;
    title: string;
    done: boolean;

    getTitle() {
        return this.title;
    }

    isDone() {
        return this.done;
    }
}

// plainToClass method will convert
// JSON data to Todo class object
// Storing the new class object in
// a typescript variable
let newTodo = plainToClass(Todo, jsonData);

// Logging the output to the console
console.log(newTodo);
console.log(newTodo.isDone());
```

### Output:

```
Todo {
  userId: 1,
  id: 1,
  title: 'Add Info about new project',
  done: true
}
true
```

**注意:** 我们可以用来将 JSON 数据转换为 TypeScript 接口的另一个有用的工具是 [`json2ts`](http://json2ts.com/) 。如果我们为上面的 JSON 对象测试这个工具，我们将得到下面的 TypeScript 接口。

```typescript
declare module namespace {

    export interface RootObject {
        userId: number;
        id: number;
        title: string;
        done: boolean;
    }

}
```

然后使用生成的接口来定义您希望您的 typescript 类遵循的语法。