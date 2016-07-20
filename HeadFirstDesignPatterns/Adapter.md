# 适配器模式(Adapter)


适配器模式：**将一个类的接口，转换成客户期望的另一个接口。适配器让原本接口不兼容的类可以合作无间。**  

适配器非常形象的图：  

![形象图](http://ww3.sinaimg.cn/large/98900c07jw1f60ibhzrx4j20aj057t8u.jpg)


非常形象的模式，就像生活中的手机充电器，电脑的电源适配器一样。

## 使用场景

当想使用一个已经存在的类，但是不匹配需求接口的时候，可以考虑使用适配器模式来适配，如果有需要还可以做 **双向适配**，来完成适配。  

![类图](http://ww4.sinaimg.cn/large/98900c07jw1f60l15wrt4j20u20m8416.jpg)

适配器实现Client所需的目标的接口，并包裹一个被适配者的对象，收到方法调用的时候，委托给被适配者，来达到适配的目标。  


## 小结

优势：  

1. 使用对象组合的方式，用修改的接口来包装适配者
2. 被适配者的任何子类也可以搭配适配器使用  
3. 个人觉得使用适配器最大的好处是 **不需要修改客户端以及被适配者的代码。**  

缺点：  

1. 需要实现所有的方法去完成适配，如果目标非常大，那么工作量也比较大。  

NOTE：之前提到的都是 **对象适配器**，另外还有一种叫做 **类适配器**，不过类适配器需要多重继承去实现(Adapter需要继承Target和Adaptee)，而不是组合的方式去实现。  


## See also

[Adapter pattern](https://en.wikipedia.org/wiki/Adapter_pattern)  
[Adapter Design Pattern Example](http://javadesign-patterns.blogspot.com/p/adapter-pattern-example.html)  
