# 如何在 C# 中设置组合框的可见性？

> 原文:[https://www . geeksforgeeks . org/如何设置 c-sharp 中组合框的可见性/](https://www.geeksforgeeks.org/how-to-set-the-visibility-of-the-combobox-in-c-sharp/)

在 Windows 窗体中，组合框在单个控件中提供了两种不同的功能，这意味着组合框同时作为文本框和列表框工作。在组合框中，一次只显示一个项目，其余项目出现在下拉菜单中。您可以使用**可见属性**设置组合框的可见性。
如果要显示给定的组合框及其子控件，则将 Visible 属性的值设置为 true，否则设置为 false。此属性的默认值为真。您可以使用两种不同的方法设置此属性:

**1。设计时:**使用以下步骤设置组合框控件的可见性是最简单的方法:

*   **第一步:**创建如下图所示的窗口表单:
    **Visual Studio->File->New->Project->windows formpp**
    ![](img/13d83ffe0a08cd6c4113a5d225366c25.png)
*   **第 2 步:**从工具箱中拖动组合框控件，并将其拖放到窗口窗体上。根据您的需要，您可以将组合框控件放在窗口窗体的任何位置。
    T3】
*   **Step 3:** After drag and drop you will go to the properties of the ComboBox control to set the visibility the ComboBox.
    ![](img/eeb8dc856e8d8358c224279165a7fd91.png)

    **输出:**
    ![](img/b73a869bba062981cb93b824893e8c42.png)

**2。运行时:**比上面的方法稍微复杂一点。在此方法中，您可以借助给定的语法以编程方式设置组合框的可见性:

```cs
public bool Visible { get; set; }
```

这里，该属性的值为*系统。布尔*类型。以下步骤用于设置组合框的可见性:

*   **步骤 1:** 使用组合框类提供的组合框()构造函数创建组合框。

    ```cs
    // Creating ComboBox using ComboBox class
    ComboBox mybox = new ComboBox();

    ```

*   **步骤 2:** 创建组合框后，设置组合框的可见性。

    ```cs
    // Set the visibility of the combobox 
    mybox.Visible = false;

    ```

*   **Step 3:** And last add this combobox control to form using Add() method.

    ```cs
    // Add this ComboBox to form
    this.Controls.Add(mybox);

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

    namespace WindowsFormsApp11 {

    public partial class Form1 : Form {

        public Form1()
        {
            InitializeComponent();
        }

        private void Form1_Load(object sender, EventArgs e)
        {
            // Creating and setting the properties of label
            Label l = new Label();
            l.Location = new Point(222, 80);
            l.Size = new Size(99, 18);
            l.Text = "Select city name";

            // Adding this label to the form
            this.Controls.Add(l);

            // Creating and setting the properties of comboBox
            ComboBox mybox = new ComboBox();
            mybox.Location = new Point(327, 77);
            mybox.Size = new Size(216, 26);
            mybox.Visible = false;
            mybox.Name = "My_Cobo_Box";
            mybox.Items.Add("Mumbai");
            mybox.Items.Add("Delhi");
            mybox.Items.Add("Jaipur");
            mybox.Items.Add("Kolkata");
            mybox.Items.Add("Bengaluru");

            // Adding this ComboBox to the form
            this.Controls.Add(mybox);
        }
    }
    }
    ```

    **输出:**

    在设置可见属性之前，输出如下:
    ![](img/64a88a0984da459fc1293c0baf825a6f.png)

    将 Visible 属性设置为 false 后，输出如下:
    ![](img/b12ae68cb5fe062e7d51491fb76107f1.png)