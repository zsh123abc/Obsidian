1，Python 包是如何定义，安装，管理的，执行时是如何定位并加载的

		 导入fk_package包，实际上就是导入包下__init__.py文件
		 import my_package
		 导入fk_package包下的print_shape模块，
		 实际上就是导入fk_package目录下的print_shape.py
		 import my_package.print_shape
		 实际上就是导入fk_package包（模块）导入print_shape模块
		 from my_package import billing
		 导入fk_package包下的arithmetic_chart模块，
		
		 实际上就是导入fk_package目录下的arithmetic_chart.py
		 mport my_package.arithmetic_chart
		
		 包就是模块
		 这里导入my_package包，就是导入此包下面的__init__文件
		 而在__init__文件中，又导入了另外三个模块
		 所以只用导入my_package包就能用所有的模块
		
		 import my_package
		
		 my_package.print_blank_triangle(5)
		 im = my_package.Item(4.5)
		 print(im)
		 my_package.print_multiple_chart(5)

		Import导入包或模块时，Python 解释器寻找模块的[优先级]如下：
			A、当前目录
			B、环境变量PYTHONPATH			
			C、sys.path(list 类型)
			
		导入不同磁盘下的包：
			https://blog.csdn.net/xuezhangmen/article/details/126986496
			
		from import 和 import的区别：
			https://blog.csdn.net/xkukeer/article/details/123817053
			
2，类编写，继承，实例化过程，成员变量，成员方法的种类， 

			 (__init__)构造方法：在实例化类时自动运行
			 (__new__)方法：它是负责创建类实例的静态方法。
			 继承：它可以使用现有类的所有功能，并在无需重新编写原来的类的情况下对这些功能进行扩展
			 实例化过程：__new__方法将被调用以创建一个新的对象，作为所需类的实例（对象创建）__init__ 
		     方法将被调用以初始化该对象（对象初始化）
		成员变量：
		    1，成员变量是在构造方法init（）中定义的，通过self调用
			2，在类的外部,成员变量属于**对象**,只能通过**对象名**访问;
	    成员方法：
		    1，Python类的成员方法大致可以分为公有方法、私有方法、静态方法、类方法这几种类型		
		     
3，字符串的一系列常用的处理处理，查找，替换，合并，格式化，截取等  

		字符串的常用处理：
				1，小写字母转化为大写：
						upper()
				2，大写字母转化为小写：
						lower()
				3，把大写转化为小写。小写转化为大写：
						swapcase()
				4，替换字符串中的子字符串：
						replace("字符串中的","替换的字符串")
				5，制定新字符串长度，不足用部分用制定字符填中：
						center(15,"=")
				6，制定分隔符，对字符串进行分割：
						split()
				7，移除字符串头、尾特定字符串：
						strip()
				8，统计子串出现的数量：
						count('j')
				9，查找制定的最左边的字符串，并返回对应下标：
						find('j')
				10，判断字符串是否都是字母：
						isalpha()
				11，判断字符串中每个元素是否是十进制数，包括全角：
						isdecimal()
				12，判断字符串是否都是大写：
						isupper()
				13，判断字符串是否都是小写：
						islower()
		字符串：
				https://blog.csdn.net/weixin_37988176/article/details/109374729
				https://blog.csdn.net/weixin_39704246/article/details/110274118? ops_request_misc=&request_id=&biz_id=102&utm_term=python%E5%AD%97%E7%AC%A6%E4%B8%B2%E5%9F%BA%E7%A1%80%E7%BB%83%E4%B9%A0%E9%A2%98&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduweb~default-1-110274118.nonecase&spm=1018.2226.3001.4187
				https://blog.csdn.net/weixin_37988176/article/details/109376909
		
4，迭代器，生成器的原理，  

	迭代器：
			1，迭代器 给 可迭代对象 迭代，
			2，迭代器就是有一个 next() 方法的对象
			迭代器 ：优点：提供了一种通用不依赖索引的迭代取值方式
						   缺点： -   取值不够灵活。next方法只能往后取值,不能往前，
									  -   无法预测迭代器的长度，
									  -   用完一次就失效
			普通的迭代器不能节省内存
	生成器：
			1，含有yield语句的函数是生成器函数,此函数被调用将会返回一个生成器对象
			2，生成器 = 可迭代对象(有__iter__方法) + 迭代器(有__next__方法)
			3，(yield)是一种特殊的迭代器。
			4，能够动态（循环一次，计算一次，返回一次）提供数据的可迭代象
			5，作用：在需要的时候才计算结果，节省内存

5，数组，字典的特性，常规使用， 

		(1) list 普通的链表，初始化后可以通过特定方法动态增加元素。
			 定义方式：arr = [元素]
		(2) Tuple 固定的数组，一旦定义后，其元素个数是不能再改变的。
			 定义方式：arr = (元素)
		(3) Dictionary 词典类型， 即是Hash数组。
			定义方式：arr = {元素k:v}

		合并字典的四种方法：
			https://blog.csdn.net/Jerry_1126/article/details/73017270?spm=1001.2101.3001.6661.1&utm_medium=distribute.pc_relevant_t0.none-task-blog-2%7Edefault%7ECTRLIST%7ERate-1-73017270-blog-124254929.pc_relevant_3mothn_strategy_recovery&depth_1-utm_source=distribute.pc_relevant_t0.none-task-blog-2%7Edefault%7ECTRLIST%7ERate-1-73017270-blog-124254929.pc_relevant_3mothn_strategy_recovery&utm_relevant_index=1
		
6，正则表达式的简单实用

		python中如何使用正则表达式
		https://blog.csdn.net/FlatTiger/article/details/123899607
		https://blog.csdn.net/weixin_39913648/article/details/113968415

> break：跳出所在的当前整个循环，到外层代码继续执行
 
> continue：跳出本次循环，从下一个迭代继续运行循环，内层循环执行完毕，外层代码继续运行
 
> return：直接返回函数，所有该函数体内的代码（包括循环体）都不会再执行