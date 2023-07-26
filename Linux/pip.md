pip国内镜像源：

阿里云	http://mirrors.aliyun.com/pypi/simple/
中国科技大学 	https://pypi.mirrors.ustc.edu.cn/simple/
豆瓣	 http://pypi.douban.com/simple
Python官方	 https://pypi.python.org/simple/
v2ex	 http://pypi.v2ex.com/simple/
中国科学院 	http://pypi.mirrors.opencas.cn/simple/
清华大学	 https://pypi.tuna.tsinghua.edu.cn/simple/

添加  -i  使用

修改pip安装路径


infer_cfg.yml

python -m site
`D:\ANACONDA_3520\lib\site.py`

python -m site -help

CentOS7上pip的安装方式
https://blog.csdn.net/liumiaocn/article/details/103038746



basketball_frame  篮筐
basket_net  篮筐+篮网
backboard  篮板




tokenizer = AutoTokenizer.from_pretrained("THUDM/chatglm-6b", trust_remote_code=True, mirror='https://mirrors.tuna.tsinghua.edu.cn/hugging-face-models')
model = AutoModel.from_pretrained("THUDM/chatglm-6b", trust_remote_code=True, mirror='https://mirrors.tuna.tsinghua.edu.cn/hugging-face-models').half().quantize(4).cuda()



https://www.bilibili.com/video/BV1za411Q79x/?spm_id_from=333.999.0.0

https://www.bilibili.com/video/BV1UV4y1E7zQ/?spm_id_from=333.999.0.0