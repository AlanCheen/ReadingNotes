# 观察者模式

观察者模式：  
**定义了对象之间的一对多依赖，这样依赖，当一个对象改变状态时，它的所有依赖者都会受到通知，并自动更新。**  

出版者（Subject） + 订阅者（Observer） = 观察者模式  

观察者依赖于主题。  

![UML](http://ww4.sinaimg.cn/large/98900c07gw1f5uino6cvoj20rs0bh0ub.jpg)  

**观察者模式提供了一种对象设计，让主题和观察者之间松耦合。**  

比如 EventBus 就是观察者模式。  

注意： **观察者模式会造成内存泄漏，一定要记得取消订阅**  

## See Also
[Observer pattern](https://en.wikipedia.org/wiki/Observer_pattern)  
[Observer Design Pattern Example](http://javadesign-patterns.blogspot.com/p/page22.html)  
