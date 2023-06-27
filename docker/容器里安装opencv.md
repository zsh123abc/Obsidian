pip install opencv-python 报错
容器里应该安装：pip install opencv-python-headless 

报错：AttributeError: module 'cv2' has no attribute 'VideoCapture'
表示版本太高不兼容，把opencv版本降低一点

opencv版本不要安装太高，容易报错


容器里：
opencv-python-headless       4.7.0.72

安装后重启容器报错，查看容器日志：
AttributeError: partially initialized module ‘cv2‘ has no attribute ‘_registerMatType‘
因为[opencv-python](https://so.csdn.net/so/search?q=opencv-python&spm=1001.2101.3001.7020) 从4.3.0 and 3.4.10 build的包对老版本系统兼容性不好，解决方法：
pip install opencv-python install "opencv-python-headless<4.3

还是报同样错，容器里删除opencv-python，删除后重启容器没有报错

导入cv2没报错，当前版本：opencv-python-headless      4.2.0.34
cv2.VideoCapture报错：AttributeError: module 'cv2' has no attribute 'VideoCapture'
降低版本 opencv-python-headless       3.4.18.65，没有报错了，但是cv2获取帧率一直为0

