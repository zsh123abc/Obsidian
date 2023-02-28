HTTP 协议详解
https://blog.csdn.net/weixin_51367845/article/details/123313047

http协议的工作流程
https://blog.csdn.net/qq_35455503/article/details/55813299

HTTP 数据类型与编码
https://blog.csdn.net/fd2025/article/details/124646894
https://blog.csdn.net/Tyro_java/article/details/123101069?ops_request_misc=&request_id=&biz_id=102&utm_term=http%E5%A6%82%E4%BD%95%E5%8D%8F%E5%95%86%E7%BC%96%E7%A0%81%E6%A0%BC%E5%BC%8F&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduweb~default-0-123101069.142^v70^js_top,201^v4^add_ask&spm=1018.2226.3001.4187

关于HTTP中的数据协商

请求和响应报文 格式 一样，格式：首行，协议头(请求头/响应头)，空行，正文
        首行：方法(GET/POST)，URL(http://127.0.0.1:8100/)，http版本号(HTTP/1.1)
        协议头：多个键值对结构(Connection:keep-alive长链接)
        空行：协议头和正文的分割线，表示协议头结束，协议头里的键值对有多个，没有空行，tcp      传输数据时可能会出现粘包问题，可能应该在正文里的出现在协议头里，客户端解析出错
        正文：请求正文(post才会有),响应正文:相应的是html，内容就会在正文中



`GET http://localhost:8080/favicon.ico 404 报错解决`
https://blog.csdn.net/Cinyyyy/article/details/123683572
bitbug_favicon.ico网页图标，放在项目根目录下
```html
<link rel="shortcut icon" href="bitbug_favicon.ico" type="image/x-icon">
```

http请求
浏览器通过域名访问
查看dns域名缓存，查看本地有无配置

HTTP和TCP之间的关系
https://blog.csdn.net/weixin_40784198/article/details/81434530/
TCP在传递数据时依赖于实现定义好的几个标记（Flags）去向另一方表态传达数据和连接的状态：

* F : FIN - 结束; 结束会话
* S : SYN - 同步; 表示开始会话请求
* R : RST - 复位;中断一个连接
* P : PUSH - 推送; 数据包立即发送
* A : ACK - 应答
* U : URG - 紧急
* E : ECE - 显式拥塞提醒回应
* W : CWR - 拥塞窗口减少

tcp三次握手：
客户端发送 随机生成的序列号seq，窗口大小win，其余信息
服务端收到后发送 随机生成的序列号seq，确认ack（客户端发送的seq+1），服务端已经收到请求
客户端收到服务端发送的报文，客户端响应ack（服务器端发送的seq+1），表示服务端已经收到客户端发送的请求

tcp四次挥手：
客户端发送报文FIN，服务端收到之后知道了客户端想断开连接，此时服务端可能还有未发送完的消息，所有服务端只会一个确认消息，用来告诉客户端已经收到断开连接消息，等所有消息发送完后，再给客户端发送FIN断开连接报文，发送完后进入断开连接状态，客户端收到后，发送一个确认报文给服务端，服务端收到后断开连接，客户端进入超时等待状态，防止服务端没有收到确认报文




报文中请求报文编码格式为ASCII，具体类容格式
```
GET  /index.htm  HTTP/1.1
```



GET /api/filetransfer/uploadfile?chunkNumber=1&chunkSize=1048576&currentChunkSize=1034&totalSize=1034&identifier=3fe29d57338142c5f888414955568229&filename=1326501901.mp4_test_0630.xml&relativePath=1326501901.mp4_test_0630.xml&totalChunks=1&filePath=%2Fzsh%2Flabel_data%2Fimages%2F&isDir=0 HTTP/1.1
Host: 192.168.100.98:1080
User-Agent: python-requests/2.28.1
Accept-Encoding: gzip, deflate
Accept: */*
Connection: keep-alive
