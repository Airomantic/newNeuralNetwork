KAN: [Kolmogorov–Arnold Networks](https://arxiv.org/pdf/2404.19756)

Refer to : https://github.com/AntonioTepsich/Convolutional-KANs

柯尔莫戈罗夫-阿诺德-摩泽尔定理（Kolmogorov-Arnold-Moser, KAM theorem）是动力系统理论中的一个重要结果，主要研究在微扰下可积哈密顿系统的行为。这个定理说明在某些条件下，尽管系统受到微扰，仍有许多准周期轨道保持存在。以下是对KAM定理的详细解释：

## 1. 背景与基本概念
- 可积系统：一个可积哈密顿系统具有与自由度相同数量的独立、守恒的哈密顿量。在这种系统中，运动可以在相空间中被精确地解出，通常表现为在某些约化坐标系中的准周期运动。
- 准周期运动：如果一个系统的运动可以表示为多个独立频率的组合，那么它是准周期的。这种运动在相空间中对应于一个环面（通常称为tori）。
## 2. KAM定理的陈述
KAM定理考虑了一个几乎可积的哈密顿系统，这意味着哈密顿量可以分解为一个完全可积部分 H_0 和一个小扰动
```math
\epsilon H_1
```
得到：
```math
H = H_0 + \epsilon H_1
```
其中 ϵ 是一个小参数，表示扰动的强度。
KAM定理的主要结论是：

- 在适当的非共振条件和一定的小扰动（即 ϵ 足够小）下，原始可积系统的大多数准周期环面（tori）在扰动下不会被完全破坏。
- 这些环面会发生变形，但依然存在，并且运动依旧是准周期的。

### 3. 具体条件
KAM定理的适用条件涉及一些技术细节，包括：

- 非共振条件：原始系统的频率不能满足某些简单的共振关系。这通常以所谓的“非共振”或“Diohantine条件”来描述，即频率向量的任何非平凡线性组合与整数系数的距离不能太小。
- 小扰动：扰动项 ϵ H_1 必须足够小。定理表明，存在一个阈值，若 ϵ 小于这个阈值，则定理的结论成立。
- 光滑性和解析性：系统的哈密顿量需要具有一定的光滑性，通常是解析的（或至少是足够高阶可微的）。
### 4. 物理解释
在哈密顿力学中，KAM定理具有重要的物理意义。它说明在许多实际物理系统中，即使存在微小的扰动，系统中的某些结构（如准周期运动）依然是稳定的，不会立即转变为混沌运动。这种稳定性在天文学中尤为重要，例如行星轨道的长期稳定性可以部分归因于KAM定理。
### 5. 影响与应用
数学和物理学均有影响，它不仅揭示了哈密顿系统的稳定性，还促进了混沌理论的发展。通过了解哪些轨道在扰动下保持稳定，研究人员能够更好地理解复杂系统的行为。
（KAM）定理展示了在小扰动下，许多可积哈密顿系统的准周期轨道依然保持稳定，这为分析和理解动力系统的长期行为提供了关键的理论基础。
#### 5.1 在KAN中的应用
KAM 定理对于证明bounded domain上的any multivariate continuous function都可以表示为单个变量的连续函数和加法运算的有限组合至关重要。
##### 借用的关键要素：
1. Multivariate Function Decomposition:
- The paper utilizes the KAM theorem's insight that a multivariate function can be decomposed into a sum of univariate functions. 多元函数可以分解为单变量函数的总和
This decomposition is crucial for the structure of KANs, where the network architecture explicitly parameterizes univariate functions as B-spline curves. 将单变量函数显式参数化为 B 样条曲线
2. Network Architecture Design:
- Inspired by the representation theorem, KANs are designed to handle input-output pairs by approximating the functionf(x). The network consists of layers where each layer's nodes compute <u>univariate functions and sum them</u>, as suggested by the KAM theorem's representation.
3. **Generalization** Beyond Depth-2 Networks:
- While the original theorem typically applies to shallow (two-layer) networks, the paper extends this to deeper networks, <u>arguing that more layers can better capture the complexities of **real-world functions**</u>. This involves stacking more KAN layers, each adhering to the decomposition principles of the KAM theorem.
##### Practical Implications:
1. Expressive Power and Efficiency:
- KANs, based on the KAM theorem, are shown to outperform traditional Multi-Layer Perceptrons (MLPs) in terms of both accuracy and interpretability. This is because KANs <u>can more efficiently learn the **compositional structure** of data</u>, thus avoiding the **curse of dimensionality** that plagues traditional neural networks.
2. Smooth and Sparse Representations:平滑和稀疏表示:
- The paper emphasizes that most real-world functions are smooth and have sparse compositional structures. KANs are particularly well-suited for such tasks because they can provide **smooth Kolmogorov-Arnold representations**, making them more practical for machine learning applications.