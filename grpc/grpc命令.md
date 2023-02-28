根据proto文件创建对应的 _pb2.py，_pb2_gtcp.py:
```javascript
python -m grpc_tools.protoc -I. --python_out=. --grpc_python_out=. ReceiveData.proto
```



