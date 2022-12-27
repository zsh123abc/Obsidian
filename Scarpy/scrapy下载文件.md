一：使用Python中的[urllib](https://so.csdn.net/so/search?q=urllib&spm=1001.2101.3001.7020)类中的urlretrieve()函数，直接从网上下载资源到本地，具体代码：

import os,stat
import urllib.request

#图片地址
img_url="https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1516371301&di=d99af0828bb301fea27c2149a7070""d44&imgtype=jpg&er=1&src=http%3A%2F%2Fupload.qianhuaweb.com%2F2017%2F0718%2F1500369506683.jpg"

#下载完的图片储存位置
file_path='D:/book/img'
#文件名字
file_name ="pyt"

#异常处理 
try:
		#是否有这个路径
		if not os.path.exists(file_path):	
				#创建路径
				os.makedirs(file_path)				
				#获得图片后缀				
				file_suffix = os.path.splitext(img_url)[1]				
				print(file_suffix)			
				#拼接图片名（包含路径）
				filename = '{}{}{}{}'.format(file_path,os.sep,file_name,file_suffix)			
				print(filename)			
				#下载图片，并保存到文件夹中
				urllib.request.urlretrieve(img_url,filename=filename)				
				except IOError as e:				
				print("IOError")
	
except Exception as e:
	print("Exception")


二：利用读写操作写入文件，具体代码：

import os,stat
import urllib.request

for i in range(1,3):

if not os.path.exists("./rym"):
print("不纯在")
os.makedirs("./rym")
else:
print("存在")

os.chmod("D:/imagss",777)
with urllib.request.urlopen("https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1516371301&di=d99af0828b""b301fea27c2149a7070d44&imgtype=jpg&er=1&src=http%3A%2F%2Fupload.qianhuaweb.com%2F2017%2F0718%""2F1500369506683.jpg",
timeout=30) as response, open("./rym/lyj.png", 'wb') as f_save:
f_save.write(response.read())
f_save.flush()
f_save.close()
print("成功")

三：以二进制方式写入文件即可
f = open(r"E:\Picture\0.png",'wb')#注意写入方式
f.write(urllib2.urlopen(url).read())
f.close()

四：调用urllib库函数
urllib.urlretrieve(url,"E:\Picture\%s.jpg"%0)

以上两种方式保存的图片路径均为E:\Picture\0.png