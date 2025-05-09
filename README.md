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
1. **创建工作目录:**
    ```bash
    mkdir -p /opt/traccar/logs
    ```

1. **获取默认 traccar.xml:**
    ```bash
    docker run \
    --rm \
    --entrypoint cat \
    traccar/traccar:latest \
    /opt/traccar/conf/traccar.xml > /opt/traccar/traccar.xml
    ```

1. **编辑 traccar.xml:** <https://www.traccar.org/configuration-file/>

1. **创建容器:**
    ```bash
    docker run \
    --name traccar \
    --hostname traccar \
    --detach --restart unless-stopped \
    --publish 80:8082 \
    --publish 5000-5150:5000-5150 \
    --publish 5000-5150:5000-5150/udp \
    --volume /opt/traccar/logs:/opt/traccar/logs:rw \
    --volume /opt/traccar/traccar.xml:/opt/traccar/conf/traccar.xml:ro \
    --volume /opt/traccar/data:/opt/traccar/data:rw \
    traccar/traccar:latest
    ```

## 数据库
执行上述“docker run”命令时的默认值是内部H2数据库，但这应该仅供基本使用.  

默认情况下，Traccar使用嵌入式H2数据库，但我们不建议将其用于生产。生产环境推荐使用外部MySQL数据库， 配置方法请看 [Traccar MySQL documentation](https://www.traccar.org/mysql/).

## 默认JVM选项:
- `-Xms1g`
- `-Xmx1g`
- `-Djava.net.preferIPv4Stack=true`
