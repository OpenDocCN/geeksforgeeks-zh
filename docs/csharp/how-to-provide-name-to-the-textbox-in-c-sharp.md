# 如何在 C# 中给文本框提供名称？

> 原文:[https://www . geeksforgeeks . org/如何向 c-sharp 中的文本框提供名称/](https://www.geeksforgeeks.org/how-to-provide-name-to-the-textbox-in-c-sharp/)

在 Windows 窗体中，文本框扮演着重要的角色。在文本框的帮助下，用户可以在应用程序中输入数据，可以是单行的，也可以是多行的。在文本框中，您可以借助文本框的**名称属性**为文本框控件指定一个名称。此属性的默认值为空字符串。在 Windows 窗体中，可以通过两种不同的方式设置此属性:

**1。设计时:**设置文本框的名称属性是最简单的方法，如以下步骤所示:

*   **步骤 1:** 创建窗口表单。如下图所示:
    **Visual Studio->File->New->Project->windows formapp**
    ![](img/1360c045c6c2debb857f904eacbae56c.png)
*   **步骤 2:** 从工具箱中拖动 TextBox 控件，并将其放到窗口窗体上。您可以根据需要将文本框放置在 windows 窗体上的任何位置。如下图所示:
    ![](img/714c73b45be782156c81b042f7a2d520.png)
*   **Step 3:** After drag and drop you will go to the properties of the TextBox control to set the Name property of the TextBox. As shown in the below image:
    ![](img/18562abc4492479b667ab775ca46b13e.png)

    **输出:**
    ![](img/4f4e43240a946d334ea840e8c47f9aca.png)

**2。运行时:**比上面的方法稍微复杂一点。在此方法中，您可以借助给定的语法以编程方式设置文本框的名称属性:

```cs
public string Name { get; set; }
```

这里，该属性的值为*系统。弦*型。以下步骤用于设置文本框的名称属性:

*   **步骤 1 :** 使用 textbox 类提供的 TextBox()构造函数创建一个 TextBox。

    ```cs
    // Creating textbox
    TextBox Mytextbox = new TextBox();

    ```

*   **步骤 2 :** 创建文本框后，设置文本框类提供的文本框的名称属性。

    ```cs
    // Set Name of the textbox
    Mytextbox1.Name = "text_box1";

    ```

*   **Step 3 :** And at last add this textbox control to from using Add() method.

    ```cs
    // Add this textbox to form
    this.Controls.Add(Mytextbox1);

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

    namespace WindowsFormsApp2 {

    public partial class Form1 : Form {

        public Form1()
        {
            InitializeComponent();
        }

        private void Form1_Load(object sender, EventArgs e)
        {
            // Creating and setting the properties of Lable1
            Label Mylablel1 = new Label();
            Mylablel1.Location = new Point(96, 54);
            Mylablel1.Text = "Enter First Name";
            Mylablel1.AutoSize = true;
            Mylablel1.BackColor = Color.GreenYellow;

            // Add this label to form
            this.Controls.Add(Mylablel1);

            // Creating and setting the properties of TextBox1
            TextBox Mytextbox1 = new TextBox();
            Mytextbox1.Location = new Point(187, 51);
            Mytextbox1.BackColor = Color.GreenYellow;
            Mytextbox1.AutoSize = true;
            Mytextbox1.Name = "text_box1";

            // Add this textbox to form
            this.Controls.Add(Mytextbox1);

            // Creating and setting the properties of Lable1
            Label Mylablel2 = new Label();
            Mylablel2.Location = new Point(96, 102);
            Mylablel2.Text = "Enter Last Name";
            Mylablel2.AutoSize = true;
            Mylablel2.BackColor = Color.GreenYellow;

            // Add this label to form
            this.Controls.Add(Mylablel2);

            // Creating and setting the properties of TextBox2
            TextBox Mytextbox2 = new TextBox();
            Mytextbox2.Location = new Point(187, 99);
            Mytextbox2.BackColor = Color.GreenYellow;
            Mytextbox2.AutoSize = true;
            Mytextbox2.Name = "text_box2";

            // Add this textbox to form
            this.Controls.Add(Mytextbox2);
        }
    }
    }
    ```

    **输出:**

    ![](img/aeffbb814c9255d0004c83ba5215bd6f.png)