创建爬虫目录：
```scrapy
scrapy startproject 目录名
```

生成爬虫：要在爬虫目录下
```
scrapy genspider 爬虫名 "要爬网站名.cn"
```

存储数据（items.py）
定义元数据，可以接受任何类型的数据,Field()是内置字典的一个别名
```
name = scrapy.Field()
```

设置文件（settings.py）
打开注释
 ```
# 是否遵循协议，遵循协议可能爬取失败
ROBOTSTXT_OBEY = False
# 爬虫优先级
ITEM_PIPELINES = {
    'scrapy_json.pipelines.ScrapyJsonPipeline': 300,
 }
```

爬虫代码（itcast.py）
1，导入items用来存储和传递数据
```
from ..items import ScrapyTestItem
```
2，设置初始域名
```
start_urls = ['https://tide.fm/meditation/']
```
3，xpath解析获取到所有数据，在进一步for解析获取指定数据
	在解析图片src属性时可能得到png格式不能用，因为前端图片 懒加载
```
node_list = response.xpath("/html/body/div/div/div/div[1]/div[4]/div/a")
```

取出数据，并做处理，管道文件(pipelines.py)
1，定义__init__函数，调用就创建文件
```
self.f = open('data.txt','w',encoding='utf-8')
```
2，process_item()里，取出item储存的数据，并做相应处理如下载，保存数据至文本
 保存数据至init函数中打开的文件，每存一次换一行
```
self.f.write('%s,%s,%s\n'%(name,img,url))
```
 根据url下载对应文件（图片，音频，视频）
```
from urllib import request

request.urlretrieve(img,r"D:\zsh\zsh_scrapy2\scrapy_test\text\img\%s.jpg"%name)
```

管道文件上级目录，运行爬虫
```
scrapy crawl 爬虫名 
```

保存至数据库
	连接数据库
	pyconfig = {
            'host':'localhost',
            'port':3306,
            'user':'root',
            'password':'123456',
            'database': 'Scrapy'
        }
        self.db = pymysql.connect(**pyconfig)
        self.cursor = self.db.cursor(pymysql.cursors.DictCursor)
	  数据库插入
        insetr_sql = "insert into scrapy (name,img,url) VALUES (%s,%s,%s)"
        nsert_value = (item['name'],item['img'],item['url'])
        self.cursor.execute(insetr_sql,nsert_value)
        result = self.cursor.fetchall()
        self.db.commit()