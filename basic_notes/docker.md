# docker命令

## 1. 系统管理指令

```bash
# 启动/停止服务
systemctl start docker    # 启动Docker服务 ‌
systemctl stop docker     # 停止Docker服务 ‌
systemctl restart docker  # 重启Docker服务 ‌
systemctl enable docker   # 设置开机自启动 ‌

# 查看服务状态
systemctl status docker   # 查看Docker运行状态 ‌
docker version            # 查看Docker版本信息 ‌
docker info               # 查看Docker系统信息 ‌
```


## 2. 镜像管理指令
```bash
# 搜索与拉取镜像
docker search nginx       # 搜索镜像 
docker pull ubuntu:20.04  # 拉取指定版本镜像 

# 本地镜像操作
docker images             # 列出所有镜像 
docker rmi ubuntu:20.04   # 删除指定镜像 
docker rmi $(docker images -q)  # 删除全部镜像 
```
## 3. 容器操作指令
```bash
# 创建并启动容器
docker run -it --name my_ubuntu ubuntu:20.04 /bin/bash  # 交互式运行容器 
docker run -d -p 8080:80 --name my_nginx nginx          # 后台运行并映射端口 

# 容器生命周期管理
docker start my_nginx      # 启动已停止的容器 
docker stop my_nginx       # 停止运行中的容器 
docker restart my_nginx    # 重启容器 
docker rm my_nginx         # 删除已停止的容器 
docker stop $(docker ps -q)# 停止所有运行中的容器 
docker container prune     # 清理所有停止的容器 

# 查看与进入容器
docker ps                  # 查看运行中的容器 
docker ps -a               # 查看所有容器（包括停止的） 
docker exec -it my_nginx /bin/bash  # 进入运行中的容器 
```
## 4. 数据管理指令
```bash
# 挂载数据卷
docker run -v /host/path:/container/path nginx  # 挂载主机目录到容器 
docker volume create my_volume                  # 创建数据卷 

# 管理数据卷容器
docker run --volumes-from data_container my_app  # 复用其他容器的数据卷 
```
## 5. 网络管理指令
```bash
# 端口映射与网络配置
docker run -p 3306:3306 mysql    # 映射主机端口到容器端口 
docker network create my_network # 创建自定义网络 
docker network ls                # 列出所有网络 
```
## 6. 日志与监控指令
```bash
# 查看日志和资源使用
docker logs my_nginx         # 查看容器日志 ‌
docker stats my_nginx        # 实时监控容器资源使用 ‌
docker top my_nginx          # 查看容器内进程列表 
```

## 7. Dockerfile构建镜像
```bash
# 构建自定义镜像
docker build -t my_image:1.0 .  # 根据当前目录的Dockerfile构建镜像 ‌
```
