# 创建并推送 Traccar-amap Docker 镜像
---

**Traccar GPS Tracking System in Docker image.**

支持网站: <http://bbs.atoo.top:8081>  
DockerHub 镜像: <https://hub.docker.com/r/bg6rsh/traccar> ![](https://img.shields.io/docker/stars/traccar/traccar) ![](https://img.shields.io/docker/pulls/traccar/traccar)  
维护者: [Bg6rsh](https://github.com/bg6rsh)

## 可用标签:
#### 6.X
- **6.6-alpine**, **6-alpine**, **alpine**, **6.6**, **6**, **latest** ![](https://img.shields.io/docker/image-size/traccar/traccar/6.6-alpine)
- **6.6-debian**, **6-debian**, **debian** ![](https://img.shields.io/docker/image-size/traccar/traccar/6.6-debian)
- **6.6-ubuntu**, **6-ubuntu**, **ubuntu** ![](https://img.shields.io/docker/image-size/traccar/traccar/6.6-ubuntu)
- _..._



## 支持多平台:
**Alpine based**: linux/amd64, linux/arm64  
**Debian based**: linux/amd64, linux/arm64  
**Ubuntu based**: linux/amd64, linux/arm64, linux/arm/v7

## 容器创建示例:
1. **在官网下载原版服务程序压缩包:**
    ```bash
    wget https://github.com/traccar/traccar/releases/download/v6.6/traccar-other-6.6.zip
    ```

2. **制作适配版服务程序压缩包**
    将适配版 tracker-server.jar,traccar.xml,changelog-gcj02.xml,changelog-master.xml 复制到原版服务程序:traccar-other-6.6.zip
    

## 数据库
执行上述“docker run”命令时的默认值是内部H2数据库，但这应该仅供基本使用.  

默认情况下，Traccar使用嵌入式H2数据库，但我们不建议将其用于生产。生产环境推荐使用外部MySQL数据库， 配置方法请看 [Traccar MySQL documentation](https://www.traccar.org/mysql/).

