# 第3章-DOM


## 文档：DOM 中的 D
D 文档 document ，当创建了一个网页并把它加载到 Web 浏览器中时，DOM 就在幕后生成，它把你编写的网页文档转换为一个文档对象。（加载到内存？）

## 对象：DOM 中的 O

- 用户定义对象
- 内建对象
- 宿主对象

最基础的宿主对象： window对象，对应浏览器窗口本身。（类似 Android 的 PhoneWindow？）

window 对象的属性和方法通常称为 BOM（浏览器对象模型）。

BOM 提供了如 window.open window.blur 等方法。

更重要的是 document 对象。


## 模型：DOM 中的 M

模型：某种事物的表现形式。 比如模型火车就代表一列真正的火车。

DOM 把一份文档表示为一棵树（数学意义上的树，类似二叉树）

家谱书模型 非常适合用来表示一份用(X)HTML 语言编写出来的文档。（parent child sibling）

节点树。

## 节点node

文档是由节点构成的集合。节点的类型：元素节点、文本节点和属性节点。

#### 元素节点（element node）

元素节点，DOM 的原子是元素节点。













