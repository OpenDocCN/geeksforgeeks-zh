# 如何在 C# 中设置文本框的位置？

> 原文:[https://www . geeksforgeeks . org/如何设置 c-sharp 中文本框的位置/](https://www.geeksforgeeks.org/how-to-set-the-location-of-the-textbox-in-c-sharp/)

在 Windows 窗体中，文本框扮演着重要的角色。在文本框的帮助下，用户可以在应用程序中输入数据，可以是单行的，也可以是多行的。在文本框中，您可以借助**位置属性**设置文本框控件左上角相对于其容器左上角的坐标。在 Windows 窗体中，可以通过两种不同的方式设置此属性:

**1。设计时:**最简单的方法是设置文本框的 Location 属性，如下步骤所示:

*   **第一步:**创建如下图所示的窗口表单:
    **Visual Studio->File->New->Project->windows formpp**
    ![](img/1360c045c6c2debb857f904eacbae56c.png)
*   **步骤 2:** 从工具箱中拖动文本框控件，并将其放到窗口窗体上。您可以根据需要将文本框放置在 windows 窗体上的任何位置。如下图所示:
    ![](img/714c73b45be782156c81b042f7a2d520.png)
*   **Step 3:** After drag and drop you will go to the properties of the TextBox control to set the Location property of the TextBox. As shown in the below image:
    ![](img/8f2bdef94fa7dec9eb000c30abaddaf4.png)

    **输出:**

    ![](img/fe132c16170868825cfd186ea65e51a1.png)

**2。运行时:**比上面的方法稍微复杂一点。在此方法中，您可以借助给定的语法以编程方式设置文本框的位置属性:

```cs
public System.Drawing.Point Location { get; set; }
```

这里，Point 用于表示控件相对于其容器左上角的左上角。以下步骤用于设置文本框的位置属性:

*   **步骤 1 :** 使用 textbox 类提供的 TextBox()构造函数创建一个 TextBox。

    ```cs
    // Creating textbox
    TextBox Mytextbox = new TextBox();

    ```

*   **步骤 2 :** 创建文本框后，设置文本框类提供的文本框的位置属性。

    ```cs
    // Set Location property
    Mytextbox1.Location = new Point(187, 51);

    ```

*   **Step 3 :** And last add this textbox control to from using Add() method.

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

    namespace my {

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
            Mylablel1.Text = "Enter Name";
            Mylablel1.AutoSize = true;
            Mylablel1.BackColor = Color.LightGray;

            // Add this label to form
            this.Controls.Add(Mylablel1);

            // Creating and setting the properties of TextBox1
            TextBox Mytextbox1 = new TextBox();
            Mytextbox1.Location = new Point(187, 51);
            Mytextbox1.BackColor = Color.LightGray;
            Mytextbox1.AutoSize = true;
            Mytextbox1.Name = "text_box1";
            Mytextbox1.Margin = new Padding(5, 5, 5, 5);

            // Add this textbox to form
            this.Controls.Add(Mytextbox1);

            // Creating and setting the properties of Lable1
            Label Mylablel2 = new Label();
            Mylablel2.Location = new Point(96, 102);
            Mylablel2.Text = "Enter Area";
            Mylablel2.AutoSize = true;
            Mylablel2.BackColor = Color.LightGray;

            // Add this label to form
            this.Controls.Add(Mylablel2);

            // Creating and setting the properties of TextBox2
            TextBox Mytextbox2 = new TextBox();
            Mytextbox2.Location = new Point(187, 99);
            Mytextbox2.BackColor = Color.LightGray;
            Mytextbox2.AutoSize = true;
            Mytextbox2.Name = "text_box2";

            // Add this textbox to form
            this.Controls.Add(Mytextbox2);
        }
    }
    }
    ```

    **输出:**
    ![](img/cf27f6bd0fd4b566926d8903878692a3.png)