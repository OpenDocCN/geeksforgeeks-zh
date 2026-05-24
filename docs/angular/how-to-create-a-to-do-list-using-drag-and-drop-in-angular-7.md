# 如何在 Angular 7 中使用拖放创建待办事项列表？

> 原文:[https://www . geeksforgeeks . org/如何使用角形拖放创建待办事项列表-7/](https://www.geeksforgeeks.org/how-to-create-a-to-do-list-using-drag-and-drop-in-angular-7/)

我们可以使用 angular **组件开发工具包(CDK)提供的拖放模块轻松创建待办事项列表。**

首先，使用以下命令创建一个角度分量-

```ts
 ng g c To-Do 
```

现在将**@ angular/CDK/拖放**中的 **CdkDragDrop、moveItemInArray、transferArrayItem** 导入到我们的待办事项组件中，

编写组件视图的代码:
创建两个部分，一个用于待完成的项目，另一个用于已完成的项目。
以下是一些参数:

1.  **cdkDropList:** 它让分部知道它是一个放置容器
2.  **cdkDropListData:** 它将数据绑定到视图
3.  **cdkdroplisconnectdto:**获取当前分部连接到的另一个放置容器的 id
4.  **cdkdroplistdown:**拖动项目后，数据模型需要更新。为此，我们可以听听这个事件
5.  **cdkDrag:** 指定可以拖动项目

**示例:**

```ts
<div>
<!-- container for both list  -->
  <h1>To do</h1>

<!-- To-Do list  -->

  <div
    cdkDropList
    #todoList="cdkDropList"
    [cdkDropListConnectedTo]="[doneList]"
    [cdkDropListData]="todo"
    (cdkDropListDropped)="drag($event)">
    <div *ngFor="let item of todo" cdkDrag>{{item}}</div>
  </div>
</div>

<div>

  <h1>Done</h1>

<!-- Done list  -->

  <div
    cdkDropList
    #doneList="cdkDropList"
    [cdkDropListConnectedTo]="[todoList]"
    [cdkDropListData]="done"
    class="example-list"
    (cdkDropListDropped)="drag($event)">
    <div *ngFor="let item of done" cdkDrag>{{item}}</div>
  </div>
</div>
```

现在编写用于监听事件和添加数据的代码。
这里我们使用了一个硬编码的列表，但是您总是可以通过使用 ngmodel 指令来获取输入。有
两种可能:

1.  项目被拖到同一个容器:使用**移动项目在同一容器中移动**
2.  项目被拖动到另一个容器:使用 **transferArrayItem** 移动到另一个容器

```ts
export class To-Do {

// hardcoded lists

  todo = [
    'Go to gym',
    'Eat lunch',
    'Take a nap',
    'Physics syllabus'
  ];

  done = [
    'Assignment',
    'Coding practice',
    'Maths syllabus',
    'English syllabus'
  ];

//function for listening to the event

  drag(event: CdkDragDrop<string[]>) {

//if movement if within the same container

    if (event.previousContainer === event.container) {
      moveItemInArray(
event.container.data, event.previousIndex, event.currentIndex);
    } 

//if movement if to other containers

    else {
      transferArrayItem(event.previousContainer.data,
                        event.container.data,
                        event.previousIndex,
                        event.currentIndex);
    }
  }
}
```

**输出:**成功将“吃午饭”从待办事项列表拖至已完成列表。
T3】