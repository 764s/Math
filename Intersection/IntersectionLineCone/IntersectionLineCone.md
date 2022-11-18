[Intersection of a Line and Cone] 
==




## 1. Introduction  

<details>
<summary>Introduction</summary>

> This document describes an algorithm for computing the set of intersection between a cone and a line, ray or segment.  
The algorithm is theoretically correct when using real-valued arithmetic.  
When computing using float-point arithmetic, rounding errors can cause misclassifications of signs of important expressions,  
leading to failure of the implementation to produce correct results.

告诉怎么计算 line, ray, segment 和 cone 的交点  
算法本身是精确的, 但是用程序实现时会有浮点误差

> With the exception of approximation error in computing the cosine of a user-specified cone angle,  
it is possible to obtain the theoretically correct result by using arbitrary precision arithmetic in conjunction with symbolic arithmetic that handles the square root operations to avoid the rounding errors inherent in computing those roots.

除了 cosine 带来的近似误差, 可以通过 symbolic arithmetic 来避免 square root operations 引起的误差.

> An implementation of the algorithm is also described in this document.  
The set of intersection is either empty, a point, a segment, a ray or a line.

交集可是 空, 点, 线段, 射线, 直线

When a point, segment or ray, the output of line-cone intersection is stored using rational numbers and a symbolic representation of a square root.  
The output can then be converted to floating-point using as many bits of precision as desired.

如果结果是点, 线段 或者 射线, 结果用 rational numbers 和 symbolic representation of a square root 表示

</details>


### 1.1 Definition of Cones  

<details>
<summary>Definition of Cones</summary>

> A infinite single-sided solid cone has a vertex __V__, an axis ray whose origin is __V__ and unit-length direction is __D__,  
and an acute cone angle θ ∈ (0, π/2).  
A point __X__ is inside the cone when the angle between __D__ and __X__ - __V__ is in [0, θ].  
Algebraically, the containment is defined by  
> __D__ · ( __X__ - __V__ ) / | __X__ - __V__ | ≥ cos(θ)  
> when __X__ ≠ __V__  
>
> Equivalently, the containment is defined by  
__D__ · ( __X__ - __V__ ) ≥ | __X__ - __V__ | cos(θ)  
which includes the case __X__ == __V__.  
>
> Finally, we can avoid computing square roots in the implementation by squaring the dot-product equation to obtain a quadratic equation and requiring that only points above the supporting plane of the single-sided cone be considered.  
The definition is  
// > Q(X) = (D · (X - V))<sup>2</sup> - γ<sup>2</sup> | X - V |<sup>2</sup>  

为了避免计算 |X - V| 的 square roots, 并且同时保证不等式成立, 同时对两边平方处理  

</details>

[Intersection of a Line and Cone]:https://www.geometrictools.com/Documentation/IntersectionLineCone.pdf  