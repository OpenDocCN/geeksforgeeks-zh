# Java 中的 ContentHandlerDecorator 类

> 原文: [https://www.geeksforgeeks.org/contenthandlerdecorator-class-in-java/](https://www.geeksforgeeks.org/contenthandlerdecorator-class-in-java/)

`ContentHandlerDecorator`类是 Java 包 `org.apache.tika.sax` 的一个组件，`ContentHandlerDecorator`是 `ContentHandler` 接口的基类。`ContentHandlerDecorator`只是将所有 SAX 事件调用委托给一个底层的修饰处理程序实例。`ContentHandlerDecorator`的所有子类都可以通过重写一个或多个 SAX 事件方法来提供额外的修饰。

**语法:**

```java
public class ContentHandlerDecorator extends org.xml.sax.helpers.DefaultHandler
```

### 构造函数:

**1. `ContentHandlerDecorator()`:** 初始化 `ContentHandlerDecorator` 类的新实例。这个装饰器将传入的 SAX 事件转发给虚拟内容处理程序。

```java
ContentHandlerDecorator c = new ContentHandlerDecorator();
```

> **注意:** `c` 是 `ContentHandlerDecorator` 类的新实例。

**2. `ContentHandlerDecorator(ContentHandler handler)`:** `ContentHandlerDecorator` 类的参数化构造函数，为给定的 SAX 事件处理程序创建一个新实例。

```java
ContentHandlerDecorator c = new ContentHandlerDecorator(handler);
```

> **注意:** `Handler` 是要修饰的 SAX 事件处理程序。

### 内容处理和装饰的方法

| S.NO | 方法 | 描述 | 返回类型 |
| --- | --- | --- | --- |
| 1 | `setContentHandler(ContentHandler)` | `setContentHandler(ContentHandler)`方法用于设置内容处理程序。 | void |
| 2 | `handleException(SAXException)` | `handleException` 方法处理所有将由 `ContentHandlerDecorator` 类的方法引发的异常。 | void |
| 3 | `characters(char[] ch, int start, int length)` | `characters` 方法用于接收元素内部字符数据的通知。 | void |
| 4 | `endDocument()` | `endDocument` 方法用于接收文档结束的通知。 | void |
| 5 | `toString()` | `toString` 方法用于返回对象的字符串表示形式。 | String |
| 6 | `endElement(String uri, String localName, String name)` | `endElement` 方法用于接收元素结束的通知。 | void |
| 7 | `endPrefixMapping(String prefix)` | `endPrefixMapping` 方法用于接收命名空间映射结束的通知。 | void |
| 8 | `ignorableWhitespace(char[] ch, int start, int length)` | `ignorableWhitespace` 方法用于接收元素内容中可忽略空白的通知。 | void |
| 9 | `processingInstruction(String target, String data)` | `processingInstruction` 方法用于接收处理指令的通知。 | void |
| 10 | `setDocumentLocator(Locator locator)` | `setDocumentLocator` 方法用于接收一个 `Locator` 对象进行文档事件。 | void |
| 11 | `skippedEntity(String name)` | `skippedEntity` 方法用于接收被跳过实体的通知。 | void |
| 12 | `startDocument()` | `startDocument` 方法用于接收文档开始的通知。 | void |
| 13 | `startElement(String uri, String localName, String name, Attributes atts)` | `startElement` 方法用于接收元素开始的通知。 | void |
| 14 | `startPrefixMapping(String prefix, String uri)` | `startPrefixMapping` 方法用于接收命名空间映射开始的通知。 | void |

### 由内容句柄装饰器实现的接口

1.  `org.xml.sax.ContentHandler` – `ContentHandlerDecorator` 类实现 `ContentHandler` 接口。`ContentHandler` 接口是大多数 SAX 应用程序实现的主要接口。`ContentHandler` 接口用于接收文档逻辑内容的通知。
2.  `org.xml.sax.DTDHandler` – `ContentHandlerDecorator` 类实现了 `DTDHandler` 接口。`DTDHandler` 接口用于接收与 DTD 相关的基本事件的通知。
3.  `org.xml.sax.EntityResolver` – `ContentHandlerDecorator` 类实现 `EntityResolver` 接口。`EntityResolver` 接口用于解析实体。
4.  `org.xml.sax.ErrorHandler` – `ContentHandlerDecorator` 类实现 `ErrorHandler` 接口。`ErrorHandler` 接口用于 SAX 错误处理程序。