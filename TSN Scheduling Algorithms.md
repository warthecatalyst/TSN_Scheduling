#TSN Scheduling Algorithms
##Basic Algorithms
incremental backtracking approach(回溯法)
一次仅仅加入一个部分然后把他们加入SMT Solver的上下文约束之中；
如果成功了，则继续添加，直到所有的Context都添加进去，否则，失败回溯到上一步，然后增大这个加入的部分（并不是特别了解）
(the size of the increment is increased)
对于(4)的一点想法：
贪心算法求解or化为Bin-Packing Problem然后2近似算法（可能有问题）