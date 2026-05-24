# 如何在 C# 中设置组合框中呈现的内容的字体？

> 原文:[https://www . geeksforgeeks . org/如何设置 c-sharp 中的内容呈现字体/](https://www.geeksforgeeks.org/how-to-set-the-font-of-the-content-present-in-the-combobox-in-c-sharp/)

在 Windows 窗体中，组合框在单个控件中提供了两种不同的功能，这意味着组合框同时作为文本框和列表框工作。在组合框中，一次只显示一个项目，其余项目出现在下拉菜单中。您可以使用**字体属性**来设置组合框中内容的字体。您可以使用两种不同的方法设置此属性:

**1。设计时:**使用以下步骤设置组合框控件中元素的字体是最简单的方法:

*   **第一步:**创建如下图所示的窗口表单:
    **Visual Studio->File->New->Project->windows formpp**
    ![](img/13d83ffe0a08cd6c4113a5d225366c25.png)
*   **第 2 步:**从工具箱中拖动组合框控件，并将其放到窗口窗体上。根据您的需要，您可以将组合框控件放在窗口窗体的任何位置。
    T3】
*   **Step 3:** After drag and drop you will go to the properties of the ComboBox control to set the font of the elements present in the ComboBox.
    ![](img/480fa115cb59f9e4200a63c0cec98540.png)

    **输出:**
    ![](img/50d6b88d6bafbef2fa2702919e4649de.png)

**2。运行时:**比上面的方法稍微复杂一点。在此方法中，您可以在给定语法的帮助下，以编程方式设置组合框中元素的字体:

```cs
public virtual System.Drawing.Font Font { get; set; }
```

这里，字体表示应用于组合框内容的字体。以下步骤用于设置组合框元素的字体:

*   **步骤 1:** 使用组合框类提供的组合框()构造函数创建组合框。

    ```cs
    // Creating ComboBox using ComboBox class
    ComboBox mybox = new ComboBox();

    ```

*   **第二步:**创建组合框后，设置组合框元素的字体。

    ```cs
    // Set the font of the combobox elements
    mybox.Font = new Font("Chiller", 12);

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
            l.Font = new Font("Chiller", 12);
            l.Size = new Size(99, 18);
            l.Text = "Select city name";

            // Adding this label to the form
            this.Controls.Add(l);

            // Creating and setting the properties of comboBox
            ComboBox mybox = new ComboBox();
            mybox.Location = new Point(327, 77);
            mybox.Size = new Size(216, 26);
            mybox.Name = "My_Cobo_Box";
            mybox.Font = new Font("Chiller", 12);
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
    ![](img/05d452add74ee147037e9e39d8f84f29.png)