Docker版Stable Diffusion WebUI，可cpu运行
https://zhuanlan.zhihu.com/p/614421868

```docker
docker run -it --name sdw --network host \
  -v /mnt/d/software/ai/stable-diffusion-webui/models:/app/stable-diffusion-webui/models \
  -v /mnt/d/software/ai/stable-diffusion-webui/outputs:/app/stable-diffusion-webui/outputs \
  --rm siutin/stable-diffusion-webui-docker \
  bash webui.sh --skip-torch-cuda-test --precision full --no-half --use-cpu Stable-diffusion GFPGAN ESRGAN VAE --all --share
```
--rm 容器退出自动删除容器


```docker
docker run -it --name sdw2 --network host \
  -v /a2/stable-diffusion-webui2:/app/stable-diffusion-webui \
  -p 10090:8090\
   siutin/stable-diffusion-webui-docker \
  bash webui.sh --listen --port 8090 --skip-torch-cuda-test --precision full --no-half Stable-diffusion GFPGAN ESRGAN VAE --all --share
```


```docker
docker run -it --name sdw --network host \
-v /a2/stable-diffusion-webui/models:/app/stable-diffusion-webui/models \  
-v /a2/stable-diffusion-webui/outputs:/app/stable-diffusion-webui/outputs \  
  --rm siutin/stable-diffusion-webui-docker \
  bash webui.sh --skip-torch-cuda-test --precision full --no-half --use-cpu Stable-diffusion GFPGAN ESRGAN VAE --all --share
```


docker run -it --name sdw2 --network host \  
  --gpus all \  
  -v /a2/stable-diffusion-webui/models:/app/stable-diffusion-webui/models \  
  -v /a2/stable-diffusion-webui/outputs:/app/stable-diffusion-webui/outputs \  
  -p 10080:8090\  
   siutin/stable-diffusion-webui-docker \  
  bash webui.sh --listen --port 8090 --skip-torch-cuda-test --precision full --no-half  Stable-diffusion GFPGAN ESRGAN VAE --all --share


sudo docker run -it  --name sdw2  --network host  --gpus all  -v /a2/stable-diffusion-webui/models:/app/stable-diffusion-webui/models  /a2/stable-diffusion-webui/outputs:/app/stable-diffusion-webui/outputs -p 10080:8090 siutin/stable-diffusion-webui-docker  bash webui.sh --listen --port 8090 --skip-torch-cuda-test --precision full --no-half  Stable-diffusion GFPGAN ESRGAN VAE --all --share




apt update && sudo apt install -y python3 python3-pip python3-venv git \
&& pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple \
&& pip install torch \
&& pip install torchvision \
&& pip install gfpgan \
&& pip install clip \
&& pip install opencv-python-headless \
&& git clone https://github.com/AUTOMATIC1111/stable-diffusion-webui 



docker run --gpus all -it -p 8888:8888 -p 7860:7860 -p 6666:22 --name ayanami --ipc=host darkroot1234/ayanami:latest