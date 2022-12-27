python web flask 日志配置：
https://blog.csdn.net/qq_48082548/article/details/120691855

不同的环境下日志的等级也是不一样的
生产环境:WARNING
开发环境:DEBUG
测试环境:DEBUGH

flask调用同时生成日志
		# 设置日志的记录等级
			BaseConfig配置中设置level = logging.DEBUG
        logging.basicConfig(level=BaseConfig.level) # 调试debug级
        # 创建日志记录器，指明日志保存的路径（前面的logs为文件的名字，需要我们手动创建，后面则会自动创建）、每个日志文件的最大大小、保存的日志文件个数上限。
        # logs目录自己创建
        file_log_handler = RotatingFileHandler("./logs/log", maxBytes=1024*1024*100, backupCount=10)
        # 创建日志记录的格式               日志等级    输入日志信息的文件名   行数       日志信息
        formatter = logging.Formatter('%(levelname)s %(filename)s:%(lineno)d %(message)s')
        # 为刚创建的日志记录器设置日志记录格式
        file_log_handler.setFormatter(formatter)
        # 为全局的日志工具对象（flask app使用的）添加日志记录器
        logging.getLogger().addHandler(file_log_handler)
        
app = Flask(__name__)