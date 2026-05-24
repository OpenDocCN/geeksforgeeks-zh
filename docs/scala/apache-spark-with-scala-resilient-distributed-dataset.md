# 带 Scala 的 Apache Spark–弹性分布式数据集

> 原文:[https://www . geesforgeks . org/Apache-spark-with-Scala-resilient-distributed-dataset/](https://www.geeksforgeeks.org/apache-spark-with-scala-resilient-distributed-dataset/)

在现代世界，我们每天都在处理巨大的数据集。数据的增长速度甚至超过了处理速度。对如此大的数据进行计算通常是通过使用分布式系统来实现的。分布式系统由并行运行进程并在需要时相互通信的集群(节点/联网计算机)组成。

**Apache Spark** 是大规模数据处理的统一分析引擎。它提供了 Java、Scala、 [Python 和 R](https://www.geeksforgeeks.org/r-vs-python-datascience/) 的高级 API，以及支持通用执行图的优化引擎。这一组丰富的功能和库支持更高级别的工具，如用于 SQL 和结构化数据处理的 Spark SQL、用于机器学习的 MLlib、用于图形处理的 GraphX 以及用于增量计算和流处理的结构化流。在本文中，我们将使用 [Scala](https://www.geeksforgeeks.org/scala-programming-language/) 学习 Apache spark(2 . x 版本)。

**一些基本概念:**

1.  [**[RDD (Elastic Distributed Data Set)**](https://www.geeksforgeeks.org/introduction-pyspark-distributed-computing-apache-spark/) **–** It is an immutable set of distributed objects. As far as RDD is concerned, data set is the main part, which is divided into logical partitions.
2.  **Sparksession–** The entry point for programming Spark with data set and data framework application programming interface.

我们将仅出于演示目的使用 Scala IDE。运行下面的代码需要一个专用的 spark 编译器。按照[链接](https://cloud.google.com/dataproc/docs/tutorials/spark-scala)运行以下代码。

让我们在 spark 中创建第一个数据帧。

## 斯卡拉

```scala
// Importing SparkSession
import org.apache.spark.sql.SparkSession

// Creating SparkSession object
val sparkSession = SparkSession.builder()
                   .appName("My First Spark Application")
                   .master("local").getOrCreate()

// Loading sparkContext
val sparkContext = sparkSession.sparkContext

// Creating an RDD
val intArray = Array(1, 2, 3, 4, 5, 6, 7, 8, 9, 10)

// parallelize method creates partitions, which additionally
// takes integer argument to specifies the number of partitions.
// Here we are using 3 partitions.

val intRDD = sparkContext.parallelize(intArray, 3)

// Printing number of partitions
println(s"Number of partitions in intRDD : ${intRDD.partitions.size}")

// Printing first element of RDD
println(s"First element in intRDD : ${intRDD.first}")

// Creating string from RDD
// take(n) function is used to fetch n elements from
// RDD and returns an Array.
// Then we will convert the Array to string using
// mkString function in scala.
val strFromRDD = intRDD.take(intRDD.count.toInt).mkString(", ")
println(s"String from intRDD : ${strFromRDD}")

// Printing contents of RDD
// collect function is used to retrieve all the data in an RDD.
println("Printing intRDD: ")
intRDD.collect().foreach(println)
```

**输出:**

```scala
Number of partitions in intRDD : 3
First element in intRDD : 1
String from intRDD : 1, 2, 3, 4, 5, 6, 7, 8, 9, 10
Printing intRDD: 
1
2
3
4
5
6
7
8
9
10
```