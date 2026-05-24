# ASP 会话。内容.移除方法

> 原文:[https://www . geesforgeks . org/ASP-session-contents-remove-method/](https://www.geeksforgeeks.org/asp-session-contents-remove-method/)

***会话。ASP*** 中的移除方法用于从会话内容集合中移除项目。这是会话类型对象的预定义方法。

**语法**

```vb
***Session.Contents.Remove(name|index)*** 
```

**参数值:**它包含代表将从会话中删除的指定项目的索引的值，即名称。

***示例:*** 下面的代码说明了如何从内容列表中删除第三项。

```vb
***<%***
***Session("item1")=("Geeks")***
***Session("item2")=("For")***
***Session("item3")=("Geeks")***
***Session("item4")=("sudo")***

***Session.Contents.Remove(3)***

***for each x in Session.Contents***
 ***Response.Write(x & "=" & Session.Contents(x) & "<br>")***
***next***
***%>***
```

**输出**

```vb
 ***item1= Geeks***
 ***iten2=For***
 ***item4=Sudo*** 
```