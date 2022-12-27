1.显示文件内容
```ruby
cat 文件名或目录
```

2.终端查看多个文件的内容
```crystal
cat rumenz rumenz1
```

3.用cat命令创建文件
```crystal
cat > rumenz2
```

等待用户输入，键入所需文本，然后按 CTRL+D （按住 Ctrl key 并输入d） 退出
```crystal
cat rumenz2
```

4.使用more和less参数的Cat命令
如果有大量的内容，屏幕滚动起来非常快，我们可以使用参数more和less
```crystal
cat a.txt | more
cat a.txt | less
```

5.在文件中显示行号
```crystal
cat -n a.txt
```
6.在文件末尾显示$
```crystal
cat -e a.txt
```