# 什么是 web 技术中的混搭？

> 原文：[https://www.geeksforgeeks.org/what-is-a-mashup-in-web-technology/](https://www.geeksforgeeks.org/what-is-a-mashup-in-web-technology/)

混搭（也称为*网络应用混合*）是一种网站用来从多个来源提供资源、功能和服务的技术。通俗地说，混搭是不同服务的聚合器。他们主要使用公共的 [API](https://www.geeksforgeeks.org/introduction-to-apis/)，通常是免费使用的，因此，从现有的服务中创建一个新的服务。

## 混搭的类型：

*   业务混搭：它们是在外部 web 服务的帮助下为应用程序和资源提供动力的服务。因此，它们促进了企业和开发者之间的协作。它们为用户提供了更好的交互式用户界面，并向用户承诺收集各种各样的信息。
*   消费者混搭：它们是利用来自可用公共数据集的不同数据的应用程序，并提供更容易访问的简单浏览器用户界面。用户可以使用这些类型的应用程序以简单、优雅和有组织的方式使用信息。
*   数据混搭：与消费者混搭相比，这些应用程序使用不同来源上可用的相同类型的数据，然后将它们组合起来创建一个全新的来源，该来源包含在单个来源上找不到的所有信息。

## 建筑等级：

定义混搭架构有三个层次：

*   `Presentation layer or user interaction layer`：这是混搭用户界面。技术：[HTML](https://www.geeksforgeeks.org/html-tutorials/)、[CSS](https://www.geeksforgeeks.org/css-tutorials/?ref=lbp)、[Ajax](https://www.geeksforgeeks.org/ajax-introduction/)、[JavaScript](https://www.geeksforgeeks.org/javascript-tutorial/) 等。
*   `Web service`：通过 API 服务访问产品功能。工具：`XMLHTTPRequest` 和 [SOAP](https://www.geeksforgeeks.org/basics-of-soap-simple-object-access-protocol/)。
*   `Data`：数据处理，如发送、存储和接收数据。技术：[JSON](https://www.geeksforgeeks.org/javascript-json/)、XML。

## 示例：

*   谷歌地图是最受欢迎的服务之一，被许多其他公司/服务使用。提供路况信息的应用程序，使用地图显示社交媒体朋友的位置，提供不同城市的评级等。是一些结合谷歌数据并在自己的应用程序中使用的服务。
*   亚马逊电子商务是一些混搭网站使用的另一个最受欢迎的服务之一。它们的应用编程接口可用于不同网站上的产品可用性查看、不同网站上特定产品的成本比较等应用。

## 优点：

使用混搭已经成为网络中一个重要且流行的部分。它有几个好处描述如下：

*   在一个地方提供聚合内容，这样用户就不必浏览不同的服务。
*   更丰富、更具交互性的用户界面。
*   开发周期通常很快，因为开发人员需要更少的代码来构建它们。
*   促进公司/服务之间更大的合作。
*   开发混搭网站的成本相对较低，因为它减少了应用程序开发的工作量。

## 不足之处

虽然混搭似乎是一个很好的选择，但它也有一些缺点，如下所述：

*   混搭网站的功能完全依赖于其他开发者，也就是说，它们只能实现其他网站 API 中定义的功能，不能灵活地使用它们。
*   如果某个网站的 API/服务停止生产，它将直接影响混搭网站。
*   混搭网站使用的内容并不完全安全。
*   缺乏可扩展性是一个主要问题，因为无法预测混搭网站使用的服务是否能处理大量的流量。