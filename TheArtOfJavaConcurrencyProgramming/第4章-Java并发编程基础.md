# 第4章-Java并发编程基础

线程：现代操作系统调度的最小单元；也叫轻量级进程（Light Weight Process）


#### 线程的状态

| 状态 | 说明 |
| :-: | :-: |
| NEW |  初始状态，被创建，但是还没有调用 start |
| RUNNABLE |  运行状态，就绪和运行 |
|  BLOCKED |  阻塞状态，表示线程阻塞于锁 |
|  WAITING |  等待状态，表示线程进入等待状态，进入该状态表示当前线程需要等待其他线程做出一些特定动作（通知或中断） |
|  TIME_WAITING |  超时等待状态，不同于 WAITING，它是可以在指定的时间自行返回 |
|  TERMINATED |  终止状态，表示当前线程已经执行完毕 |


#### 等待/通知机制


| 方法名称 | 描述 |
| :-: | :-: |
|  notify() | 通知一个在对象上等待的线程，使其从 wait()方法返回，而返回的前提是线程获取到了对象的锁 |
|  notifyAll() | 通知所有等待在该对象上的线程 |
| wait() | 调用该方法的线程进入 WAITING 状态，只有等待另外线程的通知或被中断才会返回，需要注意，调用 wait()方法后，会释放对象的锁。 |
| wait(long) |  超时等待一段时间，这里的参数时间是毫秒，也就是等待长达 n 毫秒，如果没有通知就超时返回 |
|  wait(long,int) | 对于超时时间更细粒度的控制，可以达到纳秒 |

废弃的方法是因为暂停了也还持有锁，容易出问题，比如死锁。

要点细节：

1.  调用对象的 wait notify notifyAll 都需要先获得对象的锁
2.  wait 方法后，线程状态由 RUNNING 变为 WAITING，并将当前线程放置到对象的等待队列(WaitQueue)
3.  notify notifyAll 方法调用后，**等待线程依旧不会从 wait 返回，需要调用 notify 或 notifyAll 的线程释放锁之后**，等待线程**才有机会**从 wait 返回。
4. notify 方法将等待队列中的一个线程移到同步队列(SynchronizedQueue)，而 notifyAll 移动的是所有线程，被移动的线程状态由 WAITING 变为 BLOCKED。
5. wait 方法返回的前提是『获得了调用对象的锁』。(光被 notify 是没有用的)
6. wait 方法会释放锁


#### Thread.join()

如果一个线程 A 调用了线程 B.join()，它的意思是：线程 A 等待线程 B 终止之后才从 join()返回。  

join(long) join(long,int) 则提供了超时机制，在指定的时间内没有终止的话，将会返回。

```Java
public final synchronized void join() throws InterruptedException{
	//条件不满足
	while(isAlive()){
		wait(0);
	}
	//条件符合，方法返回
}
```

当线程终止时，会调用线程自身的 notifyAll 方法，会通知所有等待在该线程对象上的线程。



#### ThreadLocal



