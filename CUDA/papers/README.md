# Addition is all you need 笔记 

文章介绍了在transformer架构中计算fp8和fp16浮点数时的计算机算子计算过程，展示计算算术公式，对公式的部分进行替换，以达到将浮点数相乘完全转换为加法操作。

该操作看可以带来，在一次浮点数计算过程中： 1.减少半加法器个数 2. 减少全加法器个数 3.总体大幅降低算子使用数量 

“sign prediction, exponent addition with offset, a j + 1-bit mantissa multiplication, and
exponent rounding. The mantissa multiplication includes (j + 1)2 AND operations, 3 half adders
and 2j − 2 full adders. The exponent rounding needs i half adders. In a regular circuit design, a
full adder involves 2 AND, 2 XOR, and 1 OR. Each XOR has 4 NAND gates. As a result, a full adder
consumes 11 gate-level computation, while a half adder (no incoming carry) consumes 5 gate-level
computations (1 AND and 1 XOR)” 

文章对公式的替换部分的算法提出了展示。 

文章对不同的尾数长度，不同的指数长度，在不同模型间，都进行了实验，并找出不同长度下的性能。 

最终结果表示： 对于LLM， 在五种不同的benchmark中，均展示相比于传统mul方法，有更强的准确性。 

“We then showed that the expected accuracy of
L-Mul surpasses that of fp8 multiplications while requiring significantly less computational power.”
