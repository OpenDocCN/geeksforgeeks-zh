# 如何以文本和XML格式创建和修改Java程序的属性文件表单？

> 原文: [https://www.geeksforgeeks.org/how-to-create-and-modify-properties-file-form-java-program-in-text-and-xml-format/](https://www.geeksforgeeks.org/how-to-create-and-modify-properties-file-form-java-program-in-text-and-xml-format/)

属性文件是一个面向文本的键值对，存在于带有`.properties`扩展名的Java项目中。内容逐行呈现键值对，通常通过记事本、写字板、EditPlus等方式准备。属性文件通常有助于存储重要的敏感信息。在本文中，让我们看看如何使用Java程序创建属性文件。

Java API 提供了`java.util.Properties`类，它有几个实用的`store()`方法来以**文本或XML格式**存储属性。为了以**文本**格式存储属性，可以使用`store()`方法。`storeToXML()`用于制作**XML**格式的。

`store()`方法采用了两个参数，如输出流和注释。

## 文本格式创建

让我们看看如何创建一个文本格式的属性文件。当我们创建属性内容时，需要给出一个有效的文件路径位置。

```java
import java.io.FileNotFoundException;
import java.io.FileOutputStream;
import java.io.IOException;
import java.util.Properties;

public class CreationOfTextOrientedProperties {

    public static void main(String args[])
        throws FileNotFoundException, IOException
    {

        // Creating properties files from Java program
        Properties properties = new Properties();

        // In the name of userCreated.properties, in the
        // current directory location, the file is created
        FileOutputStream fileOutputStream
            = new FileOutputStream(
                "userCreated.properties");

        // As an example, given steps how
        // to keep username and password
        properties.setProperty("username", "value1");
        properties.setProperty("password", "value2");

        // writing properties into properties file
        // from Java As we are writing text format,
        // store() method is used
        properties.store(
            fileOutputStream,
            "Sample way of creating Properties file from Java program");

        fileOutputStream.close();
    }
}
```

**输出:**

![](img/e3280e393d433788ebdaca24118d323a.png)

我们使用`store()`以文本格式保存属性文件。作为键值对，它们被设置，即`键=值`。除此之外，所有的都被认为是注释，因此用`#`符号，注释被放置。

在许多情况下，当属性内容较少，开发人员团队经常变动，最终用户在非IT端时，以文本格式使用属性很有帮助。

## XML格式创建

在许多情况下，需要XML，它为存储重要的敏感信息提供了一种易于理解和高效的格式。可扩展标记语言(XML)是一种标记语言，它有一套编码文档的规则，可以以人类可读和机器可读的格式理解。在这里，让我们看看如何通过Java程序创建。

```java
import java.io.FileNotFoundException;
import java.io.FileOutputStream;
import java.io.IOException;
import java.util.Properties;

public class CreationOfXMLOrientedProperties {

    public static void main(String args[])
        throws FileNotFoundException, IOException
    {

        // Creating properties files from Java program
        Properties properties = new Properties();

        // In the name of userCreated.xml, in the current
        // directory location, the file is created
        FileOutputStream fileOutputStream
            = new FileOutputStream("userCreated.xml");

        // As an example, given steps how to keep username
        // and password
        properties.setProperty("username", "value1");
        properties.setProperty("password", "value2");

        // writing properties into properties file
        // from Java As we are writing in XML format,
        // storeToXML() method is used
        properties.storeToXML(
            fileOutputStream,
            "Sample way of creating Properties file from Java program");

        fileOutputStream.close();
    }
}
```

**输出:**

![](img/31404499c79f2af1013f8eaec8113e79.png)

如果我们检查XML的输出，它有相等的入口和出口。通过Java程序创建的也有相同的结构。以`<properties>`开始，以`</properties>`结束。除了键值对集，文本被视为注释，因此它们在注释标签中。属性文件只有键值，这里也是在`<entry>`标签和`key=`中声明的，这意味着每个键值对都有单独的条目。

每当属性文件内容庞大并且包含银行交易、金融数据等敏感信息时，最好只采用XML格式。

## 将XML内容转换为只读文本模式的便捷方式

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.InputStream;
import java.io.OutputStream;
import java.util.InvalidPropertiesFormatException;
import java.util.Properties;

public class ConvertXMLToTextOrientedProperties {
    public static void main(String[] args)
        throws InvalidPropertiesFormatException, IOException
    {
        String outputPropertiesFile
            = "sampleapplication.properties";
        String inputXmlFile
            = "sampleapplicationProperties.xml";

        // Input XML File which contains
        // necessary information
        InputStream inputStream
            = new FileInputStream(inputXmlFile);

        // Output properties File
        OutputStream outputStream
            = new FileOutputStream(outputPropertiesFile);

        Properties properties = new Properties();

        // Load XML file that has necessary information
        properties.loadFromXML(inputStream);

        // Store to properties file via this way
        properties.store(
            outputStream,
            "Converted from sampleapplicationProperties.xml");

        // For sample testing let us get username--It is
        // nothing but "Geek"

        // As it is converted to .properties file,
        // we can get the values in this way
        System.out.println(properties.get("username"));
    }
}
```

**输入文件(sampleapplicationProperties.xml)**

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE properties SYSTEM "http://java.sun.com/dtd/properties.dtd">
<properties>
<comment>Elegant way of converting sampleapplicationProperties.xml
  to Sampleapplication.properties</comment>
<entry key="username">Geek</entry>
  <entry key="password">XXXXWeldoneXXXX</entry>
</properties>
```

**生成的输出文件(sampleapplication.properties)**

![](img/5b2d34d70941acf7d54bcb9f1ee45833.png)

我们还有`System.out.println(properties.get("username"));`，它显示`Geek`作为输出。所以`loadFromXML()`有助于加载XML文件，并通过`store()`将其转换为面向文本的属性文件，并且在转换后，我们可以轻松获得属性值。

## 结论

在本文中，我们已经看到了从Java程序创建属性文件的方法。在你方便的时候享用它们。它们在软件项目的任何部分都是有帮助的，因为属性文件是保存敏感信息的关键文件，并且因为它们是以文本或XML格式的键值对，所以可以看到动态用法，并且在任何时间点，我们也可以很容易地修改它们。