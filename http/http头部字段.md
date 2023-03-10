HTTP数据类型与编码：
https://blog.csdn.net/fd2025/article/details/124646894

Accept （可以处理的内容类型）

**`Accept`** 请求头用来告知（服务器）客户端可以处理的内容类型，这种内容类型用[MIME 类型](https://developer.mozilla.org/zh-CN/docs/Web/HTTP/Basics_of_HTTP/MIME_types)来表示。借助[内容协商机制](https://developer.mozilla.org/zh-CN/docs/Web/HTTP/Content_negotiation), 服务器可以从诸多备选项中选择一项进行应用，并使用 [`Content-Type`](https://developer.mozilla.org/zh-CN/docs/Web/HTTP/Headers/Content-Type) 应答头通知客户端它的选择。浏览器会基于请求的上下文来为这个请求头设置合适的值，比如获取一个 CSS 层叠样式表时值与获取图片、视频或脚本文件时的值是不同的。`*/*`，`text/html`........


Accept-Encoding （接收编码）

HTTP 请求头 **Accept-Encoding** 会将客户端能够理解的内容编码方式——通常是某种压缩算法——进行通知（给服务端）。通过内容协商的方式，服务端会选择一个客户端提议的方式，使用并在响应头 [`Content-Encoding`](https://developer.mozilla.org/zh-CN/docs/Web/HTTP/Headers/Content-Encoding) 中通知客户端该选择。gzip,deflate.......


Content-Encoding （内容编码）

表示的是数据的表示或“编码形式”，原始文件媒体/类容类型是通过Content-Type首部给出
[实体消息首部](https://developer.mozilla.org/zh-CN/docs/Glossary/Representation_header) **`Content-Encoding`** 列出了对当前实体消息（消息荷载）应用的任何编码类型，以及编码的顺序。它让接收者知道需要以何种顺序解码该实体消息才能获得原始荷载格式。Content-Encoding 主要用于在不丢失原媒体类型内容的情况下压缩消息数据。gzip,deflate.......
一般建议服务器应对数据尽可能地进行压缩，并在适当情况下对内容进行编码。对一种压缩过的媒体类型如 zip 或 jpeg 进行额外的压缩并不合适，因为这反而有可能会使荷载增大。

Content-Length （数据内容长度）
**`Content-Length`** 是一个实体消息首部，用来指明发送给接收方的消息主体的大小，即用十进制数字表示的八位元组的数目。


Transfer-Encoding（传输编码）

**`Transfer-Encoding`** 消息首部指明了将 [entity](https://developer.mozilla.org/zh-CN/docs/Glossary/Entity_header) 安全传递给用户所采用的编码形式。
`Transfer-Encoding` 是一个[逐跳传输消息首部](https://developer.mozilla.org/zh-CN/docs/Web/HTTP/Headers#hbh)，即仅应用于两个节点之间的消息传递，而不是所请求的资源本身。一个多节点连接中的每一段都可以应用不同的`Transfer-Encoding` 值。如果你想要将压缩后的数据应用于整个连接，那么请使用端到端传输消息首部 [`Content-Encoding`](https://developer.mozilla.org/zh-CN/docs/Web/HTTP/Headers/Content-Encoding) 。
当这个消息首部出现在 [`HEAD`](https://developer.mozilla.org/zh-CN/docs/Web/HTTP/Methods/HEAD) 请求的响应中，而这样的响应没有消息体，那么它其实指的是应用在相应的 [`GET`](https://developer.mozilla.org/zh-CN/docs/Web/HTTP/Methods/GET) 请求的应答的值。
Transfer-Encoding: chunked：数据以分块的形式发送，这种情况，Content-Lenght在分块传输时才会发送



http请求编码格式为ASCII
MIME type :传输body的类型text/xml，Encoding type :body内容的压缩类型gzip
客户端和服务器进行内容协商，客户端用Accept头告诉服务器可以理解的数据类型，服务器用Content头告诉客户端实际发送数据的类型
Content-Type: