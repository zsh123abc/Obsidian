

```bash
docker pull soulteary/stable-diffusion:taiyi-0.1
```


```bash
git clone https://huggingface.co/IDEA-CCNL/Taiyi-Stable-Diffusion-1B-Chinese-v0.1
```

编写docker-compose
```
version: "2"
services:

  taiyi:
    image: soulteary/stable-diffusion:taiyi-0.1
    container_name: taiyi
    restart: always
    runtime: nvidia
    ipc: host
    ports:
      - "7860:7860"
    volumes:
      - ./Taiyi-Stable-Diffusion-1B-Chinese-v0.1:/stable-diffusion-webui/models/Taiyi-Stable-Diffusion-1B-Chinese-v0.1
```

```
docker compose up -d
```
