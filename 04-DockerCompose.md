# Docker Compose

*实现对 Docker 容器集群的快速编排*

进入docker-compose.yml的上级目录，执行：

```sh
docker-compose up -d <user1>
```

- `-d`：后台运行容器。
- 首次运行会自动构建镜像（若镜像未构建过）。

在同目录下，验证容器状态：

```sh
docker-compose ps      # 查看容器运行状态
docker-compose logs <user1>  # 查看日志，确认Jupyter正常启动
```

停止并删除旧容器

```sh
# 强制删除容器（包括已停止的）
docker-compose down --rmi all
```

