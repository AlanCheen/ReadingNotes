# 第15章-Android性能优化

Android性能优化主要包括布局优化、绘制优化、内存泄露优化、响应速度优化、ListView优化、Bitmap优化、线程优化以及一些优化建议


## 布局优化

1. 减少布局文件的层级(测量/布局/绘制的时间减少):可以使用RelativeLayout来减少嵌套,从而达到减少层级的目的,另外在**相同层级**的情况下使用LinearLayout(相比于RelativeLayout更高效)  
2. 使用`include`标签复用,`merge`标签降低层级,`ViewStub`来实现懒加载,另外补充一个`Space`可以用来占位

## 绘制优化(onDraw)
