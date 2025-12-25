
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

