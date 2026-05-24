# 数据反应属性在 HTML 中有什么用？

> 原文:[https://www . geeksforgeeks . org/data-reactive-attribute-in-html/](https://www.geeksforgeeks.org/what-is-the-use-of-data-reactid-attribute-in-html/)

数据反应属性是一个自定义属性，它可以很容易地识别 DOM 中的组件。就像 HTML 的“类”和“id”属性一样，“数据反应”有助于唯一地识别元素。

因为在服务器和客户端之间以序列化的顺序共享整个对象引用可能很昂贵。因此，使用这些 id 在内部建立 DOM 中存在的节点(用于构建应用程序)的引用表示。当应用程序被呈现并且 react 在客户端被加载时，它共享给服务器的唯一数据是“data-reactid”属性。

然后，“数据反应”属性转换回所提供的数据结构，并显示数据，而无需在客户端实际呈现整个数据结构。

**示例:**使用 *app.js* 中的“react-id”属性从文件 *Data.js* 导入数据。

**T2**

```html
export const Data=[
{
 id: '.1',
 node: Div,
 children: [
   {
     id: '.2',
     node: Span,
     children: [
       {
         id: '.2’,
         node: Input,
         children: []
       }
    ]}
     ]
}]; 
```

**app . js**T0】