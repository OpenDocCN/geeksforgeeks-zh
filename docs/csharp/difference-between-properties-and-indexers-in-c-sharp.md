# c# 中属性和索引器的区别

> 原文:[https://www . geesforgeks . org/properties-and-indexers-in-c-sharp/](https://www.geeksforgeeks.org/difference-between-properties-and-indexers-in-c-sharp/)

[c# ](https://www.geeksforgeeks.org/c-sharp-properties/)中的属性是使用访问修饰符来设置和检索以安全方式声明的字段值的命名成员。属性用于抽象和封装对类字段的访问，方法是只定义重要的操作并隐藏它们的实现。属性通过描述的名称调用，可以声明为静态或实例成员。

![Difference-Between-Properties-and-Indexers-in-CSharp](img/f3dd2c50c81a73391c66b45d2be2d4b4.png)

**在 C# 中声明属性的语法:**

```cs
[access_modifier] [return_type] [PropertyName]  
{
//body of property
}

```

[c# ](https://www.geeksforgeeks.org/c-sharp-indexers/)中的索引器是数据成员，它们充当一个数组，允许您以相同的方式访问要索引的对象中的数据。索引器总是声明为实例成员，而不是静态成员。索引器的实现方式与属性相同，只是索引器的声明必须至少有一个参数。

**在 C# 中创建索引器的语法:**

```cs
[access_modifier] [return_type] this [parameter]
{
  get 
  {
     // return value
  }
  set 
  {
    // return value
  }
}

```

### C# 中属性和索引器的区别

|  | 性能 | 索引器 |
| --- | --- | --- |
| 1. | 属性通过给出唯一的名称来声明。 | 索引器在声明时没有给出名称。 |
| 2. | 属性由名称标识 | 而索引器由签名标识。 |
| 3. | 属性可以声明为静态成员或实例成员。 | 索引器总是声明为实例成员，而不是静态成员。 |
| 4. | 属性通过描述的名称调用。 | 索引器是使用创建的对象的索引来调用的。 |
| 5. | 属性在创建时不需要这个关键字。 | 索引器在其关键字中需要这个关键字。 |
| 6. | 属性的 get 访问器没有任何参数。 | 属性的 get 访问器包含与索引器相同的正确参数列表。 |