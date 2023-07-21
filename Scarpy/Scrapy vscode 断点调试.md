1.mian.py 与scrapy.cfg在同一层级

from scrapy.cmdline import execute
import os
import sys

if __name__ == '__main__':
    #sys.path.append(os.path.dirname(os.path.abspath(__file__)))
    fpath = os.path.abspath(os.path.join(os.path.dirname(__file__),".."))
    ffpath = os.path.abspath(os.path.join(fpath,".."))
    sys.path.append(ffpath)
    execute(['scrapy','crawl','bomman'])

2.设置vs code断点,参考https://blog.csdn.net/SeaBiscuitUncle/article/details/103917401

　 启动时(必需先双击打开mian.py文件,在mian.py文件下点击运行-->启动调试，否则调试时报‘ModuleNotFoundError’错误)，断点调试后，可在控制台输入变量查看，如下所示：![[Pasted image 20221011100134.png]]![[Pasted image 20221011101036.png]]


scrapy运行程序报错：
AttributeError:'TelnetConsole' object has no attribute 'port'
https://www.jianshu.com/p/d2a8e7641a51
**解决方法**  
更改settings.py文件中（如图）：

```python
EXTENSIONS = {

   'scrapy.extensions.telnet.TelnetConsole': None,

}
```


scrapy运行程序报错：
AttributeError: module 'fcntl' has no attribute 'F_GETFD'
https://www.jianshu.com/p/8b6ca1fcd437?utm_campaign=maleskine&utm_content=note&utm_medium=seo_notes&utm_source=recommendation
`C:\Users\cwj\AppData\Local\Programs\Python\Python310\Lib`文件里把
```css
fcntl.py
```
改为

```css
fcntl_ex.py
```