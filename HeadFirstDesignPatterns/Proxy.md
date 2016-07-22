# 代理模式



![类图](http://ww1.sinaimg.cn/large/98900c07jw1f62sqklu5rj20m80cegm9.jpg)

代理要做的就是：控制和管理访问(控制对象访问)  

所谓代理（proxy），就是代表某个真实的对象。  


远程代理（remote proxy），好比『远程对象的本地代表』;远程代理是 **一种对象，活在不同的Java虚拟机(JVM)堆中**（更一般的说法为，在不同 **地址空间运行的远程对象**）  

本地代表，是一种可以由本地方法调用的对象，其行为会转发到远程对象中。  


![](http://ww3.sinaimg.cn/large/98900c07jw1f62uet9p85j20gt07l3zc.jpg)

书中提到了 `RMI` 技术，它将 客户辅助对象称为`stub`（桩）,服务器辅助对象称为`skeleton`（g骨架）。

BONUS：原语类型（primitive）

例子让我想起来Android中的 `AIDL`和`Binder`，忽然间懂了好多。  
