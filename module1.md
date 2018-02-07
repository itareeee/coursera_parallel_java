# 1.3 Computation Graphs

```
       |--(Fork)----> S2 [10] -------(Join)---+
       |                                 |
S1 [1] ----+--(Continue)--> S3 [10] --(Continue)--+--> S4 [1]
```

- work
  - sum of execution time of all nodes
  - 22
- span
  - length of longest path
  - 12
- ideal parallelism = work / span
  - 22/12 ≒ 2
  - The ideal parallelism is an upper limit on the speedup factor that 
    can be obtained from parallel execution of nodes in computation graph.
  - 要は ideal parallelism の数以上にプロセッサ増やしてもスピード上がらないということ?

# 1.4 Multiprocessor Scheduling, Parallel Speedup

- T(p): Execution time of a computation graph given p processors (e.g. 2, 4, 8, 16 ...)

- T(∞) <= T(p) <= T(1)
  - T(∞) = span
  - T(1) = work
  - 当たり前やん

- Speedup(p) = T(1) / T(p)
- Speedup(p) <= the number of processors
- Speedup(p) <= ideal parallelism = work/span
  - 要はCPUコアの数を二倍にしたらSpeedは二倍以上にはならないよ、ということ
