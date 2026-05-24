# 如何改变 C# 中的文本框边框样式？

> 原文:[https://www . geeksforgeeks . org/如何更改文本框-边框样式-in-c-sharp/](https://www.geeksforgeeks.org/how-to-change-the-textbox-border-style-in-c-sharp/)

在 Windows 窗体中，文本框扮演着重要的角色。在文本框的帮助下，用户可以在应用程序中输入数据，可以是单行的，也可以是多行的。在文本框中，您可以借助 **BorderStyle 属性**来设置文本框控件的边框样式，这将使您的文本框更具吸引力。该属性的默认值为*固定三维*。在 Windows 窗体中，可以通过两种不同的方式设置此属性:

**1。设计时:**设置文本框的 BorderStyle 属性是最简单的方法，如下步骤所示:

*   **第一步:**创建如下图所示的窗口表单:
    **Visual Studio->File->New->Project->windows formpp**
    ![](img/1360c045c6c2debb857f904eacbae56c.png)
*   **步骤 2:** 从工具箱中拖动 TextBox 控件，并将其放到窗口窗体上。您可以根据需要将文本框控件放置在 windows 窗体上的任何位置。
    T3】
*   **Step 3:** After drag and drop you will go to the properties of the TextBox control to set the BorderStyle property of the TextBox.
    ![](img/f3242b8e64492e4b54c91554510dd855.png)

    **输出:**

    ![](img/555fc5a0bbaaf73a11df816d35ab75fa.png)

**2。运行时:**比上面的方法稍微复杂一点。在此方法中，您可以借助给定的语法以编程方式设置文本框的 BorderStyle 属性:

```cs
public System.Windows.Forms.BorderStyle BorderStyle { get; set; }
```

这里，BorderStyle 用于表示 TextBox 控件的边框类型。如果分配给属性的值不在枚举的有效值范围内，它将引发*InvalidEnumArgumentException*。以下步骤用于设置文本框的边框样式属性:

*   **步骤 1 :** 使用 textbox 类提供的 TextBox()构造函数创建一个 TextBox。

    ```cs
    // Creating textbox
    TextBox Mytextbox = new TextBox();

    ```

*   **步骤 2 :** 创建文本框后，设置文本框类提供的文本框的 BorderStyle 属性。

    ```cs
    // Set BorderStyle property
    Mytextbox.BorderStyle = BorderStyle.FixedSingle;

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
            Mylablel.Text = "Enter Name";
            Mylablel.AutoSize = true;
            Mylablel.BackColor = Color.LightGray;

            // Add this label to form
            this.Controls.Add(Mylablel);

            // Creating and setting the properties of TextBox1
            TextBox Mytextbox = new TextBox();
            Mytextbox.Location = new Point(187, 51);
            Mytextbox.BackColor = Color.LightGray;
            Mytextbox.AutoSize = true;
            Mytextbox.Name = "text_box1";
            Mytextbox.BorderStyle = BorderStyle.FixedSingle;

            // Add this textbox to form
            this.Controls.Add(Mytextbox);
        }
    }
    }
    ```

    **输出:**

    ![](img/278db912a1cebb9d21dadf841343be56.png)