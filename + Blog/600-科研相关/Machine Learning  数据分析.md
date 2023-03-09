[[Blog_MOC]] #Permanent

# A Visual Guide to Learning Data Science

> 本文根据 [Chanin Nantasenamat](https://chanin.streamlitapp.com/) 的 [Blog](https://towardsdatascience.com/how-to-build-a-machine-learning-model-439ab8fb3fb1) 翻译。

Data Science 的内容非常庞杂，初看很劝退，但实际上并非如此。本文的作者期望让数据科学变得更有乐趣。以此为基础，Chanin 尝试在 ipad 上涂鸦，绘制机器学习模型所需的元素，更生动形相的带大家入门。

# 数据集
数据集是构建机器学习模型的起点。简单地说，数据集本质上是一个 M×N 矩阵，其中 M 表示列（特征），N 表示行（样本）。
列可以分解为 X 和 Y。
X 是几个类似术语的同义词，如特征、自变量和输入变量。
Y 也是几个术语的同义词，即类标签、因变量和输出变量。
![[Pasted image 20220517095141.png]]

值得注意的是，用于监督学习 Supervised Learning（可执行回归或分类）的数据集将同时包含 X 和 Y，而可用于无监督学习 Unsupervised Learning 的数据集将仅包含 X。这两者的概念将在后面的模块详细讲解。
此外，如果 Y 包含定量值，那么该数据集（由 X 和 Y 组成）可用于回归任务，而如果 Y 包含定性值，那么该数据集（由 X 和 Y 组成）可用于分类任务。

# Exploratory Data Analysis
Exploratory data analysis (EDA) 探索性数据分析可以让我们初步了解和熟悉数据。「观察」是开展研究的第一步。
EDA 的主要方法包括：
1.  描述性统计 - 平均数、中位数、模式、标准差
2.  数据可视化--热图（分析特征的内部关联）、箱形图（组别差异可视化）、散点图（特征之间关联可视化）、主成分分析（聚类分布可视化）等。
3.  数据塑造--对数据进行透视，对数据进行分组，对数据进行过滤，等等。

![[Pasted image 20220517111945.png]]
![[Pasted image 20220517112000.png]]
![[Pasted image 20220517112012.png]]

**想要了解上述概念，实践很重要！**
>上述可视化方法的视频教程，可以查看 Chanin 的 youtube 频道：[https://www.youtube.com/watch?v=9m4n2xVzk9o](https://www.youtube.com/watch?v=9m4n2xVzk9o) ， 其中使用到的 Jupter Notebook 代码托管在 Github 上：[https://github.com/dataprofessor/code/blob/master/python/pandas_exploratory_data_analysis.ipynb](https://github.com/dataprofessor/code/blob/master/python/pandas_exploratory_data_analysis.ipynb)

# 数据预处理
数据预处理（也被称为数据清洗、数据处理或数据处理）是对数据进行各种检查和审查的过程，插入缺失值、校对拼写错误、标准化、数据转换（例如对数转换）等。
数据质量对生成的模型的质量有决定性影响。因此，为了达到最好的模型质量，应在数据预处理阶段花费大量精力。通常，数据预处理花费的时间可以占 Data Science 项目的 80%，而实际的模型建立和分析是剩下 20%。

# 数据拆分
## Train-Test Split
为了更好的评估和优化预处理后的数据集，可将数据分割成两部分，分别是训练集和测试集。训练集一般占数据总量的 80% 左右，测试集占 20% 左右。
先用训练集建立一个预测模型，随后用训练好的模型分析测试集，测试集上的效果越好，则模型的质量更佳。为了获得更好的模型，需要进行超参数优化，这个过程可以更科学地训练出更高效的机器学习模型。
![[Pasted image 20220517130211.png]]

## Train-Validation-Test Split
另一种常见的数据分割方法是将数据分割成三部分：训练集、验证集和测试集。与上一种方法中不同的是，训练集用于评估模型的性能，可以根据检验结果反过来调整模型参数，主要是超参数。测试集仅发挥测试功能，不介入模型的调整和优化。

![[Pasted image 20220517130430.png]]

## Cross-Validation
>不是所有数据都适合使用 cross-validation, 例如时间序列数据，就不能随便均分训练和测试集。交叉检验在深度学习标准数据集中一般不会用到，仅在特定条件下适用，且能有很好的效果。

对于样本数量不大，样本分布不充分的样本集而言，单一验证方法会因为样本集分割变化而导致最终的训练和测试结果出现比较严重的动荡。N-fold cross-validation (CV)将数据集划分为 N 份（常见的有 5 份和 10 份）（如下图所示），可以“充分利用”有限的数据找到合适的模型参数，防止过度拟合。其中 N-1 份为训练集，1 份为测试集，用以上 N 种情况的训练集训练得到模型的参数（如下图）。结果部分，可以选择平均 N 次训练的模型参数，或用 N 次结果中 validation error 对小的那个模型参数（不常用）。

![[Pasted image 20220517132004.png]]

# Model Building
现在，实际应用的机会来了。根据目标变量（通常被称为 Y 变量）的数据类型（定性或定量），我们将建立一个分类（如果 Y 是定性的）或回归（如果 Y 是定量的）模型。

## Learning Algorithms
机器学习的算法大致可以分为三个类型
1.  Supervised learning 监督学习是在了解输入和输出结果之间的关系的基础上，根据这种已知关系训练得到的最优模型。
2.  Unsupervised learning 非监督学习则直接对数据进行建模。没有给定事先标记过的训练范例，所用的数据没有属性或标签这一概念。事先不知道输入数据对应的输出结果是什么。无监督学习大致可以分为聚类和降维两大类。
3.  Reinforcement learning
