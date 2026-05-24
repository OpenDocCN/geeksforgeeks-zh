# 从文本文件中提取内容的 Java 程序

> 原文: [https://www.geeksforgeeks.org/java-program-to-extract-content-from-a-txt-document/](https://www.geeksforgeeks.org/java-program-to-extract-content-from-a-txt-document/)

## Java 类库介绍

使用 Apache Tika 库的 Java 类来处理文件。它用于文档类型检测和从各种文件格式中提取内容，使用各种文档解析器和文档类型检测技术来检测和提取数据。它提供了一个单一的通用 API 来解析不同的文件格式。所有这些解析器库都封装在一个称为 `Parser` 接口的单一接口中。请从 [Apache Tika 下载页面](https://tika.apache.org/download.html) 下载 Tika。

## 核心类说明

`BodyContentHandler` 是一个内置类，它为文本创建一个处理程序，该处理程序编写这些 XHTML 正文字符事件，并将它们存储在内部字符串缓冲区中。它是从 Java 中的父类 `ContentHandlerDecorator` 继承而来的。可以使用父类提供的方法 `ContentHandlerDecorator.toString()` 检索指定的文本。

`ParseContext` 类是 Java 包 `org.apache.tika.parser` 的一个组件，用于解析上下文并将其传递给 Tika 解析器。

`TXTParser` 是一个内置包，提供了一个类 `TXTParser`，用于解析文本文档的内容。它提取存储在段落、字符串和表格中的文本文档的内容（不调用表格边界）。如果密码被指定为参数，它也可以用来解析加密的文档。

Java 支持多个内置的类和包来提取和访问 PDF 文档中的内容。以下类别用于提取内容：

## 程序步骤

1.  创建内容处理程序。
2.  在系统的本地目录中创建一个 TXT 文件。
3.  现在，创建一个文件输入流，其路径与上面创建的 txt 文件相同。
4.  使用文档的元数据类型对象创建内容解析器。
5.  现在使用 TXT 解析器类解析文档。
6.  打印如上创建的 TXT 文件的内容，以说明上述文档中内容的提取。

## 示例代码

```java
// Java Program to Extract Content from a TXT document

// Importing java input/output classes
import java.io.File;
import java.io.FileInputStream;
import java.io.IOException;
// Importing Apache POI classes
import org.apache.tika.exception.TikaException;
import org.apache.tika.metadata.Metadata;
import org.apache.tika.parser.ParseContext;
import org.apache.tika.parser.txt.TXTParser;
import org.apache.tika.sax.BodyContentHandler;
import org.xml.sax.SAXException;

// Main Class
public class GFG {

    // Main driver method
    public static void main(String[] args) throws Exception
    {
        // Creating a content handler by
        // creating an object of BodyContentHandler class
        BodyContentHandler handler
            = new BodyContentHandler();

        // Creating a file in local directory
        // Create a file input stream
        // on specified path with the created file
        FileInputStream fstream
            = new FileInputStream(new File("C:/test.txt"));

        // Creating an object of type Metadata to use
        Metadata metadata = new Metadata();

        // Create a context parser for the text document by
        // creating an object of ParseContext class
        ParseContext pcontext = new ParseContext();

        // Now, text document can be parsed
        // using the TXTParser class
        TXTParser TexTParser = new TXTParser();

        // Method parse invoked on TXTParser class
        TexTParser.parse(fstream, handler, metadata,
                         pcontext);

        // Print and display the extracted content from TXT file
        System.out.println("Extracting contents :"
                           + handler.toString());
    }
}
```

**输出:** 作为文件返回，如下所示:

![](img/dd91a00a04e47174fa4ad18522981642.png)