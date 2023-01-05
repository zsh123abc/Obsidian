HTTP 协议详解
https://blog.csdn.net/weixin_51367845/article/details/123313047

http协议的工作流程
https://blog.csdn.net/qq_35455503/article/details/55813299

请求和响应报文 格式 一样，格式：首行，协议头(请求头/响应头)，空行，正文
        首行：方法(GET/POST)，URL(http://127.0.0.1:8100/)，http版本号(HTTP/1.1)
        协议头：多个键值对结构(Connection:keep-alive长链接)
        空行：协议头和正文的分割线，表示协议头结束，协议头里的键值对有多个，没有空行，tcp      传输数据时可能会出现粘包问题，可能应该在正文里的出现在协议头里，客户端解析出错
        正文：请求正文(post才会有),响应正文:相应的是html，内容就会在正文中




GET http://localhost:8080/favicon.ico 404 报错解决
https://blog.csdn.net/Cinyyyy/article/details/123683572
bitbug_favicon.ico网页图标，放在项目根目录下
```html
<link rel="shortcut icon" href="bitbug_favicon.ico" type="image/x-icon">
```


