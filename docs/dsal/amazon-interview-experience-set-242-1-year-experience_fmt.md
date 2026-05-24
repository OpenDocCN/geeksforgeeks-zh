# 亚马逊面试体验|第 242 集(1 年体验)

> 原文:[https://www . geesforgeks . org/Amazon-面试-经验-设置-242-1 年-经验/](https://www.geeksforgeeks.org/amazon-interview-experience-set-242-1-year-experience/)

## 电话面试轮: (1 小时)
面试官先自我介绍，然后我自我介绍。需要在共享文档中编写代码。他们在面试前分享了 CollabEdit 链接。
1. [Minimum Platforms](https://practice.geeksforgeeks.org/problems/minimum-platforms/0)
2. [Arrange given numbers to form the biggest number](https://practice.geeksforgeeks.org/problems/largest-number-formed-from-an-array/0)

一周后，他们打电话让我去海得拉巴办公室参加现场面试。他们安排好了一切。
每一轮都以面试官自我介绍开始，然后是我自我介绍。
每一轮结束时，面试官都会问“你有什么问题吗？”。

## 第一轮: (1 小时, 2 位面试官)
1. 关于我的经验、项目和我的角色、我的项目架构的问题
2. 我们能用单次遍历构建一棵树吗？不能。哪种遍历是必须的？中序遍历。为什么？
然后他问了 [https://www.geeksforgeeks.org/construct-a-special-tree-from-given-preorder-traversal/](https://www.geeksforgeeks.org/construct-a-special-tree-from-given-preorder-traversal/)
3. [http://www.geeksforgeeks.org/next-greater-element/](https://www.geeksforgeeks.org/next-greater-element/)

## 第二轮: (1 小时 45 分钟, 1 位面试官)
1. 不使用乘法运算符计算两个数的乘积。
2. 他描述了一个场景，比如你有一个超市，每天都有商品售出，等等……最终问题变成如下：
给定一个文件，其中每行包含一个售出的产品 ID（数百万个产品），有些产品 ID 可能会重复。我们需要找出该文件中唯一售出的商品数量（即唯一售出的）。
3. [链表中的环](https://practice.geeksforgeeks.org/problems/detect-loop-in-linked-list/1)
4. 如何用一个指针实现一个队列
5. [给定一个键，在链表中搜索该键，如果存在，则交换前一个节点和当前节点的值。在我给出解决方案后，他要求我交换节点而不是值。](https://practice.geeksforgeeks.org/problems/swap-kth-node-from-beginning-and-kth-node-from-end-in-a-singly-linked-list/1)
6. [给定一棵二叉树，构造该树的镜像。](https://practice.geeksforgeeks.org/problems/mirror-tree/1)

大约 10-15 个行为问题。一些是：
*   和队友一起上课
*   当你分担队友的负担时
*   你的首相不同意你的意见
*   如果项目时间少了，你会怎么处理
*   你为提高团队效率做了什么
*   你在队里犯的大错
*   你被调到了新团队，但你对这项技术没有任何经验。你将如何处理？
*   你的队友工作不正常，因为你工作的时间更多。你将如何处理这种情况？
*   你想出了主意，但团队不同意
*   您希望改进哪些领域/技术？
*   等等，等等，如此之多

## 第三轮: (1 小时, 2 位面试官)
他们说首先我们会进行技术问题，然后是与经验和项目相关的问题。
1. [给定一个数组，找出缺失的数字。](https://practice.geeksforgeeks.org/problems/missing-number-in-array/0) 数组未排序，元素的范围也未知。
例如：输入：`a[]={1,100}` 输出：`2,3,…99`
输入 `a[]={100,1}` 输出：`2,3,..99`
然后他们要求算法来处理：
*   如果只有一个数字丢失并且范围从 1 到 n
*   如果数组已排序且缺少一个数字

2. [给定二叉树中的两个节点，检查它们是否是堂兄弟节点。](https://practice.geeksforgeeks.org/problems/check-if-two-nodes-are-cousins/1) 堂兄弟节点意味着两者必须在同一层级但没有共同的父节点。
他们要求在一次树的遍历中找出结果（两次遍历也不允许。我是在两次遍历中完成的 🙂）。
他们给了提示，最后我们解决了它。
3. 关于堆的问题
*   如何插入一个值，时间复杂度是多少
*   如何删除一个值，时间复杂度是多少
*   如何用给定的数组构造堆，时间复杂度是多少

## 第四轮: (1 小时, 1 位面试官)
他是最资深的家伙。我感到有点不舒服。
1. 询问当前的项目、我的角色以及与经验相关的问题。
2. 他描述了如下场景：
亚马逊有很多正在外部销售的产品。给定数百万个产品，他可以告诉你如何构建一个带有产品 ID 的 URL 来获取产品详情页面，该页面包含有关产品、评级和评论等信息。
例如：如果产品 ID 是 `123456`，那么 URL 变成 `www.amazon.com/product/123456`
然后问题如下：
*   检索该页面中出现的每个产品（例如：`123456`）的评级（例如：`www.amazon.com/product/123456`）
*   找到每种产品（数百万种产品）的评级后。给出一个算法，找出排名前十的产品。要求我写生产级代码而不是伪代码。
*   然后他扩展了如果产品评级相同（某些产品可能会出现这种情况），那么我们需要考虑评论数量更多的产品
*   上述情况的时间复杂性

3. 你为什么想离开现在的工作？

## 建议：
1. 需要覆盖（优先级从高到低）：树、堆、排序和搜索、链表、栈、队列、字符串、动态规划、贪心、分治、哈希表和碰撞、递归和回溯、位操作、基础图算法、面向对象设计、可扩展性和内存单位、任何缺失的主题。
2. 你应该知道 STL 数据结构的时间复杂度。
例如：对于哈希，我们会说我们可以在 `O(1)` 时间内找到一个值，但如果我们使用 C++ STL，`map` 是用平衡二叉搜索树实现的，所以它需要 `O(logn)` 时间。
3. 你必须准备一些行为问题，至少是标准问题，比如“为什么选择亚马逊？”、“你为什么想离开？”
4. 在纸上练习，因为你需要在面试的所有轮次中在纸上写代码。

如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

[All Practice Problems for Amazon](https://practice.geeksforgeeks.org/company/Amazon/) !

## 相关实践问题
[Largest Number formed from an Array](https://practice.geeksforgeeks.org/problems/largest-number-formed-from-an-array/0)