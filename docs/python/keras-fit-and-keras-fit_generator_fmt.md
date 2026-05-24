# Keras中的`fit()`与`fit_generator()`

> 原文：[https://www.geeksforgeeks.org/keras-fit-and-keras-fit_generator/](https://www.geeksforgeeks.org/keras-fit-and-keras-fit_generator/)

Python中的`keras.fit()`和`keras.fit_generator()`是两个用于训练机器学习和深度学习模型的独立函数。它们可以完成相似的任务，但主要区别在于何时使用哪一个。

## `fit()`

### 语法

```py
fit(object, x = NULL, y = NULL, batch_size = NULL, epochs = 10,
  verbose = getOption("keras.fit_verbose", default = 1),
  callbacks = NULL, view_metrics = getOption("keras.view_metrics",
  default = "auto"), validation_split = 0, validation_data = NULL,
  shuffle = TRUE, class_weight = NULL, sample_weight = NULL,
  initial_epoch = 0, steps_per_epoch = NULL, validation_steps = NULL,
  ...)
```

### 理解几个重要参数

```py
-> object : 要训练的模型。
-> x : 我们的训练数据。可以是向量、数组或矩阵。
-> y : 我们的训练标签。可以是向量、数组或矩阵。
-> batch_size : 可以取任何整数值或NULL，默认设置为32。它指定了每个梯度更新的样本数。
-> epochs : 整数，表示我们想要训练模型的轮数。
-> verbose : 指定详细模式（0 = 静默，1 = 进度条，2 = 每轮一行）。
-> shuffle : 是否在每个训练轮次之前打乱训练数据。
-> steps_per_epoch : 指定一个训练轮次结束并开始下一个轮次之前采取的总步数。默认值为NULL。
```

### 如何使用`fit`

```py
model.fit(Xtrain, Ytrain, batch_size = 32, epochs = 100)
```

这里我们首先输入训练数据(`Xtrain`)和训练标签(`Ytrain`)。然后，我们让模型在批量大小为32的情况下训练100个轮次。

当我们调用`fit()`函数时，它做出以下假设：
*   整个训练集可以装入计算机的内存。
*   第二次调用`fit`方法不会重新初始化我们已经训练好的权重，这意味着我们可以连续调用`fit`。
*   不需要使用Keras生成器（即没有数据增强）。
*   原始数据本身用于训练网络，这意味着原始数据必须能存储在内存中。

## `fit_generator()`

### 语法

```py
fit_generator(object, generator, steps_per_epoch, epochs = 1,
  verbose = getOption("keras.fit_verbose", default = 1),
  callbacks = NULL, view_metrics = getOption("keras.view_metrics",
  default = "auto"), validation_data = NULL, validation_steps = NULL,
  class_weight = NULL, max_queue_size = 10, workers = 1,
  initial_epoch = 0)
```

### 理解几个重要参数

```py
-> object : Keras模型对象。
-> generator : 一个生成器，其输出必须是以下形式的列表：
                      - (inputs, targets)
                      - (inputs, targets, sample_weights)
生成器的单次输出构成一个批次，因此列表中的所有数组长度必须等于批次大小。生成器应无限次循环遍历其数据，不应返回或退出。
-> steps_per_epoch : 指定从生成器中获取数据，直到一个轮次结束、下一个轮次开始所采取的总步数。我们可以将steps_per_epoch的值计算为数据集中的样本总数除以批次大小。
-> epochs : 整数，表示我们想要训练模型的轮数。
-> verbose : 指定详细模式（0 = 静默，1 = 进度条，2 = 每轮一行）。
-> callbacks : 在模型训练期间应用的回调函数列表。
-> validation_data : 可以是以下之一：
                      - 输入和标签的列表
                      - 一个生成器
                      - 输入、标签和样本权重的列表，可用于在任何轮次结束后评估模型的损失和指标。
-> validation_steps : 仅当validation_data是一个生成器时，此参数才可用。它指定在每个轮次停止之前从生成器中获取的总步数，其值计算为验证数据集中的数据点总数除以验证批次大小。
```

### 如何使用`fit_generator`

```py
# 通过训练图像生成器执行数据增强
dataAugmentaion = ImageDataGenerator(rotation_range = 30, zoom_range = 0.20,
fill_mode = "nearest", shear_range = 0.20, horizontal_flip = True,
width_shift_range = 0.1, height_shift_range = 0.1)

# 训练模型
model.fit_generator(dataAugmentaion.flow(trainX, trainY, batch_size = 32),
 validation_data = (testX, testY), steps_per_epoch = len(trainX) // 32,
 epochs = 10)
```

在这里，我们为10个轮次训练网络，默认批量大小为32。

对于较小且不太复杂的数据集，建议使用`fit`函数。而在处理真实数据集时，情况则不那么简单，因为真实数据集通常规模很大，难以放入计算机内存。处理这些数据集更具挑战性，其中一个关键步骤是进行数据增强，以避免模型过拟合并提高模型的泛化能力。

**数据增强**是一种从现有训练数据集中人工创建新数据集进行训练的方法，旨在利用现有数据量来提高深度学习神经网络的性能。这是一种正则化形式，能使我们的模型比以前更好地泛化。这里我们使用Keras的`ImageDataGenerator`对象来应用数据增强，对图像进行随机平移、调整大小、旋转等操作。每一批新数据都是根据提供给`ImageDataGenerator`的参数随机调整的。

当我们调用`fit_generator()`函数时，它做出以下假设：
*   Keras首先调用生成器函数。
*   生成器函数（如`dataAugmentaion`）为`fit_generator()`函数提供数据。
*   `fit_generator()`函数首先接受一批数据集，然后对其进行反向传播，接着更新模型中的权重。
*   对于指定的轮次数（在我们的例子中是10），重复此过程。

## 总结

我们已经学习了用于训练深度学习神经网络的`Keras.fit`和`Keras.fit_generator`函数的区别。
*   **当整个训练数据集可以放入内存且不应用数据增强时，使用`fit`**。
*   **当数据集太大无法放入内存或需要应用数据增强时，使用`fit_generator`**。