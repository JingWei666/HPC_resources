# CUDA学习路径

## CUDA教学： https://zhuanlan.zhihu.com/p/34587739

## 项目
Ok, here's a project for you:

Implement the "Addition is all you need" Kernel in a readable manner with lots of comments using ThunderKittens in NanoGPT-TK as an explanatory example and contribute it to their Open Sources repo.

Background: The "Addition is all you need" paper proposed an alternative to Attention Kernels, using only additive arithmetic. They claim similar performance as Attention at much lower power usage. Great stuff. Only I don:'t think there are many Kernels released yet.Addition is all you need: paper: https://arxiv.org/html/2410.00907v1

NanoGPT-TK https://github.com/HazyResearch/nanoGPT-TK

ThunderKittens is a C++ template library that brings simplified Triton-style CUDA programming to CUDA C++. Read the article, you will learn a lot: https://hazyresearch.stanford.edu/blog/2024-05-12-tk

ThunderKittens is extremely well written and still small enough that you can read through it. You can lean C++ Template Metaprogramming done right from there.

(Sidenote: Most production level Kernels today use NVIDIAs Cutlass/Cute library or OpenAI Triton today, but I cannot recommend Cutlass or Cute, they are badly documented and intransparent, and their codebase requires you to reverse engineer and experiment for months before you can be fully productive)

NanoGPT-TK aims to implement a reference GPT-style LLM from first principles. Using ThunderKittens. NanoGPT (without TK) is the original project from Andrej Karpathy and a great learning resource as well.

If, on the other hand, you are allowed to use Triton, by all.means, do it, unless you really want to learn modern CUDA C++ specifically. The future will be domain-specific languages like Triton as the AI accelerator hardware will cease to be general-purpose.

As a sidenote, such a project could easily open a door at companies like NVIDiA, Meta, Google or AMD. So don't forget to blog about it if you do it, and maybe add benchmarks / power usage estimates.

解析： 
1. 核心任务：到底要你做什么？
这个项目的目标是：在 NanoGPT-TK 这个开源项目中，用 ThunderKittens 框架实现一个《Addition is all you need》论文中提到的核心算子。

论文内容（L-Mul）： 论文提出了一种叫 L-Mul（Linear-Complexity Multiplication） 的算法。核心思想是：在深度学习中，不再使用昂贵的“浮点乘法”，而是通过“加法和位移”来近似乘法。这样可以大幅降低功耗，且性能几乎不变。

工具（ThunderKittens）： 这是斯坦福大学 HazyResearch 实验室开发的一个 C++ 模板库。它让你能用类似 Triton 的高级逻辑去写 CUDA。它封装了极其复杂的硬件底层（如 Tensor Cores 的使用、共享内存搬运），让你专注于“切片（Tiling）”逻辑。

项目（NanoGPT-TK）： 这是著名的 NanoGPT（由 AI 大神 Andrej Karpathy 创建）的“高性能版”，使用了 ThunderKittens 进行底层加速。

