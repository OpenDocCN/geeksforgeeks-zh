# Pytorch 函数–张量()，fill_diagnol()，append()，index_copy()

> 原文:[https://www . geesforgeks . org/py torch-functions-tesnor-fill _ diagnol-append-index _ copy/](https://www.geeksforgeeks.org/pytorch-functions-tesnor-fill_diagnol-append-index_copy/)

本文旨在分享一些 PyTorch 函数，这些函数将对您的深度学习和数据科学之旅有很大帮助。将使用两个编写示例和一个不能使用这些函数的示例来解释每个函数。让我们开始吧。

PyTorch 是一个开源的机器学习库，它包含一个张量库，能够创建一个标量、一个向量、一个矩阵或者简而言之我们可以创建一个 n 维矩阵。它用于计算机视觉和自然语言处理，主要由脸书的研究实验室开发。它是开源软件，并根据修改后的 BSD(巴克利软件分发)许可证发布。

**我们的四大功能:**

*   `torch.tensor()`
*   `fill_diagonal_()`
*   `expand(*size)`
*   `index_copy_()`

## 功能 1–torch.tensor()

这个函数使我们能够创建 PyTorch 张量。张量可以是任何东西，比如它可以是标量，它可以是一维矩阵，它可以是 n 维矩阵。

**为什么我们需要张量？**

每当我们想要在我们的深度学习模型中计算任何矩阵计算时，第一个也是最重要的任务是将我们的数据帧转换成 numpy 数组，然后转换成张量，或者如果我们正在处理一些图像分类问题，我们必须将这些图像转换成 PyTorch 张量。

**语法和参数:**

```py
data:          data that we want to convert into tensor.
dtype:         data type of that data whether it is torch32, torch64 etc.
device:        type of your device whether it is cpu or gpu(cuda).
requires_grad: if it is True, then gradients of that tensor will be saved in
               torch.grad property.
```

**代码:使用此函数创建向量。**

```py
# vector of int datatype
t1 = torch.tensor([1, 2, 3, 7, 1])

# if one float can convert the whole tensor into flaat
t2 = torch.tensor([4, 2, 5, .9])

# we can convert the tensor data type
t3 = torch.tensor([2, 6, 1, 6, 8.], dtype = torch.int32)
```

在上例中， `t1` 是包含简单一维数组的张量。在， `t2` 我们在火炬里面。张量我们已经使用了单个浮点元素，但是由于这个单个元素，我们的整个 `t2` 张量已经转换为浮点类型。在， `t3` 中，我们强制设置了 `dtype = torch.int32` 来更改张量的数据类型。

**代码:使用矩阵创建张量。**

```py
t4 = torch.tensor([[3, 6, 8], [2, 6, 8], [0, 7, 4]])
```

在上面的例子中，我们创建了一个 `t4` 张量，它是 *3*3* 张量。类似地，如果我们想创建一个 n 维张量，我们可以创建它，就像具有 4 维或更多维的张量一样。

**例 3(最常见的错误):**

在这个例子中，我们将讨论在创建张量的过程中经常尝试的错误。在示例 2 中，我们了解到可以创建 n 维数组。

**代码:**

```py
t4 = torch.tensor([[3, 6, 8], [2, 6, 8], [0, 7, 4]])
```

在这里，我们创建了一个具有两个维度的张量，但是每个维度并不包含相等数量的元素，即每个维度没有相同的长度。正因为如此。编译器会抛出一个错误，说…

> ValueError Traceback (most recent call last)
> <ipython-input-21> in <module>
> ----> 1 torch.tensor([[1,2],[3,4,5]])
>
> ValueError: expected sequence of length 2 at dim 1 (got 3)

所以我们学到的是，我们可以创建一个 n 维的数组，但是所有的维度应该有相同的长度，否则我们会得到一个错误。

## 函数 2–fill_diagonal_()

`fill_diagonal_()` 用 `fill_value` 填充主对角线，但是该矩阵应该是 2D 矩阵，对于 `ndim > 2` 的矩阵，行数应该等于列数，如果不是，那么我们必须设置 `wrap = True`，以便对角线值可以重复。

**语法和参数:**
`fill_diagonal_(fill_value, wrap=False) -> Tensor`

```py
fill_value: tensor matrix whose diagonals we want to fill.
wrap:       it takes boolean, it enables us to work with a non-square matrix.
```

**例 1:**

在这个例子中，首先我们将使用 `torch.zeros(3, 3)` 创建一个大小为(3，3)的张量。

```py
a = torch.zeros(3, 3)
```

`a` 是大小为(3，3)的张量，它的所有元素都为零，即 `a` 是零矩阵

现在我们想要的是用 4 替换它的所有对角线值，所以我们可以在 `fill_diagonal_()` 的帮助下做到这一点。

```py
a.fill_diagonal_(fill_value = 4, wrap = False)

print(a)
```

如果我们看张量 `a`，它会是这样的

> tensor([[4., 0., 0.],
>         [0., 4., 0.],
>         [0., 0., 4.]])

**例 2 :**

从示例 1 中我们了解到，我们可以使用此函数替换对角线元素，但是如果我们有一个行数不等于列数的张量，那么在这种情况下，我们必须设置 `fill_diagonal_()` 的“wrap”参数。

你可以看看这段代码，

```py
b = torch.zeros([9, 4])

# without putting wrap = True

A = b.fill_diagonal_(5, wrap = False)
```

在上面的代码中，首先我们创建了一个大小为(9，4)的零张量，然后我们用 5 填充它的对角线，但是我们没有设置 `wrap = True`。现在我们来看看张量 `A`，

> tensor([[5., 0., 0., 0.],
>         [0., 5., 0., 0.],
>         [0., 0., 5., 0.],
>         [0., 0., 0., 5.],
>         [0., 0., 0., 0.],
>         [0., 0., 0., 0.],
>         [0., 0., 0., 0.],
>         [0., 0., 0., 0.],
>         [0., 0., 0., 0.]])

这里你可以看到，一旦对角线到达某个特定尺寸的长度末端，那么对角线的其余部分就不会改变

所以为了解决这个问题，我们必须将包装设置为真。看看这段代码，

```py
B = b.fill_diagonal_(6, True)

print(B)
```

现在看看张量 `B`

> tensor([[6., 0., 0., 0.],
>         [0., 6., 0., 0.],
>         [0., 0., 6., 0.],
>         [0., 0., 0., 6.],
>         [0., 0., 0., 0.],
>         [6., 0., 0., 0.],
>         [0., 6., 0., 0.],
>         [0., 0., 6., 0.],
>         [0., 0., 0., 6.]])

你会发现，即使对角线到达了一个特定维度的末端，它也会再次开始改变下一个维度的对角线。

**例 3(常见错误):**

让我们假设你有一个大小为(4，5)的零张量，你想用 3 改变它的对角线，但是如果你想把那个张量的数据类型改变为 `int32`，那么你可能会想在 `fill_diagonal_()` 中设置一个 `dtype = torch.int32` 作为，

```py
B = b.fill_diagonal_(6, True)

print(B)
```

但是，这里你必须记住一件小事，`fill_diagonal_()` 只接受两个参数作为参数，一个是你想放入对角线的数据，另一个是处理非正方形张量的 `wrap`，

所以，上面的代码会抛出一个错误，

> TypeError
> Traceback (most recent call last)
> <ipython-input-26> in <module>
> ----> 1 a = torch.zeros(4,5)
>       2 a.fill_diagonal_(3, dtype=torch.float32)
>
> TypeError: fill_diagonal_() got an unexpected keyword argument 'dtype'

## 功能 3–expand(*size)

*   返回自我张量的新视图，其中单个维度扩展到更大的尺寸。
*   将 -1 作为尺寸的大小意味着不改变该尺寸的大小。
*   张量也可以扩展到更多的维度，新的维度将被附加在前面。对于新尺寸，尺寸不能设置为 -1。
*   扩展张量不会分配新的内存，只会在现有的张量上创建一个新的视图，通过将步幅设置为 0，将尺寸为 1 的维度扩展到更大的尺寸。大小为 1 的任何维度都可以扩展为任意值，而无需分配新内存。

**语法和参数:**

```py
expand(*size)
```

**示例 1 :**
如果我们有一个单例维度矩阵，那么我们可以使用 `expand()` 扩展它的单例维度

```py
a = torch.tensor([[5], [3], [8], [4]])

a.size()

a.expand(4, 8)
```

张量 `a` 的 look，

> tensor([[5, 5, 5, 5, 5, 5, 5, 5],
>         [3, 3, 3, 3, 3, 3, 3, 3],
>         [8, 8, 8, 8, 8, 8, 8, 8],
>         [4, 4, 4, 4, 4, 4, 4, 4]])

最初，`a` 是一个包含单例维度的矩阵，现在使用 `expand()` 我们将其单例维度扩展为 8

**例 2:**

```py
b = torch.tensor([[7], [3], [4]])

b.size()

b.expand(3, -1)
```

在上面的例子中，我们把第二个尺寸设为 -1，这意味着我们不想扩展它的尺寸。

**例 3(常见错误):**

```py
c = torch.tensor([[4, 6], [9, 6]])

c.size()  # this matrix didn't any singleton dimension

c.expand(2, 6)
```

这抛出了一个错误，因为根据 `expand()` 的定义，我们必须将一个大小与非单例维度匹配，但是因为我们有两个单例维度，所以我们不能满足条件。错误…

> RuntimeError: The expanded size of the tensor (6) must match the existing size of the non-singleton dimension 1 (2). Target size: [2, 6]. Tensor size: [2, 2]

## 函数 4–index_copy_(dim, index, tensor) -> Tensor

它使我们能够在给定的索引中把张量复制成自张量，该索引在索引张量中定义，它包含三个参数

*   `dim`
*   保持指数顺序的指数张量 `index`
*   我们想在自我张量中复制的张量 `tensor`

**例 1:**

```py
self_tensor = torch.zeros(6, 3)

t = torch.tensor([[7, 6, 9], [3, 9, 1], [0, 1, 9]], dtype = torch.float)

i = torch.tensor([3, 1, 0])

self_tensor.index_copy_(0, i, t)
```

现在，如果你看看输出张量…

> tensor([[0., 1., 9.],
>         [3., 9., 1.],
>         [0., 0., 0.],
>         [7., 6., 9.],
>         [0., 0., 0.],
>         [0., 0., 0.]])

在上面的例子中

我们把 `t` 张量复制成了阶在 `i` 张量中定义的自张量

**例 2:**

```py
a = torch.tensor([[1, 8], [9, 5], [1, 5]])

b = torch.tensor([[3, 5], [9, 0], [2, 2]])

i = torch.tensor([2, 1, 0])

a.index_copy_(0, i, b)
```

输出张量:

> tensor([[2, 2],
>         [9, 0],
>         [3, 5]])

我们可以用两个非零张量执行与示例 1 相同的操作

**例 3(常见错误)**

```py
a = torch.tensor([[8, 3], [1, 0]])

b = torch.tensor([[3, 9]])

i = torch.tensor([1])

a.index_copy(1, i, b)
```

> RuntimeError
> Traceback (most recent call last)
> <ipython-input-6-FB983DC7560F> in <module>
>       3 b = torch.tensor([[3, 9]])
>       4 i = torch.tensor([1])
> ----> 5 a.index_copy_(1, i, b)
>
> RuntimeError: index_copy_(): Source/Target slices have different shapes: dimension 1 for the source slice: 2, dimension 0 for the source slice: 1.

上面的例子抛出了一个错误，因为我们试图给出 `dim = 1`

但是，索引的 `dim`th 元素应该包含与我们的 `b` 张量相同数量的元素。

**结论:**所以每当我们需要将一个张量复制成一个具有特定顺序的自张量时，我们可以使用这个函数

**参考链接–**

*   [PyTorch 官方文档链接](https://PyTorch.org/docs/stable/tensors.html)
*   [整码笔记本](https://jovian.ml/sachinsom507/01-tensor-operations-d80d4)