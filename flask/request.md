request对象的导入
```python
from flask import request
```

Json请求: 使用 request.data 获取请求体
```python
    # 接收处理json数据请求    
    data = json.loads(request.data) # 将json字符串转为dict   
    user_name = data['user_name']
```

form表单请求：request.form 获取请求参数
```python
    # 接收post请求的form表单参数    
    user_name = request.form.get('user_name')
```

URL请求参数: request.args
```python
    # 接收处理GET数据请求    
    user_name = request.args.get('user_name')
```

上传文件请求：request.files
```python
    # 接收post请求上传的文件    
    file = request.files.get('file'
```
