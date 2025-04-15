# Docker Compose

*实现对 Docker 容器集群的快速编排*

进入docker-compose.yml的上级目录，执行：

```sh
docker-compose up -d <user1> # up是构建镜像并启动容器
```

- `-d`：后台运行容器。
- 首次运行会自动构建镜像（若镜像未构建过）。

在同目录下，验证容器状态：

```sh
docker-compose ps      # 查看容器运行状态
docker-compose logs <user1>  # 查看日志，确认Jupyter正常启动
```

删除原有容器并重新构建

```sh
# 停止并删除 docker-compose.yml 中定义的所有容器
# 不会删除镜像或数据卷（挂载的宿主机目录不受影响）
docker-compose down 
# 额外删除镜像和匿名卷（完全重置环境）
docker-compose down --rmi all --volumes
# 强制重新构建
docker-compose build --no-cache
# 启动容器
docker-compose up -d
# 进入容器
docker exec -it <user1> bash
```

退出容器并重新进入

```sh
exit
# 查看容器 ID
docker ps --filter name=<user1>
# 进入容器
docker exec -it <id|name> bash
```

虚拟机IP：192.168.230.129

