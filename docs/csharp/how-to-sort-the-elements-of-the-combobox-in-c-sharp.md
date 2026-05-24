# c# 中组合框的元素如何排序？

> 原文:[https://www . geeksforgeeks . org/如何对 c-sharp 中的组合框元素进行排序/](https://www.geeksforgeeks.org/how-to-sort-the-elements-of-the-combobox-in-c-sharp/)

在 Windows 窗体中，组合框在单个控件中提供了两种不同的功能，这意味着组合框同时作为文本框和列表框工作。在组合框中，一次只显示一个项目，其余项目出现在下拉菜单中。您可以使用**排序属性**对组合框中的元素进行排序。
如果要对组合框的元素进行排序，那么将该属性的值设置为 true，否则设置为 false。此属性的默认值为 false。这种排序不区分大小写，元素按升序排序。您可以使用两种不同的方法设置此属性:

**1。设计时:**使用以下步骤对组合框控件中的元素进行排序是最简单的方法:

*   **第一步:**创建如下图所示的窗口表单:
    **Visual Studio->File->New->Project->windows formpp**
    ![](img/13d83ffe0a08cd6c4113a5d225366c25.png)
*   **第 2 步:**从工具箱中拖动组合框控件，并将其放到窗口窗体上。根据您的需要，您可以将组合框控件放在窗口窗体的任何位置。
    T3】
*   **Step 3:** After drag and drop you will go to the properties of the ComboBox control to sort the elements present in the ComboBox.
    ![](img/ee0b67ed03732b9c54bdc3b984fae71b.png)

    **输出:**
    ![](img/b73a869bba062981cb93b824893e8c42.png)

**2。运行时:**比上面的方法稍微复杂一点。在此方法中，您可以在给定语法的帮助下，以编程方式对组合框中的元素进行排序:

```cs
public bool Sorted { get; set; }
```

这里，该属性的值为*系统。布尔*类型。以下步骤用于对组合框元素进行排序:

*   **步骤 1:** 使用组合框类提供的组合框()构造函数创建组合框。

    ```cs
    // Creating ComboBox using ComboBox class
    ComboBox mybox = new ComboBox();

    ```

*   **步骤 2:** 创建组合框后，对组合框的元素进行排序。

    ```cs
    // Sort the elements of the ComboBox 
    mybox.Sorted = true;

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
            mybox.Sorted = true;
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

    排序前:
    ![](img/64a88a0984da459fc1293c0baf825a6f.png)

    排序后:
    ![](img/0665419102ebfe1c451da8c6bf1b60bb.png)