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