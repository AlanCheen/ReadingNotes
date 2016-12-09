# 第2章-简单的HTTP协议

对 HTTP 协议结构进行讲解。

<img src="http://ww3.sinaimg.cn/large/98900c07gw1fakkd19aglj21ey0tk0zk.jpg"/>


## 客户端和服务端的通信


请求报文：

<img src="http://ww1.sinaimg.cn/large/98900c07gw1fakk72xrlhj20b406djrm.jpg"/>


响应报文： 

<img src="http://ww1.sinaimg.cn/large/98900c07gw1fakk6k8n60j209d064aa9.jpg"/>


## HTTP 是不保存状态的协议

无状态 ，不保存之前发送过的请求或响应的功能。

可以减少服务器的 CPU以及内存消耗。



## 告知服务器意图的 HTTP方法

|   方法名   |     作用      |
| :-----: | :---------: |
|   GET   |    获取资源     |
|  POST   |   传输实体主体    |
|   PUT   |    传输文件     |
|  HEAD   |   获得报文首部    |
| DELETE  |    删除文件     |
| OPTIONS |   询问支持的方法   |
|  TRACE  |    追踪路径     |
| CONNECT | 要求用隧道协议连接代理 |



## 持久连接节省通信

由于 HTTP 最开始每次通信都需要重新链接/断开TCP，效率低，通信开销大，速度低。

##### 持久连接 keep-alive

减少 了 TCP 连接断开的开销，减轻服务器负载，提升速度。

##### 管线化 pipelining

以前发送请求后需要等待并收到响应，才能发送下一个请求。

管线化技术可以使得不需等待就能发送下一个请求，这样就能做到**并发发送多个请求**了。

​	管线化比持久连接还要快！


## 使用 Cookie 的状态管理

HTTP 本身是无状态的，但是遇到一些功能，比如登录，那么保存登录状态就不需要每次都重新登录就显得格外重要。

所以引入了 Cookie 技术。

服务端发送响应，带`Set-Cookie`的首部字段信息，客户端再次发送请求的时候在首部字段`Cookie`写入，传递给服务端。