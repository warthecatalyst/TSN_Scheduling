#TSN Scheduling Algorithms
##Basic Designs and thoughts
incremental backtracking approach(回溯法)
一次仅仅加入一个部分然后把他们加入SMT Solver的上下文约束之中；
如果成功了，则继续添加，直到所有的Context都添加进去，否则，失败回溯到上一步，然后增大这个加入的部分（并不是特别了解）
(the size of the increment is increased)
对于(4)的一点想法：
贪心算法求解or化为Bin-Packing Problem然后2近似算法（可能有问题）

## Algorithm pseudo code
```
public SMT_Solution incremental_approach(double alpha, Constraints constraints){
    if(alpha>1.0) return null
    S = SMT_Solver.solve(constraints*alpha)
    if(S!=null){
        return incremental_appoach(alpha,constraints*alpha)
    }
    alpha += eps
    return incremental_approach(alpha,constraints)
}
