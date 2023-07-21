Git 详细安装教程：
https://blog.csdn.net/mukes/article/details/115693833
git-lfg安装：解决推拉大文件时效率和性能问题
https://blog.csdn.net/wzk4869/article/details/130636377
```python
sudo apt-get install git-lfs
```

```python
git lfs install
```

git操作：
1，进入要管理的目录

2，初始化
```
git init   
```

3，查看管理目录下的文件状态，查看文件是否被添加至追踪区
```
git status 
```

工作区：新添加或修改过的文件，未被追踪
暂存区：已被追踪(git add)，等待提交版本库
版本库：本都版本库，存放所有提交的版本，可回滚到以前版本
远程仓库：需联网，从本地仓库(git push)上传到远程仓库，(git pull)拉取代码到本地仓库

4，将文件添加至追踪区
```
git add
```

三种状态的变化：
		未管理的红色，管理后变成绿色
		新增/修改：git add 文件名，管理文件，放入暂存区，等待提交
		
把文件状态还原为为追踪，相当于add的反向
```
git rm --cached
```
			
个人信息配置【一次即可】：
```
git config --global user.email "邮箱"
```

```
git config --global user.name "名字"
```
		
5，生成版本
```
git commit -m '描述信息'
```

6.1，查看所有版本
```
git log 
```
6.2，查看所有版本（包括回滚记录，和回滚之前的版本）
```
git reflog
```
	 
7，回滚(类似于撤回操作)
```
git reset --hard commit(版本编号)
```

8， 显示过去5次提交
```
git log -5 --pretty --oneline
```

9，查看分支
```
git branch：
```
创建分支
```
git branch 分支名称
```
切换分支	
```
git checkout 分支名称
```
合并分支（可能产生冲突）
```
git  merge 分支名称
```
两个分支修改了同一行代码，合并时就会产生
冲突，可手动解决，也可以用beyoudC工具解决

删除分支 
```
git branch -d 分支名称
```
     
10，  给远程仓库起别名：
```
git remote add origin 远程仓库地址
```
向远程仓库推送代码
```
git push -u origin 分支
```
		
11，在不同机器进行开发，从远程仓库取出代码

克隆远程仓库代码：
```
git clone 远程仓库地址(第一次需要，后续只需pull)
			
```
拉取仓库代码
```
git pull origin 分支名称
```
切换分支
```
git checkout 分支
```
		
把master分支合并到dev[一次]：
```
git merge master
```

开发完后提交：
```
git add
git commit -m 'xxx'
git push origin dev
git push https不行就换SSH
https：git push https://github.com/zsh123abc/python.git
SSH：git push git@github.com:zsh123abc/python.git
```

修改git缓存的大小，100M不行就1000M
```powershell
git config --global http.postBuffer 100M
```

流程：
在主分支的基础下创建新分支，把主分支的代码合并到新分支，修改操作在新分支下进行操作，修改好稳定之后在切回主分支，把新分支合并到主分支，然后push提交到远程仓库，
不同机器上操作，第一次先clone远程仓库的代码到本地，后续pull拉代码就可


git clone报错
fatal: unable to access 'xxxxx': Empty reply from server
解除ssl验证
```
git config --global http.sslVerify false
```

解决 github 报错 Failed to connect to github.com port 443:connection timed out
```bash
取消全局代理：
git config --global --unset http.proxy 
git config --global --unset https.proxy
```


从其他地方克隆，加上用户名，然后输入密码
git clone https://zhangsihao@code.17yund.me/ai/label_system_backend_python.git


git clone https://github.com/zsh123abc/git_P.git

git vim : https://blog.csdn.net/weixin_42666707/article/details/120595776

git详解：
https://blog.csdn.net/bjbz_cxy/article/details/116703787

CAP定理：
https://blog.csdn.net/weixin_45887061/article/details/122781134

git常用命令
https://m.php.cn/tool/git/464354.html

GitLab
https://code.17yund.me/zhangsihao/label_system_backend_python.git

git 设置代理、取消代理、查看代理
https://blog.csdn.net/weixin_50726818/article/details/128445447

报错信息：
GitHub fatal: unable to access 或 gnutls_handshake() failed: The TLS connection was non-properly 解决办法
https://blog.csdn.net/qq_31375855/article/details/121838533