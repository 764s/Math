KDTree
==

> a k-dimensional tree is a space-partitioning data structure for organizing points in a k-dimensional space.  
> k-d trees are a useful data structure for several applications, 
> such as searches involving a multidimensional search key (e.g rage searches and nearest neighbor searches) 
> and creating point clouds. 
> k-d trees are a special case of binary space partitioning trees.  

多维树是一个空间分区数据结构, 用来处理多维空间中的点.  
适用于 a multidimensional search key (overlap) 和 创建 point clouds.  
kd trees 是 binary space partitioning trees 的特殊情况.  

### Description

> The k-d tree is a binary tree in which every node is a k-dimensional point.  

k-d tree 是一个 binary, 他的所有 node 都是一个 k维点.  

> Every non-leaf node can be thought of as implicitly generating a splitting hyperplane that 
> divides the space into two parts,  known as half-space.  

每个非终节都可以看作产生了一个 hyperplane, 他把整个空间分成了两个部分.  
_?? 整个空间指什么, 父节点代表的空间吗_  
_?? 空间是指分割过的有限空间吗. 空间是无限的概念, 对同一个空间无论如何分割应该都不边才对_  

> Points to the left of this hyperplane are represented by the left subtree of that node 
> and points to the right of the hyperplane are represented by the right subtree.  

hyperplane 左边的点由 node 的 left subtree 表示, 右边的点由 right subtree 表示.  
_?? hyperplane 的左是什么, subtree 的左是什么, 这两个概念一样吗, 这个重要吗_  

> The hyperplane direction is chosen in the following way:  
> every node in the tree is associated with one of the k dimensions, 
> with the hyperplane perpendicular to that dimension's axis.  

_? 每个node 都对应k dimensions 中的一个, 对应的hyperplane垂直于这个dimension轴_  
_?? point 是什么, 谁的, node 空间的_  

> So, for example, if for a particular split the "x" axis is chosen, 
> all points in the subtree with a smaller "x" value than the node then the node will appear 
> in the left subtree and all points with a larger "x" value will be in the right subtree. 
> In such a case, the hyperplane would be set by the x value of the point, and its normal 
> would be the unit x-axis.  

如果选定的split是 "x" axis, 所有"x" value 比node更小的, 出现在 left subtree 中, 所有 "x" value 更大的出现在
right subtree 中.  

_?? 和node比, node一定也有一个点吗_  
_? node 好像有一个点, 这个点和选定的轴共同决定了这个hyperplane_  





[k-d tree](https://en.wikipedia.org/wiki/K-d_tree)  