socket（套接字），在任何类型的通信开始之前，网络应用程序都必须创建套接字。

socket以及setsockopt函数
https://blog.csdn.net/rlenew/article/details/107592753

socket.socket()函数 套接字详解及TCP、UDP程序示例
https://blog.csdn.net/Dontla/article/details/103679153

python socket函数详解
https://blog.csdn.net/weixin_39724362/article/details/111762534


1，创建套接字，初始化socket，参数指定协议族，套接口类型等
2，绑定主机ip，port
3，监听套接字，默认最大连接数为128
4，等待客户端连接，一直阻塞到客户端连接，当客户端访问绑定的(ip:port)时建立连接
5，连接后接受客户端请求头信息，收到的信息以utf-8格式解码，发送消息时也需要以utf-8格式编码
6，re匹配从请求头中取出请求路径（‘/index.html’）,拼接上主机路径打开本地文件，读取文件内容数据，读取数据后关闭文件
7，返回（utf-8）格式编码后的信息给客户端，文件存在返回200 OK，并且返回文件数据，文件不存在返回404 NOT FOUND
8，关闭套接字，服务端回到阻塞状态，等待客户端连接


GET http://localhost:8080/favicon.ico 404 报错解决
https://blog.csdn.net/Cinyyyy/article/details/123683572
bitbug_favicon.ico网页图标，放在项目根目录下
```html
<link rel="shortcut icon" href="bitbug_favicon.ico" type="image/x-icon">
```


hosts文件路径：
``C:\Windows\System32\drivers\etc\hosts``


多进程：操作系统中同时运行的多个程序
多线程：在同一个进程中同时运行的多个任务
协程：可以运行的函数，一个线程上可以运行多个协程

简单理解socket（AF_INET&SOCK_STREAM,SOCK_DGRAM）
https://blog.csdn.net/u010624263/article/details/84194470

进程和线程的详解和区别
https://blog.csdn.net/Zhouzi_heng/article/details/124747195

HTTP 协议详解
https://blog.csdn.net/weixin_51367845/article/details/123313047