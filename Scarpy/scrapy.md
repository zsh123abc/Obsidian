
https://www.bilibili.com/video/BV1jx411b7E3/?spm_id_from=333.337.search-card.all.click&vd_source=f3c9c62f7a998ee51527ede59ab5cc91

scrapy爬虫：
```
#创建爬虫目录：
 scrapy startproject xxx
#生成爬虫：要在爬虫目录下
 scrapy genspider spider(爬虫名) "爬虫名.cn"


#设置文件（settings.py）
 ROBOTSTXT_OBEY = False
 ITEM_PIPELINES = {
    'scrapy_json.pipelines.ScrapyJsonPipeline': 300,
 }


#存储数据（items.py）
 #Field对象指明了每个字段的元数据（任何元数据）,Field对象接受的值没有任何限制
 #Field类是内置字典类（dict）的一个别名，并没有提供额外的方法和属性
 title = scrapy.Field()
 video = scrapy.Field()
 
 
#爬虫代码目录(spiders.py)
	# 导包：从上级目录下导包 ..items
	  from ..items import ScrapyJsonItem
	  
	# 启动爬虫的名字
	  name = 'json_spider'
	  
    # 限制范围
      allowed_domains = ['json_spider.cn']
    
    # 起始位置
	  start_urls =['https://tide.fm/api/v2/
	  web/explorer/scene_pages/all?tag=&offset=0&limit=512']
	  
	# 爬取多页数据(按需求)
	  url =['https://tide.fm/api/v2/web/
	  explorer/scene_pages/alltag=&offset=0&limit=512',

	  'https://tide.fm/api/v2/web/
	  explorer/scene_pages/all?tag=Video&offset=0&limit=512',

	  'https://tide.fm/api/v2/web/
       explorer/scene_pages/all?tag=Free&offset=0&limit=512']

    
 提取html数据
  def parse(self, response):
	 完善spider 使用xpath等解析
	 拿到所有div遍历
	 node_list = response.xpath("
	 //section[@class='scenes']/div")
	
	 遍历完的数据存进item = ItcastItem()
	 title = node.xpath("a/div/span/text()").extract()[0]
	 item["title"] = title
	
	 返回给管道文件处理
	 yield item

 提取json页面数据
  def parse(self, response):
	 # 拿到所有数据
	 pageData = json.loads(response.text)
	 # 循环拿数据：
	 for node in pageData["scenes"]:
		 # 字典数据直接指定key拿value
		 img_name = node["name"]
	     item["title"] = img_name["zh-Hans"]
		 item['video'] = node["video_cover_demo_url"] 
		 # 每拿到一次数据就返回给管道文件做处理 
	     yield item
	     
	 # 如果需要爬取多重页面的数据，可以使用scrapy.Request回调函数，
	 # 传入新的url地址，指定回调函数
	 if self.url is not None:
         index = 0
         index = index + 1
         next_url = self.url[index]    
         yield scrapy.Request(next_url, callback= self.parse)


#取出数据，并做处理(pipelines.py)
  # 文件开始的时候运行
  def __init__(self):
	# 创建文件用于储存数据  
    self.txt_file = open('data.txt', 'w', encoding='utf-8')
    
  # 存储文件数据  
  def process_item(self, item, spider):
 
	 title = item["title"]
	 video = item["video"]
 

	 # 下载到本地文件夹	
	 %：格式化字符串 %title可以把title传到%s	  
	 request.urlretrieve(video,"D:\%s.MP4"%title)  
	 
  # 文件关闭的时候执行	 
  def close_spider(self, spider):  
    #关闭打开的文件
    self.txt_file.close()


#运行爬虫并且保存数据
 scrapy crawl 爬虫名 
 (-o 文件名.文件格式)

```
