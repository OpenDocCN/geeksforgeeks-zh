# p5.js | p5.Table.addColumn()方法

> 原文: [https://www.geeksforgeeks.org/p5-js-p5-table-addcolumn-method/](https://www.geeksforgeeks.org/p5-js-p5-table-addcolumn-method/)

`addColumn()`方法在 p5.js 的 `Table` 对象中用于向 table 对象添加新列。该方法接受一个用于指定列标题的参数，以便后续可以轻松引用。这是一个可选值，如果不指定标题，新列的标题将为空。

## 语法

```
addColumn( [title] )
```

## 参数

该功能接受如上所述的单个参数，描述如下：

*   `title`: 表示新列标题的字符串。这是一个可选参数。

下面的示例说明了 p5.js 中的 `addColumn()`函数：

## 示例 1

```javascript
function setup() {
  createCanvas(500, 300);
  textSize(16);

  saveTableBtn = createButton("Save Table");
  saveTableBtn.position(30, 50);
  saveTableBtn.mouseClicked(saveToFile);

  text("Click on the button to save table to csv", 20, 20);

  // Create the table
  table = new p5.Table();

  // Add two columns
  // using addColumn()
  table.addColumn("author");
  table.addColumn("language");

  // Add two rows
  let newRow = table.addRow();
  newRow.setString("author", "Dennis Ritchie");
  newRow.setString("language", "C");

  newRow = table.addRow();
  newRow.setString("author", "Bjarne Stroustrup");
  newRow.setString("language", "C++");

  text("The table has " + table.getColumnCount() + 
       " columns", 20, 100);
}

function saveToFile() {
  saveTable(table, "saved_table.csv");
}
```