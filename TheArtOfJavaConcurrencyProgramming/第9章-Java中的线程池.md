# 第9章-Java中的线程池


合理使用线程池的好处：

1. 降低资源消耗。通过重复利用已创建的线程降低『线程创建和销毁』造成的开销。
2. 提高响应速度。当任务到达时，任务可以不需要等到线程创建就能立即执行。
3. 提高线程的可管理性。统一分配、调优和监控（无限制创建会消耗系统资源，降低系统稳定性）


#### 线程池的实现原理

当提交一个任务后，线程池的主要处理流程。  

```flow
st=>start: Start:>http://www.google.com[blank]
e=>end:>http://www.google.com
op1=>operation: 提交任务
op2=>operation: 创建线程执行任务
op3=>operation: 将任务存储在队列里
op4=>operation: 按照策略处理无法执行的任务
cond=>condition: 核心线程池是否已满?:>http://www.google.com
cond2=>condition: 队列是否已经满了?:>http://www.google.com
cond3=>condition: 线程池是否已经满了?:>http://www.google.com

st->op1->cond
cond(yes)->cond2
cond(no)->op2
cond2(yes)->cond3
cond2(no)->op3->e
cond3(yes)->op4->e
cond3(no)->op2->e
```


#### 关闭线程池

shutdown   shutdownNow

原理都是遍历线程，逐个调用线程的 interrupt 来中断线程。

shutdownNow 首先将线程池的状态设置成 STOP，然后尝试**停止所有正在执行或暂停的任务**，并返回等待执行任务的列表。

shutdown 只是将线程池的状态置为 SHUTDOWN 状态，然后**中断所有『没有正在执行』任务的线程**。

调用上面两个方法后 isShutdown 会返回 true，但是 isTerminaed 在所有任务都关闭后才会返回 true。



