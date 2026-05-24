# SQL |替代报价运算符

> 原文:[https://www . geesforgeks . org/SQL-alternative-quote-operator/](https://www.geeksforgeeks.org/sql-alternative-quote-operator/)

这篇文章是 [SQL 串联运算符](https://www.geeksforgeeks.org/sql-concatenation-operator/)的延续。

现在，假设我们想在文字值中使用**撇号**，但是不能直接使用。

参见**错误的**代码:
选择 id，名字，姓氏，薪水，
名字||“有薪水的”| |薪水
为“新”FROM one

所以上面我们得到了错误，因为 Oracle 服务器认为**第一个撇号**代表**起始字面**，而**第二个撇号**代表**结束字面**，那么**第三个撇号**呢？？？。这就是我们出错的原因。

### 

**替代报价操作员( *q* )**

:
为了**克服**上述问题甲骨文引入了一个名为**的操作符替代报价操作符** (q)。

让我们来看一个例子:

```sql
Query that uses Alternative Quote Operator(q)
SELECT id, first_name, last_name, salary,
first_name||q'{ has salary's }'||salary 
AS "new" FROM myTable

```

```sql

Output:
See, we are able to use apostrophe in the
new column as a literal value of myTable 

ID  FIRST_NAME LAST_NAME  SALARY            new
3    Shane     Watson     50000    Shane has salary's 50000
1    Rajat     Rawat      10000    Rajat has salary's 10000
2    Geeks     ForGeeks   20000    Geeks has salary's 20000
3    MS        Dhoni      90000    MS    has salary's 90000

```

如上所述，**q ' { T1 }表示我们的文字值的开始，然后我们使用 **}'** 表示我们的文字值的结束。所以看这里，我们很容易地在我们的文字值中使用了撇号(意味着我们很容易地在工资中使用【T4 的】**)，没有任何错误，这就是为什么我们得到输出，因为 Rajat 有工资**的** 50000。

所以要在字面上使用撇号，我们首先需要使用 **q** ，也就是众所周知的**替代引用运算符**，之后我们需要使用撇号 **'** ，之后我们需要使用**分隔符**，在分隔符之后我们写我们的字面值， 当我们写完我们的文字值后，我们需要再次关闭分隔符**，在之前我们已经打开了**，之后我们需要再次放一个**撇号**，因此这样我们可以在我们的文字值中使用撇号。 这个概念被称为**替代报价运算符** (q)。****

**我们可以使用**任意字符**，如 **{** ， **<** ， **(** ， **[** ，**！**或任何字符作为**分隔符**。这些字符被称为**分隔符**。**

### 

****1 另一个例子****

**：**

****不使用报价运算符**:**

```sql
Here we get **Error** since we are using **apostrophe** in our literal value directly.

**Error** code below:
SELECT id, name, dept, name||' work's in '||dept||'
 department' AS "work" FROM myTable2 
```

****使用报价运算符** :
从 myTable2 中选择 id、姓名、部门、姓名||q'[工作所在]' | |部门||'
部门'作为“工作”**

```sql
**Output**:
See, we are able to use apostrophe in the 
work column as a literal value of myTable2 

ID NAME      DEPT           work
1  RR       Executive  RR work's in 'Executive department
2  GFG      HR         GFG work's in 'HR department
3  Steve    Sales      Steve work's in 'Sales department
4  Bhuvi    CSE        Bhuvi work's in 'CSE department 
```

**如上所述， **q'[** 表示我们的文字值的开始，我们使用**'**表示我们的文字值的结束。所以看这里，我们在我们的文字值中很容易地使用了**撇号**(意味着我们在工作中很容易地使用**)没有任何错误，这就是为什么我们在执行部门得到的输出是 RR **工作的**。]****

****在上面我们使用 **[** 作为分隔符，所以它是**而不是**使用分隔符的限制意味着我们可以使用任何字符作为分隔符。****

******参考:**
[关于替代报价操作员](https://learningsql.blogspot.in/2014/12/alternative-quote-q-operator.html)
[在线执行 SQL 查询](https://livesql.oracle.com/apex/livesql/file/index.html)****