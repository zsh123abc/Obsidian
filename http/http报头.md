
## 通用报头
通用头域包含请求和响应消息都支持的头域，通用头域包含Cache-Control、Connection、Date、Pragma、Transfer-Encoding、Upgrade、Via。对通用头域的扩展要求通讯双方都支持此扩展，如果存在不支持的通用头域，一般将会作为实体头域处理。
既可以出现在请求报头，也可以出现在响应报头中
```
Date：表示消息产生的日期和时间

Connection：允许发送指定连接的选项，例如指定连接是连续的，或者指定“close”选项，通知服务器，在响应完成后，关闭连接

Cache-Control：用于指定缓存指令，缓存指令是单向的（响应中出现的缓存指令在请求中未必会出现），且是独立的（一个消息的缓存指令不会影响另一个消息处理的缓存机制）

Pragma: 用来包含实现特定的指令，最常用的是Pragma:no-cache。在HTTP/1.1协议中，它的含义和Cache-Control:no-cache相同。
```


## 请求报头
请求报头通知服务器关于客户端求求的信息。
请求方的HTTP报头结构：通用报头|请求报头|实体报头
```
Host：请求的主机名，允许多个域名同处一个IP地址，即虚拟主机

User-Agent：发送请求的浏览器类型、操作系统等信息

Accept：客户端可识别的内容类型列表，用于指定客户端接收那些类型的信息

Accept-Encoding：客户端可识别的数据编码

Accept-Language：表示浏览器所支持的语言类型

Connection：允许客户端和服务器指定与请求/响应连接有关的选项，例如这是为Keep-Alive则表示保持连接。

Transfer-Encoding：告知接收端为了保证报文的可靠传输，对报文采用了什么编码方式。
```

## 响应报头
```
用于服务器传递自身信息的响应。

响应方的HTTP报头结构：通用报头|响应报头|实体报头

常见的响应报头：

Location：用于重定向接受者到一个新的位置，常用在更换域名的时候

Server：包含可服务器用来处理请求的系统信息，与User-Agent请求报头是相对应的
```

## 实体报头
实体报头HTTP header用来描述消息体内容。实体报头既可用于请求也可用于响应中。如Content-Length，Content-Language，Content-Encoding之类的报头都是实体报头。
尽管实体报头既非请求或响应报头，（由于它经常出现在请求头或响应头中）它们通常包含于此类概念中。
在下面例子中，Content-Length是一个实体报头，而Host和User-Agent是request headers（请求报头）:
```
POST /myform.html HTTP/1.1
Host: developer.mozilla.org
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.9; rv:50.0) Gecko/20100101 Firefox/50.0
Content-Length: 128
```