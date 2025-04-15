# Docker

#### download docker

参考：[Ubuntu 22.04 安装 Docker 容器 - 知乎](https://zhuanlan.zhihu.com/p/25850755057)

#### upgrade docker

```Sh
sudo apt update
sudo apt update
sudo apt full-upgrade
```

#### show images

```sh
sudo docker images
```

#### delete image

```sh
# 二选一即可
docker rmi <image-id>
docker image rm <image-id>
```

#### download images

```sh
sudo docker pill ubuntu
```

---

#### run docker

```sh
sudo docker run -it ubuntu:<TAG> --name <Name> /bin/bash
```

- `-t`：在 Ubuntu 容器内分配一个伪终端。
- `-i`：通过从容器获取一个标准输入（STDIN），允许我们创建一个可交互的连接。
- `ubuntu:latest`：标签为 `latest` 的 Ubuntu Docker 镜像。
- `/bin/bash`：新容器的 BASH shell。这个是可选项。如果不加 shell 的话，会分配默认的 shell 给容器。

#### detach docker terminal

```
Ctrl+P, Ctrl+Q
```

#### show container status

```sh
docker ps [-a]
```

`-a`：显示所有容器，包括已停止的等等。

#### attach docker terminal

```sh
sudo docker attach <container-id|name>
```

#### start/stop/pause/unpause/remove docker

```sh
sudo docker start/stop/pause/unpause/rm <name>
# rm [-f] 强制删除容器，不论其是否运行
# stop a container in the docker's shell
exit
```

#### rename

```sh
sudo docker rename <raw-name> <new-name>
```

清理缓存：

```sh
# 查看磁盘使用情况
df -h
# 清理Docker缓存和未使用的镜像/容器
docker system prune -a --volumes
# 清理临时文件
sudo rm -rf /tmp/*
```

### DockerHub

配置见： [Docker/DockerHub 国内镜像源/加速列表（4月6日更新-长期维护）-腾讯云开发者社区-腾讯云](https://cloud.tencent.com/developer/article/2485043)

毫秒镜像： [毫秒镜像](https://1ms.run/)

```sh
sudo mkdir -p /etc/docker
sudo tee /etc/docker/daemon.json <<EOF
{
    "registry-mirrors": [
        "https://docker.1ms.run",
        "https://docker.xuanyuan.me"
    ]
}
EOF
sudo systemctl daemon-reload
sudo systemctl restart docker
```

























