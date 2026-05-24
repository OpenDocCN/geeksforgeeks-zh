# 如何在 C# 的 ComboBox 中添加项目？

> 原文:[https://www . geesforgeks . org/how-add-items-in-combobox-in-c-sharp/](https://www.geeksforgeeks.org/how-to-add-items-in-combobox-in-c-sharp/)

在 Windows 窗体中，组合框在单个控件中提供了两种不同的功能，这意味着组合框同时作为文本框和列表框工作。在组合框中，一次只显示一个项目，其余项目出现在下拉菜单中。您可以使用**项目属性**在组合框中列出或收集元素。您可以使用两种不同的方法设置此属性:

**1。设计时:**使用以下步骤在组合框控件中添加项目是最简单的方法:

*   **第一步:**创建如下图所示的窗口表单:
    **Visual Studio->File->New->Project->windows formpp**
    ![](img/13d83ffe0a08cd6c4113a5d225366c25.png)
*   **第 2 步:**从工具箱中拖动组合框控件，并将其放到窗口窗体上。根据您的需要，您可以将组合框控件放在窗口窗体的任何位置。
    T3】
*   **Step 3:** After drag and drop you will go to the properties of the ComboBox control to add the collection of elements in the ComboBox.
    ![](img/cd86253efb3d21e496ebb6eddb076d60.png)

    **输出:**
    ![](img/53629da54057e3af94401ab2c6af701a.png)

**2。运行时:**比上面的方法稍微复杂一点。在此方法中，您可以在给定语法的帮助下，以编程方式添加组合框中的元素列表:

```cs
public System.Windows.Forms.ComboBox.ObjectCollection Items { get; }
```

在这里，*组合框。对象集合*表示组合框中存在的元素。以下步骤用于添加组合框中的元素:

*   **步骤 1:** 使用组合框类提供的组合框()构造函数创建组合框。

    ```cs
    // Creating ComboBox using ComboBox class
    ComboBox mybox = new ComboBox();

    ```

*   **步骤 2:** 创建组合框后，在组合框中添加元素。

    ```cs
    // Adding elements in the combobox
    mybox.Items.Add(230);
    mybox.Items.Add(231);
    mybox.Items.Add(232);
    mybox.Items.Add(233);
    mybox.Items.Add(234);;

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
            l.Text = "Select Your id";

            // Adding this label to the form
            this.Controls.Add(l);

            // Creating and setting the properties of comboBox
            ComboBox mybox = new ComboBox();
            mybox.Location = new Point(327, 77);
            mybox.Size = new Size(216, 26);
            mybox.Name = "My_Cobo_Box";
            mybox.Items.Add(230);
            mybox.Items.Add(231);
            mybox.Items.Add(232);
            mybox.Items.Add(233);
            mybox.Items.Add(234);

            // Adding this ComboBox to the form
            this.Controls.Add(mybox);
        }
    }
    }
    ```

    **输出:**
    ![](img/8d4d4fff15731352212c2f242404979d.png)