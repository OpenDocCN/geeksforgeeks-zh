# 如何在 C# 中创建多行文本框？

> 原文:[https://www . geesforgeks . org/how-create-multiline-textbox-in-c-sharp/](https://www.geeksforgeeks.org/how-to-create-multiline-textbox-in-c-sharp/)

在 Windows 窗体中，文本框扮演着重要的角色。在文本框的帮助下，用户可以在应用程序中输入数据，可以是单行的，也可以是多行的。在文本框中，您可以使用文本框的 **Multiline 属性**创建存储多行内容的多行文本框。从多行文本框中将该属性的值设置为 true，否则设置为 false。此属性的默认值为 false。在 Windows 窗体中，可以通过两种不同的方式设置此属性:

**1。设计时:**设置文本框的 Multiline 属性是最简单的方法，如以下步骤所示:

*   **步骤 1:** 创建窗口表单。
    **Visual Studio - >文件- >新建- >项目- >窗口形式程序**
    T6】
*   **步骤 2:** 从工具箱中拖动 TextBox 控件，并将其放到窗口窗体上。您可以根据需要将文本框放置在 windows 窗体上的任何位置。
    T3】
*   **Step 3:** After drag and drop you will go to the properties of the TextBox control to set the Multiline property of the TextBox.
    ![](img/1d6a16b103cc526f079c397743dedc2c.png)

    **输出:**

    ![](img/ea5561e205ef5204b0c35d0d849185ed.png)

**2。运行时:**比上面的方法稍微复杂一点。在此方法中，您可以借助给定的语法以编程方式设置文本框的 Multiline 属性:

```cs
public override bool Multiline { get; set; }
```

这里，该属性的值为*系统。布尔*类型。以下步骤用于设置文本框的 Multiline 属性:

*   **步骤 1 :** 使用 textbox 类提供的 TextBox()构造函数创建一个 TextBox。

    ```cs
    // Creating textbox
    TextBox Mytextbox = new TextBox();

    ```

*   **步骤 2 :** 创建文本框后，设置文本框类提供的文本框的 Multiline 属性。

    ```cs
    // Set Multiline property
    Mytextbox.Multiline = true;

    ```

*   **Step 3 :** And last add this textbox control to from using Add() method.

    ```cs
    // Add this textbox to form
    this.Controls.Add(Mytextbox);

    ```

    **示例:**

    ```cs
    using System;
    using System.Collections.Generic;
    using System.ComponentModel;
    using System.Data;
    using System.Drawing;
    using System.Linq;
    using System.Text;
    using System.Threading.Tasks;
    using System.Windows.Forms;

    namespace my {

    public partial class Form1 : Form {

        public Form1()
        {
            InitializeComponent();
        }

        private void Form1_Load(object sender, EventArgs e)
        {

            // Creating and setting the properties of Lable1
            Label Mylablel = new Label();
            Mylablel.Location = new Point(96, 54);
            Mylablel.Text = "Introduction";
            Mylablel.AutoSize = true;
            Mylablel.BackColor = Color.LightGray;

            // Add this label to form
            this.Controls.Add(Mylablel);

            // Creating and setting the properties of TextBox1
            TextBox Mytextbox = new TextBox();
            Mytextbox.Location = new Point(187, 51);
            Mytextbox.BackColor = Color.LightGray;
            Mytextbox.ForeColor = Color.DarkOliveGreen;
            Mytextbox.Height = 140;
            Mytextbox.Width = 200;
            Mytextbox.Name = "text_box1";
            Mytextbox.Multiline = true;

            // Add this textbox to form
            this.Controls.Add(Mytextbox);
        }
    }
    }
    ```

    **输出:**
    ![](img/3dc079b0f4f7487f2ebf2e0c9872509f.png)