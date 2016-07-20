# 适配器模式(Adapter)


适配器模式：**将一个类的接口，转换成客户期望的另一个接口。适配器让原本接口不兼容的类可以合作无间。**  
![形象图](http://ww3.sinaimg.cn/large/98900c07jw1f60ibhzrx4j20aj057t8u.jpg)


当想使用一个已经存在的类，但是不匹配需求接口的时候，可以考虑使用适配器模式来适配，如果有需要还可以做 **双向适配**，来完成适配。  

![UML](http://ww1.sinaimg.cn/large/98900c07jw1f60jn82l4uj20u20m8q5l.jpg)


适配器实现Client所需的目标的接口，并包裹一个被适配者的对象，在目标接口的方法调用适配者的方法，来达到适配的目标。  

个人觉得使用适配器最大的好处是 **不需要修改客户端以及被适配者的代码。**  


## See also

[Adapter pattern](https://en.wikipedia.org/wiki/Adapter_pattern)  
[Adapter Design Pattern Example](http://javadesign-patterns.blogspot.com/p/adapter-pattern-example.html)  
