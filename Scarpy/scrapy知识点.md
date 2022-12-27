一，创建爬虫文件
		#创建爬虫目录：
		 scrapy startproject xxx
		#生成爬虫：要在爬虫目录下
		 scrapy genspider spider(爬虫名) "爬虫名.cn"

二，配置管道文件（pipelines.py），配置设置文件（setting.py），
		在items中加入要提取的数据名（title = scrapy.Field()）
		1，scrapy.Field（）：设置Field对象使得title可以接受任何数据
		2，spider.py中要使用iteam存储数据就必须导包
		（from ..items import ScrapyJsonItem）， ..items：..从上目录导包
		3，ITEM_PIPELINES = {
				   'scrapy_json.pipelines.ScrapyJsonPipeline': 300,
			}：
			如果有多个爬虫，这里可以设置爬虫的优先级，数字越小优先级越高
三，start_urls 存放要爬取网页的链接

四，在parse函数中进行提取数据保存在item中并且返回给管道文件做处理
	1，爬取多页数据：yield scrapy.Request(下一个要爬取的网址，回调哪个方法)
	2，

五，pipelines.py处理数据：
		1，提取html文件：response.xpath()
		      解析完存入item中
		2，提取json文件： json.loads(response.text)
			  取出所有数据，在根据对应的名字取出数据			  
	    3，根据存进去的名字把对应数据从iteam中拿出来：
				title = item["title"]，
		随后做相应的处理：
			1，储存文本文件中：
					储存json格式改文件后缀名即可：
						file = open('a.txt', 'w');  
						file.write(str(title));
						file.close()
						file = open('a.txt', 'a');  
						file.write(str(result2));  
						file.close();
			2，下载到本地：
				    1， 导入urlib库：from urllib import request
				,    2，# 下载图片 (下载音频，视频，改文件名后缀即可)：,
					request.urlretrieve(white_src（文件路径）,
					"D:\zsh（文件储存位置）"%title)      
					3，%s：格式化字符串，在字符串最后加入%title可以把title传入s的位置
					4，
					
					


爬虫图片懒加载：
https://blog.csdn.net/weixin_44774193/article/details/99899827

火狐xpath扩展工具
更多工具>面向开发者的拓展>搜索xpath>Try XPath
安装后再Expression中写入复制的xpath值
