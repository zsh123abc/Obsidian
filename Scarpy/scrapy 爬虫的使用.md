整个工作流程,

	爬虫中起始的url构造成request对象, 并传递给调度器.
	
	引擎从调度器中获取到request对象. 然后交给下载器
	
	由下载器来获取到页面源代码, 并封装成response对象. 并回馈给引擎
	
	引擎将获取到的response对象传递给spider, 由spider对数据进行解析(parse). 并回馈给引擎
	
	引擎将数据传递给pipeline进行数据持久化保存或进一步的数据处理.
	
	在此期间如果spider中提取到的并不是数据. 而是子页面url. 可以进一步提交给调度器, 进而重复步骤2的过程
	
	上述过程中一直在重复着几个东西,

引擎(engine)

	scrapy的核心, 所有模块的衔接, 数据流程梳理.

调度器(scheduler)

	本质上这东西可以看成是一个队列. 里面存放着一堆我们即将要发送的请求. 可以看成是一个url的容器. 它决定了下一步要去爬取哪一个url. 通常我们在这里可以对url进行去重操作.

下载器(downloader)

	它的本质就是用来发动请求的一个模块. 小白们完全可以把它理解成是一个requests.get()的功能. 只不过这货返回的是一个response对象.

爬虫(spider)

	这是我们要写的第一个部分的内容, 负责解析下载器返回的response对象.从中提取到我们需要的数据.

管道(pipeline)

	主要负责数据的存储和各种持久化操作.

extract()/extract_first()方法本身都是用去提取节点的内容的

extract()解析：
https://blog.csdn.net/chendongpu/article/details/124662470?utm_medium=distribute.pc_relevant.none-task-blog-2~default~baidujs_baidulandingword~default-1-124662470-blog-107787199.pc_relevant_multi_platform_whitelistv3&spm=1001.2101.3001.4242.2&utm_relevant_index=4

爬虫数据保存到文本中:
file = open('a.txt', 'w');  
file.write(str(title));
file.close()
file = open('a.txt', 'a');  
file.write(str(result2));  
file.close();

查看项目下有几个爬虫：
scrapy list


scrapy.cfg ：项目的配置文件

mySpider/ ：项目的Python模块，将会从这里引用代码

mySpider/items.py ：项目的目标文件

mySpider/pipelines.py ：项目的管道文件

mySpider/settings.py ：项目的设置文件

mySpider/spiders/ ：存储爬虫代码目录

爬虫运行参数 :
![[爬虫运行参数.png]]




